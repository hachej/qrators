# Qrators

Content curation repo. Collects links, articles, and resources shared in podcasts, social media, and communities.

## Structure

```
content/
├── after-last-podcast-links.md   ← Links shared since last podcast episode
└── year=YYYY/month=MM/day=DD/    ← Hive-partitioned daily content
    ├── article-slug.md           ← Downloaded article (markdown + frontmatter)
    └── document.pdf              ← Downloaded PDFs
```

## Content Format

Each article is a markdown file with YAML frontmatter:

```markdown
---
download_date: "2026-03-20T05:35:59Z"
source_url: "https://example.com/article"
added_by: "Ju Hurault"
source_type: "github"  # or: linkedin, x, substack, blog, arxiv, hackernews
title: "Article Title"
---

(article content in markdown)
```

## How to Add Content

When a user shares a URL or asks to save an article:

1. **Fetch the URL** using WebFetch
2. **Extract the main content** — strip navigation, ads, sidebars
3. **Convert to clean markdown**
4. **Save to** `content/year=YYYY/month=MM/day=DD/slug.md` where:
   - Date = today's date
   - Slug = lowercase, hyphenated title (max 60 chars)
5. **Add frontmatter** with download_date, source_url, added_by, source_type, title
6. **Commit and push** with message: `Add: <title>`

## How to Search Content

When asked "what do we have about X":
- Search content/ recursively for matching terms
- Check both filenames and file contents
- Report titles, dates, and source URLs

## After-Podcast Links

`content/after-last-podcast-links.md` tracks links shared after the latest podcast episode. When processing new links:
1. Fetch and save each link as a daily article
2. Update the links file with the new cutoff date

## Git Workflow

After adding content:
```bash
git add content/
git commit -m "Add: <title>"
git push origin main
```

Always commit and push after saving new content.
