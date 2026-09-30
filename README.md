# SEO skills

A snapshot of the Agent Skills I use for SEO work with Claude Code and Codex, taken September 29, 2026. It won't be updated.

## Install

Copy the folders in `skills/` into your agent's skills directory:

```bash
git clone https://github.com/parsakhaz/seo-skills.git
cp -R seo-skills/skills/* ~/.claude/skills/    # Claude Code
cp -R seo-skills/skills/* ~/.codex/skills/     # Codex
```

## The skills

Start with `seo-foundations` on a new site. It writes `.seo/foundations.md`, which the other skills read.

| Skill | What it does |
|-------|--------------|
| `seo-foundations` | Crawls your site, finds competitors, maps the search landscape |
| `seo-briefing` | Pulls analytics and search data into a prioritized briefing |
| `seo-content-strategy` | Turns the briefing into a ranked content plan |
| `seo-content-drafting` | Writes the blog posts, landing pages and comparison pages in the plan |
| `seo-readability-pass` | Rewrites existing copy so a first-time reader understands it |
| `seo-authority-pass` | Adds explainer pages, a glossary, author bylines, JSON-LD and OG images |
| `seo-from-calls` | Mines customer call transcripts for questions your site doesn't answer |
| `seo-writing-framework` | The research, draft, edit and score loop every writing skill follows |
| `good-writing-fundamentals` | The line-level edit pass that cuts AI-sounding prose |
| `seo-data-pull` | Support skill: pulls PostHog/GA4, Search Console and Ahrefs data into `.seo/data/` |
| `seo-data-organize` | Support skill: archives `.seo/` into a dated history |

The data skills use whatever analytics, Search Console and SEO tools your agent has connected, and note the gaps when a source is missing.

`good-writing-fundamentals` is adapted from [petergyang/no-ai-slop](https://github.com/petergyang/no-ai-slop) under the MIT license; see its `LICENSE` file.
