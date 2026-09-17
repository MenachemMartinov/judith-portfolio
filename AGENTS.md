# Project Instructions

These instructions apply to the entire repository and to every AI agent working in it.

## Design authority

- Before creating, redesigning, or editing any page or visual component, read `STYLE_GUIDE.md` completely.
- Treat `STYLE_GUIDE.md` as the sole source of truth for visual design. It was derived exclusively from the pasted Lifestyle Session HTML reference.
- Do not infer design rules from the existing website pages. Existing pages are content sources and future restyling targets.
- When an existing page conflicts with `STYLE_GUIDE.md`, follow the guide unless the user explicitly requests an exception.

## Editing rules

- Preserve accurate page-specific copy, metadata, approved images, prices, package details, and destinations unless the task explicitly changes them.
- Never copy service-specific facts from the Lifestyle reference into another service page.
- Never invent business facts, prices, packages, availability, image URLs, or links.
- Keep pages in Hebrew and RTL unless the user explicitly requests another language or direction.
- Preserve the standalone HTML and Tailwind CDN architecture unless the user explicitly requests a migration.
- Do not add a navigation bar or another visual pattern that is absent from the guide unless explicitly requested.
- Preserve unrelated user changes and avoid editing files outside the requested scope.

## Completion checks

- Compare the result against `STYLE_GUIDE.md` before finishing.
- Verify narrow mobile and desktop layouts, RTL flow, links, image behavior, semantic structure, keyboard focus, and reduced-motion behavior.
- Report any missing source content or assets instead of filling the gap with invented material.
