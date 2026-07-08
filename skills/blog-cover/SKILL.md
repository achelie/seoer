---
name: blog-cover
description: Generate polished pastel SaaS and SEO blog cover images, especially Gumloop-inspired editorial covers for AI tools, SaaS alternatives, pricing, comparison, migration, developer workflow, customer support, SEO, meeting notes, voice, avatar, and project-management articles. Use when the user asks for a blog/article cover, Open Graph image, Gumloop-style image, or non-repetitive generated cover.
---

# Blog Cover

Create production-ready raster blog covers. The default target is a 1200x630 Open Graph image with pastel gradient mesh, dotted halftone texture, floating UI cards, app/workflow nodes, and clean SaaS editorial composition.

This skill is a public, renamed version of the user's local `gumloop-blog-cover` skill. Use `$blog-cover` as the public skill name.

## Visual Language

Use this baseline style unless the user gives stronger project rules:

- Pastel macaron gradient mesh: pink, coral, peach, yellow, lavender, mint, or sky blue.
- Fine dotted halftone texture across the full background.
- Rounded white UI cards with soft shadows, glass highlights, pills, and connector lines.
- Small favicon-style app nodes when relevant, kept secondary and not copied as full product UI.
- One clear decision motif: savings, workflow route, migration checklist, usage meter, support queue, code flow, voice stack, or SEO report packet.
- Clean, playful, modern SaaS editorial feel with generous empty space.

Avoid:

- Real third-party logos unless the user explicitly permits them.
- Trademarked product UI copied from screenshots.
- Dark heavy palettes, generic purple-only gradients, stock photos, people, watermarks.
- Long titles or tiny paragraphs inside the image.
- Reusing the same card positions, connector path, and label row from the previous cover.

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
Primary request: Create a pastel editorial SaaS cover image for an article titled "<title>".

Scene/backdrop:
A soft pastel gradient mesh with subtle dotted halftone texture across the full canvas.

Subject:
Visualize <topic> using abstract SaaS UI elements, small app/workflow nodes, rounded cards, connector lines, and short labels.

Composition/framing:
Landscape 1200:630 ratio. Choose <composition family>. Keep generous empty space. Avoid the last cover's structure.

Style/medium:
Polished 2D/3D hybrid SaaS blog illustration, soft shadows, crisp iconography, playful but clean.

Text (verbatim):
"<short exact text>"

Constraints:
No real company logos, no copied product UI, no watermarks, no photorealistic people, no tiny paragraphs. Text must be legible at social-card size.
```

## Checks

- Final image matches requested dimensions or is intentionally resized.
- Generated text is readable enough.
- Output file is inside the project if the page references it.
- Cover renders without stretching or layout shift.
- The composition differs from recent covers.
