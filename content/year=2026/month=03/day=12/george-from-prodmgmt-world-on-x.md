---
download_date: "2026-03-12T19:35:46.590Z"
source_url: "https://x.com/nurijanian/status/2032124503330058696?s=20"
added_by: "Ju Hurault"
source_type: "x"
title: "George from 🕹prodmgmt.world on X"
---
# George from 🕹prodmgmt.world (@nurijanian)


If you're a PM who uses Claude Code/Cursor to build and execute research, strategy, and discovery work, this stack cuts context setup from 15 minutes of pasting to under a minute.

Obsidian solves the storage problem: every note you write becomes a local markdown file, yours permanently, readable by any tool, locked to no platform.

The second piece is qmd, a CLI tool built by Tobi Lütke (Shopify's CEO) specifically for searching markdown files, now at 14.5k GitHub stars.

It combines three search approaches running entirely on your machine: BM25 full-text retrieval, vector semantic search via a locally-running 300MB embedding model, and LLM re-ranking for final relevance scoring. No data leaves your laptop.

You point it at a folder, run `qmd embed` to index your entire collection.

What this means in practice: I can open Claude Code and ask it to find every decision I've made about a particular product area, or pull every research note that mentions a specific problem, without manually copying anything.

Claude runs the search, reads the relevant files, and starts from that context rather than from scratch. The time I used to spend pasting background into chat windows before each session now goes into the actual work.

What I didn't expect was how much it compounds. I'm not sure how to quantify it precisely, but every note I add increases the usefulness of future sessions without any extra effort on my part.

Setup to replicate this:

1. Install Obsidian and import all your notes from wherever you used to store them
2. Install QMD (https://github.com/tobi/qmd)

Works perfectly with http://prodmgmt.world of course
