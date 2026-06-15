---
name: frontend-slides
description: Use when the user wants to create, scaffold, edit, or present a web-based slide deck or presentation (e.g. reveal.js, Slidev, Spectacle, or plain HTML/CSS/JS slides), or to turn an outline / markdown notes into slides.
---

# Frontend Slides

Help the user turn an outline, markdown notes, or topic into a polished, web-based
slide deck, or extend/restyle an existing one.

## Workflow

1. **Clarify scope before building**
   - What is the deck for (talk length, audience, tone)?
   - Is there an existing project to extend, or a new one to scaffold?
   - Any framework preference? If none given, pick based on the project's stack:
     - Plain static site / no build tooling → **reveal.js** (single HTML file + CDN or local assets)
     - Vue/markdown-first workflow → **Slidev**
     - React project → **Spectacle** or **MDX Deck**

2. **Scaffold the project** (new decks only)
   - Create a minimal, runnable project with one file per slide's content kept in a
     single markdown/JS source where the framework supports it (Slidev, reveal.js
     markdown plugin) rather than hand-writing dozens of near-identical HTML blocks.
   - Add a `package.json` with a dev script so the user can preview locally
     (`npm run dev` / equivalent).

3. **Structure the content**
   - One idea per slide. Prefer short bullet points, headings, and code blocks over
     dense paragraphs.
   - Use a title slide, section dividers for long decks, and a closing/summary slide.
   - For code-heavy talks, use the framework's syntax-highlighted code blocks and
     keep snippets short enough to read at presentation size.
   - Add speaker notes (reveal.js `<aside class="notes">`, Slidev `<!--` comments)
     for any context that shouldn't appear on-screen.

4. **Styling**
   - Keep a consistent theme; prefer the framework's built-in themes over custom CSS
     unless the user has specific branding requirements.
   - Check contrast and font sizes are presentation-readable (large fonts, minimal
     text per slide).

5. **Preview before finishing**
   - Start the dev server and confirm the deck renders, navigation works, and any
     code/diagrams display correctly. Report the local URL to the user.

## Conventions

- Don't hand-roll a slide framework from scratch unless the user explicitly asks for
  plain HTML/CSS/JS with no dependencies — reuse an established library.
- Keep each slide's source self-contained and easy to reorder.
- When editing an existing deck, match its existing framework, theme, and file
  layout rather than introducing a new one.
