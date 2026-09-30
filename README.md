# SEO skills

These are the skills I give my coding agents when I want them to do SEO. They
figure out what a site is and who it competes with, pull the analytics, decide
what to write, and then write it in a voice that doesn't sound like AI.

They work with Claude Code and Codex, and with any other agent that reads
`SKILL.md` files.

> **This is a snapshot.** I copied these out of my working setup on
> September 29, 2026 and I won't keep this repo updated. Fork it and make it
> yours.

## Install

```bash
git clone https://github.com/parsakhaz/seo-skills.git

# Claude Code
cp -R seo-skills/skills/* ~/.claude/skills/

# Codex
cp -R seo-skills/skills/* ~/.codex/skills/
```

Then open your agent inside your website's repo and ask for what you want. For
example, "set up SEO for this site" or "what should we write next".

## How they fit together

```
seo-foundations  →  seo-briefing  →  seo-content-strategy  →  seo-content-drafting
   (once)             (weekly)          (you approve it)          (writes the pages)
```

1. **`seo-foundations`**: Run this once on a new site. It reads your site,
   finds your real competitors, maps what people search for, and writes
   `.seo/foundations.md`. Every other skill reads that file.
2. **`seo-briefing`**: Your SEO morning report. It pulls traffic, Search
   Console and keyword data, then tells you what's working, what's broken and
   what to do next.
3. **`seo-content-strategy`**: Turns the briefing into a ranked to-do list:
   quick title fixes, pages to rewrite, and new pages to create. You approve it
   before anything gets written.
4. **`seo-content-drafting`**: Writes the blog posts, landing pages and
   comparison pages from the approved plan, then submits the new URLs for
   indexing.

The agent keeps everything in a `.seo/` folder in your repo, so each run can
see what changed since the last one.

## Other skills

| Skill | Use it when |
|-------|-------------|
| `seo-readability-pass` | Your copy sounds too technical and a newcomer wouldn't follow it |
| `seo-authority-pass` | You want explainer pages, a glossary, author bylines and structured data so Google trusts the site |
| `seo-from-calls` | You have sales call transcripts and want pages that answer what buyers asked |
| `seo-writing-framework` | You're writing anything a customer reads. The other writing skills use it too |
| `good-writing-fundamentals` | You have a draft and want the AI-sounding phrases cut out |
| `seo-data-pull` | Runs automatically. Pulls data from whatever analytics tools you've connected |
| `seo-data-organize` | Runs automatically. Archives `.seo/` so you can compare weeks over time |

## What you'll want connected

The skills use whatever your agent can reach, and they tell you what's missing
instead of making up numbers. They get better with:

- **Analytics**: PostHog, GA4, Plausible or similar
- **Google Search Console**: what you rank for and how often people click
- **Ahrefs or Semrush**: keywords, backlinks and competitor gaps

You can start with none of these. `seo-foundations` only needs your website.

## Tips

- A few skills say "Run with Claude Opus 4.6" because that model wrote the best
  copy when I made them. Use whatever model you like best.
- Put a short voice guide in your `AGENTS.md` or `CLAUDE.md` with how you
  talk, words you never use, and one page you love. `seo-readability-pass`
  writes one for you if you don't have it.

## Credits

`good-writing-fundamentals` is adapted from Peter Yang's
[no-ai-slop](https://github.com/petergyang/no-ai-slop) under the MIT license.
Its `LICENSE` file is in the skill folder.
