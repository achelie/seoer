---
name: srt-to-game-guide-publisher
description: Turn SRT subtitles, gameplay notes, screenshots, and guide asset folders into long-form SEO game guides. Use when the user provides an SRT file or a folder of guide materials and asks for a high-quality guide, all images used, cover image setup, publish dates, related guide navigation, FAQ or Article JSON-LD, sitemap updates, GitHub push, or Vercel/Cloudflare deployment.
---

# SRT To Game Guide Publisher

Use this skill to convert video subtitles and local game assets into an original, publishable guide. The goal is not transcription. The goal is a useful article that keeps the creator's useful details while becoming a crawlable, structured guide.

## Workflow

1. Inspect the material folder.
   - Locate `.srt`, cover images, screenshots, and any existing notes.
   - Identify which image should be the cover. If the user says every image must be used, track every image path before drafting.
2. Clean and analyze the SRT.
   - Remove timestamps, duplicate captions, repeated filler, and speech recognition artifacts.
   - Extract the main tips, entities, numbers, item names, character names, build names, tiers, and mistakes.
   - Correct obvious subtitle mishearings using in-project game data when available.
3. Build the guide outline.
   - Create a search-friendly title, slug, intro, table of contents, strategy sections, mistake section, and FAQ.
   - Use the SRT as the primary source but rewrite as original article prose.
   - Keep guide flow practical: what to do, when to do it, why it matters, what to avoid.
4. Place images deliberately.
   - Use all required images exactly once unless the user allows reuse.
   - Write useful alt text and captions tied to the section.
   - Do not publish private local path text in the article body.
5. Integrate with the site.
   - Follow existing guide storage patterns such as MDX content files, App Router pages, or data registries.
   - Add or update guide metadata: title, slug, description, cover, published date, updated date, reading time, and related guides.
   - Add Article and FAQ JSON-LD when supported by the project.
   - Ensure `/guides` sorting and sitemap behavior match the project's existing contract.
6. Validate and release.
   - Check word count and image coverage.
   - Run lint, typecheck, tests, and build when present.
   - Verify generated HTML contains guide content, dates, structured data, and sitemap entry.
   - Use `$site-release-indexability-ops` for commit, push, deploy, and production checks.

## Writing Rules

- Do not output a cleaned transcript as the final guide.
- Preserve concrete strategy details from the source video.
- Explain game terms in context when a new player may search for them.
- Avoid unsupported meta claims. If a ranking or patch claim matters, verify it against local data or current sources.
- Follow project `AGENTS.md` style rules, including banned phrases or punctuation.

## Completion Checks

- The guide uses the SRT as its main source.
- All required local images are referenced.
- The article is long enough for the user's requested threshold.
- The guide appears in site navigation/list pages.
- The sitemap includes the new URL.
- Related guide links do not include the current guide.
- Production URL works when deployment is in scope.
