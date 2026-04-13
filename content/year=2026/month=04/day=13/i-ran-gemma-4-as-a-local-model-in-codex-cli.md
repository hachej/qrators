---
download_date: "2026-04-13T10:48:26Z"
source_url: "https://medium.com/google-cloud/i-ran-gemma-4-as-a-local-model-in-codex-cli-7fda754dc0d4"
added_by: "christophe"
source_type: "blog"
title: "I ran Gemma 4 as a local model in Codex CLI"
tags: ["gemma", "local-models", "codex-cli", "agentic-coding"]
---

I ran Gemma 4 as a local model in Codex CLI

/@danielvaughan?source=post_page---byline--7fda754dc0d4---------------------------------------
6 min read8 hours ago

--

Press enter or click to view image in full size

Sketchnote comparing Gemma 4 local inference on a 24 GB MacBook Pro and Dell GB10, showing that model quality beats raw token speed for agentic coding.I wanted to know whether Gemma 4 could replace a cloud model for my day-to-day agentic coding. Not in theory, in practice. I use Codex CLI every day, running GPT-5.4 as my default model. It works well, but every token costs money, and every prompt sends my code to someone else’s server. Gemma 4 promised local tool calling that works. I spent a day finding out whether that promise holds.
I set up two machines. A 24 GB M4 Pro MacBook Pro, the laptop I carry everywhere, running the 26B MoE variant via llama.cpp. And a Dell Pro Max GB10, 128 GB of unified memory on an NVIDIA Blackwell chip, running the 31B Dense variant via Ollama v0.20.5. Both configured as custom model providers in Codex CLI’s config.toml with wire_api = "responses". Then I ran the same code generation task on both, and on the cloud model as a baseline.
The short answer: local Gemma 4 works. The longer answer involves an afternoon of debugging, some surprising benchmark numbers and a finding about model architecture that I was not expecting.

## Why I wanted this
Three things pushed me towards local models. First, cost. I run Codex CLI heavily, multiple sessions a day, sometimes in parallel. The API bills add up. Second, privacy. Some of the codebases I work with should not leave my machine. Third, resilience. Cloud APIs throttle, go down and change pricing. A local model runs.
The reason I had not done this before is that local models could not call tools. Codex CLI’s entire value comes from the model reading files, writing code, running tests and applying patches. If the model cannot reliably emit {"tool": "Read", "args": {"file": "package.json"}}, it is useless as an agent. Previous Gemma generations scored 6.6 per cent on the tau2-bench function-calling benchmark. That is 93 failures out of 100. Not a foundation for anything.
Gemma 4 31B scores 86.4 per cent on the same benchmark. That is what made this test worth running.

## What it took to get a working setup
Neither machine worked on the first attempt.
The Mac. I started with Ollama, because it is the simplest path. Two bugs killed it immediately. A streaming bug in v0.20.3 routes Gemma 4’s tool-call responses to the wrong field, landing them in the reasoning output instead of the tool_calls array. Separately, a Flash Attention freeze hangs Ollama on any prompt longer than about 500 tokens with Gemma 4 on Apple Silicon. Codex CLI’s system prompt alone is roughly 27,000 tokens. So Ollama freezes before it even starts processing your request.
I switched to llama.cpp, installed via Homebrew. The working server command has six load-bearing flags:
llama-server \
 -m /path/to/gemma-4-26B-A4B-it-Q4_K_M.gguf \
 --port 1234 -ngl 99 -c 32768 -np 1 --jinja \
 -ctk q8_0 -ctv q8_0Every flag matters on 24 GB. The -np 1 limits to a single slot, because multiple slots multiply KV cache memory. The -ctk q8_0 -ctv q8_0 quantises the KV cache, reducing it from 940 MB to 499 MB. The --jinja flag is required for Gemma 4's tool-calling template. And -m with a direct path avoids the -hf flag, which silently downloads a 1.1 GB vision projector that causes an out-of-memory crash.
The Codex CLI config also needed web_search = "disabled", because Codex CLI sends a web_search_preview tool type that llama.cpp rejects. None of this is documented anywhere obvious. I found it by reading error messages, GitHub issues and trying things.
The GB10. I expected vLLM to work, as the plan I was following recommended it. It did not. vLLM 0.19.0’s compiled extensions are built against PyTorch 2.10.0, but the only CUDA-enabled PyTorch for aarch64 Blackwell (compute capability sm_121) is 2.11.0+cu128. Different ABI. ImportError at startup. I built llama.cpp from source with CUDA, and it compiled and benchmarked fine, but Codex CLI's wire_api = "responses" sends non-function tool types that llama.cpp rejects.
What worked was Ollama v0.20.5. The streaming bug that breaks Apple Silicon does not reproduce on NVIDIA. ollama pull gemma4:31b, SSH tunnel to forward port 11434 to my Mac (because Codex CLI's --oss mode checks only localhost), and codex --oss -m gemma4:31b. Text generation and tool calling both worked on the first attempt.
The honest summary: the Mac setup took most of an afternoon. The GB10 took about an hour, most of it waiting for model downloads.

## The benchmark
I gave all three configurations the same task through codex exec --full-auto: write a parse_csv_summary Python function with error handling, write tests and run them.
GPT-5.4 produced type-hinted code with proper exception chaining, boolean type detection and a clean helper function. Zero dead code. Five tests passed first time. Sixty-five seconds.
The GB10’s 31B Dense produced clean, functional code without type hints or boolean detection, but with solid error handling and no dead code. Five tests, first attempt, three tool calls. Seven minutes.
The Mac’s 26B MoE left dead code in the implementation, a type inference loop written, abandoned in place, then rewritten below it with the comment ‘Actually, let’s simplify’ still in the source. The test file took five attempts to write. Each time the model introduced new syntax errors through shell heredoc quoting: filerypt instead of file_path, encoding=' 'utf-8' with a rogue space, fileint(file_path). Ten tool calls to accomplish what the GB10 did in three.

## The speed numbers, and why the Mac is faster than expected
I ran llama-bench on both machines with the same context lengths.
The Mac generates tokens 5.1 times faster than the GB10. That surprised me, because both machines have 273 GB/s LPDDR5X memory bandwidth.
The explanation is the Mixture of Experts architecture. Token generation is memory-bandwidth limited: every token requires reading the model’s active parameters from memory. The 31B Dense reads all 31.2 billion parameters for every token. The 26B MoE activates only 3.8 billion per token, roughly 1.9 GB at Q4 quantisation. The Mac pushes 1.9 GB per token through its 273 GB/s bandwidth and gets 52 tok/s. The GB10 pushes 17.4 GB per token through the same bandwidth and gets 10 tok/s. Same pipe, vastly different payload.
Prompt processing was the other surprise. I expected the GB10’s Blackwell GPU to dominate, but the Mac held its own: 531 tok/s versus 548 tok/s at 8K context. The MoE’s sparse activation benefits prompt processing too, not only generation.

## What I learned
The finding I did not expect: model quality matters more than token speed for agentic coding.
The Mac generated tokens 5.1 times faster. It still finished only 30 per cent sooner (4m 42s versus 6m 59s). The speed advantage was consumed by retries, ten tool calls instead of three, five failed test writes and dead code the model did not clean up. The GB10’s slower model got it right the first time.
The cloud model proved this most starkly. Fastest time, fewest tokens, best quality. Five out of five in 65 seconds. A model that gets it right the first time beats one that iterates faster but needs more iterations.
But local is viable. Both machines produced working code with passing tests. The quality gap between Gemma 3 (6.6 per cent tool calling) and Gemma 4 (86.4 per cent) is the gap that matters. Going from ‘broken’ to ‘works’ is the step that makes local agentic coding practical.
For my own workflow, I have landed on a hybrid. codex --profile local for iteration and privacy-sensitive work. Default cloud for anything complex. Codex CLI's profile system makes switching a single flag.

## If you are going to try this
A few specifics from the setup that will save you time.
On Apple Silicon, skip Ollama for Gemma 4 entirely. Use llama.cpp with --jinja. Set web_search = "disabled" in your Codex CLI profile. Use -m with a direct GGUF path, not -hf. Set context to 32,768 (Codex CLI's system prompt needs at least 27,000 tokens) and quantise the KV cache with -ctk q8_0 -ctv q8_0.
On NVIDIA, Ollama v0.20.5 works. Use codex --oss -m gemma4:31b. If the machine is remote, tunnel port 11434 via SSH.
Set stream_idle_timeout_ms to at least 1,800,000 in your provider config. A single tool-call cycle took one minute 39 seconds on the Mac. The default timeout will kill your session before the model finishes thinking.
And pin your llama.cpp version. A reported 3.3 times speed regression between builds means your benchmarks can change overnight.
Benchmarks were run on 12 April 2026 using Codex CLI v0.120.0. Mac: llama.cpp ggml 0.9.11 (build 8680) on a 24 GB M4 Pro MacBook Pro, model gemma-4–26B-A4B-it Q4_K_M. GB10: Ollama v0.20.5 on a Dell Pro Max GB10 (128 GB, NVIDIA Blackwell), model gemma-4–31B-it Q4_K_M. Cloud baseline: GPT-5.4 with high reasoning effort. All three ran the same prompt through codex exec --full-auto. Raw speed benchmarks used llama-bench.

