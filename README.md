# ☀️ Morning Brief

A curated daily AI/tech digest, built with [Astro](https://astro.build). Designed for fast reading with a Substack × Medium editorial feel.

## Repo Structure

```
openclaw-posts/
├── src/
│   ├── content/
│   │   └── blog/           ← 📝 Blog posts go here (markdown)
│   │       ├── 2026-04-03.md
│   │       ├── 2026-04-04.md
│   │       └── 2026-04-05.md
│   ├── components/
│   │   └── ArticleCard.astro
│   ├── layouts/
│   │   └── BaseLayout.astro
│   ├── pages/
│   │   ├── index.astro      ← Homepage (lists all digests)
│   │   └── [slug].astro     ← Individual digest page
│   ├── styles/
│   │   └── global.css       ← Design system & tokens
│   └── content.config.ts    ← Content collection schema
├── astro.config.mjs
├── package.json
└── tsconfig.json
```

## Publishing a New Digest

Your AI agent should create a **single markdown file** at:

```
src/content/blog/YYYY-MM-DD.md
```

### Required Frontmatter

```yaml
---
title: "AI Digest: YYYY-MM-DD"
date: YYYY-MM-DD
description: "One-line summary of today's key signal."
tags: [ai, digest]
draft: false
---
```

### Required Body Structure

The markdown body must follow this exact section format. The parser in `[slug].astro` reads `##` as section headers and `###` as article cards.

```markdown
_Curated for: Technical AI PM | Conversational Commerce | Agentic Systems_

## 🧭 Executive TL;DR

- **Headline**: One-sentence insight. [Read more](#anchor-link)
- **Headline**: One-sentence insight. [Read more](#anchor-link)
- (5–7 bullets total)

## 🔴 Top Stories

### Article Title
**Source:** https://example.com/article | **Tags:** #Tag1 #Tag2
One paragraph summary of the article.
**Why it matters to you:** One sentence on relevance.

### Another Article Title
**Source:** https://example.com/other | **Tags:** #Tag3
Summary text.
**Why it matters to you:** Relevance.

## 🟡 Worth Knowing

### Article Title
**Source:** https://example.com | **Tags:** #Tag1
Summary.
**Why it matters to you:** Relevance.

## 🎬 Creator Digest

### Video Title
**Source:** https://youtube.com/watch?v=xxx | **Tags:** #YouTube #channel_name
Summary.
**Why it matters to you:** Relevance.
```

### Key Rules

| Rule | Detail |
|------|--------|
| **File location** | `src/content/blog/YYYY-MM-DD.md` |
| **Sections** | Use `## ` for section headers (TL;DR, Top Stories, Worth Knowing, Creator Digest) |
| **Articles** | Use `### ` for each article title within a section |
| **Source line** | Must start with `**Source:**` followed by the URL, then `\|` then `**Tags:**` with `#hashtags` |
| **Why line** | Must start with `**Why it matters to you:**` |
| **TL;DR** | Use standard markdown bullet list (`- **Bold**: text`) |
| **Top Stories** | 3 articles max — highest signal |
| **Worth Knowing** | 3 articles — important but secondary |
| **Creator Digest** | 3 videos — curated YouTube/podcast picks |

## Development

```bash
npm install        # Install dependencies
npm run dev        # Start dev server at localhost:4321
npm run build      # Build static site to dist/
```
