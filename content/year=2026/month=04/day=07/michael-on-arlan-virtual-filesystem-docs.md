---
download_date: "2026-04-07T10:41:07Z"
source_url: "https://x.com/michael_chomsky/status/2041217735968063519"
added_by: "Julien Hurault"
source_type: "x"
title: "Michael on Arlan's virtual filesystem docs idea"
tags: ["ai-agents", "context-engineering", "filesystem", "documentation"]
---
# Michael (@michael_chomsky)

Arlan is actually a genius.

He basically turned every piece of documentation into a virtual filesystem for agents to grep/cat/use bash commands on.

I've been thinking about doing something like this for months but he actually executed, and it's so damn good!

In hindsight this is obvious.

Why are we doing RAG on documentation? This is highly structured and carefully organized knowledge. RAG makes little sense on its own, especially with LLMs being RL'd into loving file operations.

Mintlify did something similar for their KB agent, but this is even more interesting imo, as it lets my local agent do the operations.

My local agent has the context of my current task, and Arlan made the agent 10x more powerful.

But we shouldn't stop here.

I want the same thing for any github repo (every github repo in a virtual filesystem, with just-bash allowing bash operations without cloning locally)

@davis7's btca is the closest thing I've seen to this, but I wonder if anyone else is working on something around taking some data source, turning it into a virtual filesystem, and giving it to agents?

Quoted post: Arlan (@arlanr), linking to the X article "Turning the entire web into a filesystem."
