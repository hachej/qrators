---
download_date: "2026-04-13T05:37:45Z"
source_url: "https://x.com/Axel_bitblaze69/status/2040312495886241836"
added_by: "Julien Hurault"
source_type: "x"
title: "AutoAgent just went open source"
tags: ["ai-agents", "agent-optimization", "benchmarking", "open-source"]
---

# AutoAgent just went open source

Author: Axel Bitblaze (@Axel_bitblaze69)  
Posted: 2026-04-04T06:16:20Z

Something for your to do list this weekend:

Clone one repo. Write one markdown file.. you'll have an agent that outperforms what research teams hand build.

Here's the repo:

Your AI agents are about to upgrade themselves..

AutoAgent just went open source and this changes everything about how you build with AI..

Let me explain.

rn when you build an AI agent whether in Claude Code, Cursor, or anything else.. you're manually writing prompts, picking tools, tweaking configs, testing, failing, rewriting.

That entire loop is what AutoAgent automates it.

Here's how it works in simple terms:

> You write a markdown file describing what you want your agent to do
> A "meta-agent" reads your instructions and rewrites the entire agent setup for you
> It tests the new version against real benchmarks
> Keeps changes that improved performance
> Throws away what didn't work
> Repeats. All night. Autonomously.

You go to sleep with a mid agent. You wake up with a top 1% agent.

And fyi AutoAgent already hit:

#1 on SpreadSheetBench (96.5%)
#1 on TerminalBench with GPT-5 score (55.1%)

How would this help you:

If you're building AI workflows, automations, coding agents you no longer need to spend hours fine-tuning prompts and tools manually.

You describe the outcome you want, AutoAgent engineers the path to get there.

This is AutoML but for agents. And it's free.

How to set it up:

> Clone it: `git clone https://github.com/kevinrgu/autoagent`
> Install: `uv sync`
> Write your `program.md` in plain English instructions for what your agent should do
> Add benchmark tasks in `tasks/` so it knows what "good" looks like
> Run it overnight

It handles the rest.. rewrites your prompts, tools, routing, config all inside Docker so nothing breaks.

Bookmark this one.

Related link:

- GitHub: https://github.com/kevinrgu/autoagent
