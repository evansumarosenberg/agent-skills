---
name: slidev-rapid-iteration
description: Edit Slidev decks through fast, user-guided iteration. Use when making focused changes to an established Slidev presentation, preserving the user's recent edits, working with layouts or Mermaid diagrams, and validating only when the user explicitly requests it.
---

# Slidev Rapid Iteration

Make one focused deck change at a time, then return control for the user's review. Treat the active Slidev deck and the user's latest manual edits as authoritative.

## Edit workflow

1. Locate the target slide and inspect its immediate neighbors before editing. Preserve the deck's section flow, layout conventions, and any manual edits made since the last task.
2. Make only the requested change. Do not rewrite adjacent slides, "improve" unrelated copy, or turn a slide request into broader deck cleanup.
3. Keep slide copy concise, direct, and presentation-ready. Prefer clear claims over boilerplate caveats; distinguish the user's own example or measurement from a general claim.
4. Avoid em dashes unless the user specifically asks for them.
5. Report what changed in one concise summary. Mention validation only when it was requested or was not run by request.

## Layout choices

- Respect the layout the user selected. Use `auto-default`, `auto-column`, `auto-image`, and `::auto::` only when they fit the requested content.
- Keep fixed titles outside `::auto::`; put only fit-managed content inside it.
- Do not use auto-column for dense side-by-side prose. Prefer the normal layout when the comparison needs more room.
- For Mermaid flowcharts, choose direction deliberately: use `flowchart LR` for compact horizontal process flows and `flowchart TD` only when vertical space is available. Node shape comes from Mermaid syntax; use rounded nodes for ordinary steps and diamonds for decisions when helpful.

## Validation

- Do not build, render, test, or browse the deck after ordinary edits unless the user explicitly asks for validation.
- When validation is requested, use the user's already-running Slidev dev server, normally at port 3030, and inspect it with the in-app browser when available. Do not start another dev server or run a build unless the user requests that specifically.
- Verify the requested concern only, such as overflow, centering, Mermaid rendering, or a specific slide's readability.

## Research and factual slides

- Research current or disputed claims before adding them. Use primary sources where available.
- Separate evidence gathering from slide editing when the user asks for a fact check first. Do not alter the deck until asked, unless the request clearly authorizes the edit.
- Keep citations off text slides when that is the deck's established convention; retain sources in the handoff instead.

## Collaboration style

- Treat the user as the deck's creative director. Their current manual changes take precedence over prior assistant choices.
- Ask a concise question only when placement, intended claim, or visual direction would materially change the slide. Otherwise make the best local edit and let the user iterate.
- For a requested new slide, place it at the named location. If no location is given, place it after the slide or concept being extended.
