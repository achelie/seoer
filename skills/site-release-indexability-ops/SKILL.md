---
name: site-release-indexability-ops
description: Release, deploy, and verify SEO-critical websites. Use when the user asks to commit, push, deploy to Vercel or Cloudflare, merge site branches, fix local-vs-production release drift, update ads.txt, favicon, sitemap, robots, noindex, canonical URLs, GSC/indexability issues, or confirm that newly published pages can be crawled and indexed.
---

# Site Release Indexability Ops

Use this skill for the final mile of SEO site work: clean Git scope, intentional commit, deployment, production verification, and indexability checks.

## Workflow

1. Inspect repository state before changing anything.
   - Run `git status -sb`.
   - Identify current branch, default branch, remote URL, and untracked files.
   - Never stage unrelated user files silently.
2. Confirm release scope from the request and the diff.
   - If the whole worktree belongs to the request, stage all relevant files.
   - If mixed changes exist, stage only explicit paths.
3. Run local validation before release.
   - Prefer project scripts in this order when present: lint, typecheck, test, build, design or production audit.
   - If a failure is caused by generated output that should not be linted, fix the project ignore/config or remove the generated output only when it is clearly disposable.
4. Commit and push.
   - Use a short, concrete commit message.
   - Push the current branch or the requested target branch.
   - For branch consolidation requests, fetch first and merge or rebase non-destructively. Do not use destructive reset or checkout unless explicitly requested.
5. Deploy from clean content.
   - If the working tree contains unrelated or untracked files, deploy from a clean worktree, git archive, or checkout at the intended commit.
   - Use the site's existing platform first. Vercel and Cloudflare are both acceptable when the project is configured for them.
6. Verify production.
   - Check deployment status is ready.
   - Fetch the production URL and changed URLs.
   - Verify HTTP 200, canonical URL, robots/noindex state, sitemap inclusion, favicon or ads.txt when relevant, and absence of obvious runtime errors.
   - For UI changes, use a real browser or screenshot check when available.
7. Report exactly what shipped.
   - Include commit hash, branch, production URL, validation commands, and any residual risk or manual wait step such as GSC recrawl timing.

## Indexability Checks

For pages that should be indexed, confirm:

- `robots.txt` does not block the path.
- Page HTML does not contain `noindex`.
- Canonical points to the intended production URL.
- The URL appears in sitemap when it is a stable public page.
- The server returns 200 without auth, redirect loops, or client-only blank content.
- Article pages expose crawlable title, description, date, body content, and structured data when the project already uses it.

For GSC work:

- Treat GSC as a live external system. Only perform irreversible actions when the user explicitly asks.
- If fixes are deployed but Google needs time, state what is fixed now and what must wait for recrawl.
- Do not claim indexing is complete unless GSC or a live Google result proves it.

## Deployment Notes

- Vercel: inspect deployment readiness, production alias, and recent error logs when the CLI or app tooling is available.
- Cloudflare: verify Pages or Workers project binding, build command, output directory, custom domain, and route status.
- Static sites: verify generated HTML and sitemap artifacts before deploy.

## Safety Rules

- Do not deploy from a dirty tree when unrelated files may be uploaded.
- Do not commit secrets, `.env`, local screenshots, temporary SRT files, or browser profiles.
- Do not force push unless the user explicitly asked and the risk is explained.
- Do not treat successful deployment as successful SEO. Deployment and indexability are separate checks.
