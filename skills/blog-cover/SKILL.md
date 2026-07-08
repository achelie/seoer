---
name: blog-cover
description: Generate polished Mac-style pastel SaaS and SEO blog cover images for AI tools, SaaS alternatives, pricing, comparison, migration, developer workflow, customer support, SEO, meeting notes, voice, avatar, and project-management articles. Use when the user asks for a blog/article cover, Open Graph image, Mac-style pastel SaaS image, official favicon-style nodes, or non-repetitive generated cover.
---

# Blog Cover

Create production-ready raster blog covers. The default target is a 1200x630 Open Graph image with a Mac-style pastel SaaS look: soft gradient mesh, dotted halftone texture, floating white glass cards, real official favicon-style nodes, bold decision cards, dotted arrows, and clean editorial composition.

Use `$blog-cover` as the public skill name.

## Visual Language

Use this baseline style unless the user gives stronger project rules:

- Mac-style pastel gradient mesh: pink, coral, peach, warm yellow, pale purple, mint, and sky blue blended softly.
- Fine dotted halftone texture across the full background.
- Large rounded white or off-white glass cards with soft shadows, subtle bevels, and clear hierarchy.
- Bold readable headline or metric cards, such as price, savings, limit, rank, or status. Only use exact numbers the article verified.
- Real official favicon-style brand nodes are allowed when relevant. Keep them small, contextual, and secondary. Do not recreate full logos as the main subject.
- Dotted arrows, dashed connector routes, pill labels, and small circular utility icons.
- A small abstract black agent/blob mark is allowed when it supports the composition, but it must stay secondary.
- Clean, playful, modern Mac-like SaaS editorial feel with generous empty space.

Avoid:

- Large third-party logos as the hero subject. Small official favicon-style nodes are allowed.
- Trademarked product UI copied from screenshots.
- Dark heavy palettes, generic purple-only gradients, stock photos, people, watermarks.
- Long titles or tiny paragraphs inside the image.
- Reusing the same card positions, connector path, and label row from the previous cover.

## Style Lock

Keep future outputs close to the reference quality bar:

- Rounded 1200x630 social-card composition with a soft pink-orange-blue pastel background.
- Smooth Mac-like glass cards, large corner radius, soft drop shadow, and crisp black or green/red typography.
- One dominant decision panel on each side or a strong diagonal/cascade decision path.
- Clear labels that remain readable at social-card size.
- Official favicon-style nodes can appear in small rounded squares or circular badges.
- Dotted connector arrows and small icon pills should guide the eye without making the image busy.

Do not treat every skill update as permission to change the art direction. Improve prompt specificity, topic motifs, or composition variety while preserving this Mac-style pastel SaaS baseline.

## Similarity Guard

Before generating, inspect recent covers in the project or user-provided references. Choose a composition that is visibly different from the most recent cover.

Rotate among:

- Orbit map
- Desk scene
- Cascade stack
- Split tension
- Radial burst
- Timeline strip
- Workflow route
- Tool shelf
- Report packet

If the previous cover used left-card/right-card/bottom-pill-row, explicitly forbid that layout in the next prompt.

## Topic Motifs

- AI tool alternatives: migration route, tool shelf, owned stack, decision checklist.
- Pricing and limits: usage meter, receipt, spend-cap, plan ladder, token chips. Never invent prices or limits.
- Coding tools: editor panes, terminal cards, safe permission gates, diff snippets, tests, branch lanes.
- Meeting notes: private notebook, bot outside a meeting room, calendar/audio separation, shield motif.
- Voice and TTS: waveform ring, voiceprint ribbons, microphone nodes, local server chips, open-source module blocks.
- Avatar/video/dubbing: filmstrip, storyboard ribbon, subtitles, language chips, render/server cubes.
- SEO tools: SERP grid, rank tracker, content brief, crawl map, report packets, keyword map.
- Help desk/CX: ticket queue, shared inbox, agent seats, SLA tabs, add-on notes.
- Project management: command center, seat counter, integration orbit, automation trigger paths.

## Workflow

1. Gather topic, title, slug, size, style references, banned colors, and recent-cover constraints.
2. Save the final prompt in a project-local prompt file when the project already tracks cover prompts.
3. Use a raster image backend. Prefer the built-in image generation tool when available.
4. Inspect the result for readable text, matching style, no copied logos, and no obvious artifacts.
5. Resize or crop only for dimensions and framing. Do not paint over generated text.
6. Save the selected asset into the project path the page will reference, usually `public/blog/<slug>/cover.png`.
7. Report the final image path, generation backend, and prompt path.

## Prompt Template

```text
Use case: ads-marketing
Asset type: 1200x630 blog article cover
Primary request: Create a Mac-style pastel SaaS cover image for an article titled "<title>".

Scene/backdrop:
A soft pink-orange-blue pastel gradient mesh with subtle dotted halftone texture across the full canvas.

Subject:
Visualize <topic> using large rounded white glass cards, bold decision metrics, dotted connector arrows, official favicon-style nodes where relevant, small workflow pills, and short labels.

Composition/framing:
Landscape 1200:630 ratio. Choose <composition family>. Keep generous empty space. Avoid the last cover's structure.

Style/medium:
Mac-style polished 2D/3D hybrid SaaS blog illustration, soft shadows, crisp iconography, playful but clean.

Text (verbatim):
"<short exact text>"

Constraints:
Small official favicon-style brand nodes are allowed. No large brand logos as the hero subject, no copied product UI, no watermarks, no photorealistic people, no tiny paragraphs. Text must be legible at social-card size.
```

## Checks

- Final image matches requested dimensions or is intentionally resized.
- Generated text is readable enough.
- Output file is inside the project if the page references it.
- Cover renders without stretching or layout shift.
- The composition differs from recent covers.
