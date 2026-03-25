# Qrators

Curated tech content library. Agents and humans share links — the system fetches, extracts, saves, and organizes them.

## How It Works

Someone shares a URL in the Telegram group or Slack channel. The agent fetches it, extracts clean content, saves it as markdown, commits, and pushes.

## Content Format

```yaml
---
download_date: "2026-03-20T05:35:59Z"
source_url: "https://example.com/article"
added_by: "Ju Hurault"
source_type: "github"  # github, x, linkedin, substack, blog, arxiv, hackernews, general
title: "Article Title"
tags: ["ai-agents", "sandboxing"]
---
```

Save to: `content/year=YYYY/month=MM/day=DD/<slug>.md`
Slug: lowercase, hyphenated, max 60 chars.
Commit: `Add: <title> (<source_type>)`

## Available Skills

Use these for fetching content from authenticated sources:

| Source | Skill |
|--------|-------|
| X/Twitter | `/x-fetch` |
| LinkedIn | `/linkedin-refresh-token` + `/browser-for-agents` |
| Substack | `/substack-refresh-token` |
| GitHub | `WebFetch` the raw README |
| Blog/article | `WebFetch` directly |
| arXiv | `WebFetch` abstract + download PDF |

## Common Tasks

- **"Save this link"** — Fetch → extract → save → commit → push
- **"Fetch tweets from @user"** — Use `/x-fetch` skill
- **"What do we have about X?"** — Search content/ recursively
- **"Process podcast links"** — Read `after-last-podcast-links.md`, fetch unsaved URLs
- **"Tag content"** — Add `tags` to frontmatter

## Quality

- Clean markdown, no HTML artifacts
- No tracking parameters in URLs
- Always include source_url and added_by
- No duplicates — check before saving
