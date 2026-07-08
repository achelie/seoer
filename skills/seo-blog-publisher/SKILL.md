---
name: seo-blog-publisher
description: Create, rewrite, and publish SEO blog articles for tool, SaaS, AI alternatives, pricing, comparison, and migration topics. Use when the user asks for long-tail keywords, official screenshots, unique article images, blog covers, Reddit or customer-research sections, copy editing, humanized writing, JSON-LD, sitemap updates, GSC-friendly pages, or deployment after publishing a blog post.
---

# SEO Blog Publisher

Use this skill to take a blog topic from keyword intent to production-ready page. It is optimized for independent SEO sites where article quality, crawlability, images, and deployment all matter.

## Workflow

1. Understand search intent.
   - Extract primary keyword, secondary keywords, audience, and article format from the request.
   - If the user gives no title, create a click-worthy title that still matches the keyword.
   - Avoid ambiguous terms by adding the product, category, or use case to title and slug.
2. Research current facts.
   - Use official product pages, docs, pricing pages, GitHub repos, changelogs, and app pages first.
   - Use Reddit and community results as qualitative signals only. Label them as common complaints or user reports, not statistics.
   - Check licenses, free plan limits, commercial-use limits, and current product names before writing.
3. Plan images before drafting.
   - Every article image must be unique within the article.
   - Prefer official screenshots or product pages. If login is required, batch the login requests so the user can sign in once.
   - Use `$blog-cover` for generated Open Graph covers when a cover is requested.
4. Draft the article.
   - Write for the target reader, not for a generic SERP scraper.
   - Include practical sections such as best for, not for, migration cost, pricing traps, free plan limits, setup burden, data/privacy concerns, and how to choose.
   - Do not add "Quick answer" if the project or user forbids it.
   - Avoid fake exact numbers. Only include prices, usage limits, and license claims that were verified.
5. Humanize and edit.
   - Follow the project's `AGENTS.md` or local style guide.
   - Remove formulaic AI phrasing, empty claims, repeated transitions, and unsupported superlatives.
   - Respect local banned punctuation or wording rules.
6. Integrate with the site.
   - Add or update the article route, metadata, blog registry, related posts, sitemap, and tests according to local patterns.
   - Add Article, Breadcrumb, ItemList, or FAQ JSON-LD only when the project already uses structured data or the page warrants it.
   - Ensure title, date, excerpt, cover, alt text, and body content are crawlable in generated HTML.
7. Validate and release.
   - Run relevant lint, tests, build, and browser checks.
   - Use `$site-release-indexability-ops` when the user asks to commit, push, deploy, or verify production indexability.

## Article Requirements

- Match the requested long-tail terms naturally in title, intro, headings, body, alt text, and metadata.
- Put real decision support above generic tool summaries.
- State uncertainty clearly when community complaints or product behavior is not official.
- Keep affiliate-style claims out unless the project explicitly supports them.
- Do not reuse one image two or more times in the same article.
- Do not publish screenshots that expose private user data, account tokens, or non-public dashboards.

## Useful Checks

Before finishing, check:

- Word count meets the request.
- Required keywords appear naturally.
- No duplicate image paths inside the article.
- Cover file exists and renders at the expected size.
- Source links are current and relevant.
- Metadata and sitemap include the page.
- Related posts exclude the current article.
- Production page returns 200 after deployment when release is in scope.
