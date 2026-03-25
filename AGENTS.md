# Qrators

Curated tech content library. Agents and humans share links — the system fetches, extracts, saves, and organizes them for later reference, podcast prep, and newsletter research.

## What This Is

A shared knowledge base built by collecting and archiving articles, tweets, GitHub repos, and research papers. Content comes from:
- **Telegram group** (Qrators) — anyone shares a link, the bot saves it
- **Slack channel** (#qrators) — same workflow
- **Podcast prep** — links discussed or shared around episodes
- **Manual curation** — "save this for later"

## How It Works

### Saving Content

When someone shares a URL:
1. Fetch the page with `WebFetch`
2. Extract the main content (strip nav, ads, cookie banners, sidebars)
3. Convert to clean markdown
4. Save to `content/year=YYYY/month=MM/day=DD/<slug>.md`
5. Commit and push

### Frontmatter Format

Every article has YAML frontmatter:
```yaml
---
download_date: "2026-03-20T05:35:59Z"
source_url: "https://example.com/article"
added_by: "Ju Hurault"          # or whoever shared it
source_type: "github"            # github, x, linkedin, substack, blog, arxiv, hackernews, general
title: "Descriptive Article Title"
tags: ["ai-agents", "sandboxing"] # optional topic tags
---
```

### Slug Rules
- Lowercase, hyphenated
- Max 60 characters
- Descriptive (not just the domain)
- Examples: `rivet-dev-secure-exec.md`, `building-ai-agents-with-bash.md`

### Commit Messages
Format: `Add: <title> (<source_type>)`
Examples:
- `Add: rivet-dev/secure-exec (github)`
- `Add: Building AI agents with just bash (blog)`

## Directory Structure

```
content/
├── after-last-podcast-links.md       ← Links shared since last episode
└── year=YYYY/
    └── month=MM/
        └── day=DD/
            ├── article-slug.md       ← Archived article
            └── paper-name.pdf        ← Downloaded PDF
```

Hive-partitioned by date for easy browsing and querying.

## Available Tools & Skills

Qrators agents have access to skills from boring-master. Use these instead of raw WebFetch when applicable:

| Source | How to Fetch | Notes |
|--------|-------------|-------|
| **X/Twitter** | `python3 ~/projects/_archive/boring-coding/scripts/x_fetch_user_tweets.py <username>` | Uses stored session cookies. Fetches full timeline. |
| **X single tweet** | `python3 ~/projects/_archive/boring-coding/scripts/x_fetch_user_tweets.py <username> --url <tweet_url>` | |
| **LinkedIn** | Use `browser-use` with stored LinkedIn session | Session at `~/.browser-profiles/linkedin/` |
| **GitHub repos** | `WebFetch` the README raw URL | `https://raw.githubusercontent.com/<owner>/<repo>/main/README.md` |
| **Blog/article** | `WebFetch` directly | Strip HTML, extract main content |
| **Substack** | `WebFetch` the post URL | Usually clean markdown already |
| **arXiv** | `WebFetch` the abstract page + download PDF | Save PDF to `content/year/month/day/` |
| **HackerNews** | `WebFetch` the linked article, not the HN page | HN is just the discussion |

### Session Auth (pre-configured)
- **X cookies**: `~/.browser-profiles/x/auth.json` — refresh with `x_refresh_token.py --login`
- **LinkedIn cookies**: `~/.browser-profiles/linkedin/` — refresh via `/linkedin-refresh-token` skill
- **Substack cookies**: refreshed via `/substack-refresh-token` skill

## Common Tasks

### "Save this link"
1. Identify the source type (x, github, linkedin, blog, etc.)
2. Use the appropriate tool from the table above
3. Extract clean content → save → commit → push
4. Always confirm what was saved

### "Fetch tweets from @username"
```bash
python3 ~/projects/_archive/boring-coding/scripts/x_fetch_user_tweets.py <username> --dest content/year=YYYY/month=MM/day=DD/
```
Then commit and push each saved tweet.

### "What do we have about X?"
Search filenames and content recursively. Report: title, date, source_url, and a one-line summary.

### "Summarize recent additions"
List articles added in the last N days with titles and sources.

### "Process podcast links"
Read `content/after-last-podcast-links.md`, fetch each URL that hasn't been saved yet, save them, update the cutoff date.

### "Tag/categorize content"
Add or update `tags` in frontmatter. Common tags: `ai-agents`, `data-engineering`, `llm`, `devtools`, `career`, `business`, `open-source`, `security`, `infrastructure`.

## Quality Standards

- **Clean markdown** — no HTML artifacts, no tracking parameters in URLs
- **Readable** — the saved version should be useful without visiting the original
- **Attributed** — always include source_url and added_by
- **No duplicates** — check if the URL already exists before saving

## Git Workflow

Always commit and push after changes:
```bash
git add content/
git commit -m "Add: <title> (<source_type>)"
git push origin main
```
