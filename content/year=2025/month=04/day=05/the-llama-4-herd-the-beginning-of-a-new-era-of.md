---
download_date: "2026-04-08T17:11:06Z"
source_url: "https://ai.meta.com/blog/llama-4-multimodal-intelligence/"
added_by: "Christophe"
source_type: "blog"
title: "The Llama 4 herd: The beginning of a new era of natively multimodal AI innovation"
tags: ["ai", "llama", "meta", "multimodal", "open-models"]
---

# The Llama 4 herd: The beginning of a new era of natively multimodal AI innovation

**Publication Date:** April 5, 2025

Meta introduced the Llama 4 family as its next major open-weight model release, centered on natively multimodal models and a mixture-of-experts architecture. The announcement covers three models: Llama 4 Scout, Llama 4 Maverick, and Llama 4 Behemoth.

## What Meta announced

- **Llama 4 Scout**: a 17B-active-parameter model trained with 16 experts, positioned as the efficient model in the lineup.
- **Llama 4 Maverick**: a 17B-active-parameter model trained with 128 experts, aimed at higher capability while still remaining deployable on a single H100 host.
- **Llama 4 Behemoth**: Meta's larger teacher model, described as still in training and not yet released.

Meta presents Scout and Maverick as its first open-weight, natively multimodal models with very long context support, and its first Llama models built with a mixture-of-experts design.

## Claimed capabilities

- Scout fits on a single H100 GPU with Int4 quantization.
- Maverick fits on a single H100 host.
- Behemoth is described as outperforming GPT-4.5, Claude Sonnet 3.7, and Gemini 2.0 Pro on STEM-oriented benchmarks including MATH-500 and GPQA Diamond.
- Scout and Maverick were made available via `llama.com` and Hugging Face, with Meta AI integrations rolling out across WhatsApp, Messenger, Instagram Direct, and Meta AI.

## Why it matters

This post frames Llama 4 as Meta's attempt to push the open model ecosystem forward on three fronts at once:

- multimodal input from the start rather than bolt-on tooling
- larger effective capacity through MoE routing
- longer context windows without moving to impractically large deployment footprints

Meta also uses the announcement to reinforce its long-running argument that open releases accelerate developer adoption and ecosystem growth.

## Notes

The original `ai.meta.com` article was not directly readable from this environment, but its title and metadata matched a public Meta newsroom mirror used to recover the announcement text.
