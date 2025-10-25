<!--
  Generated: guidance for AI coding agents working in this workspace.
  Keep the file short (20-50 lines). Be specific to the project's patterns,
  file layout, and conventions discoverable in the repository.
-->
# Copilot instructions for this workspace

This repository contains small HTML/CSS practice projects and static pages (mostly under the `Form-Practice/`, `Forms/`, `images/`, and `Monday Form Assignment/` folders). The goal of this file is to help an AI agent make safe, high-value edits quickly.

Key facts
- Projects are plain static HTML pages with locally linked CSS files (no build system or package manifests present).
- Typical files to edit: `*.html` and their sibling `*.css` files (examples: `Forms/Form's-1.html`, `Forms/Form-1.html`, `Form-Practice/Form.html`).
- Images are stored in an `images/` directory or local image files next to pages (e.g., `IMG_2634.JPG` referenced in `Form's-1.html`).

What an agent should do first
- Preserve DOCTYPE, html lang, meta viewport and charset when editing pages.
- When modifying layout or styles, update only the specific CSS file that the HTML page links to (avoid creating global style files unless the user asks).
- If adding new assets (images, fonts), place them in an `images/` folder or next to the page and update relative paths.

Project-specific patterns and examples
- Inline component-like sections: pages use semantic sections (e.g., `<section id="projects">`, `<nav>`, `<aside class="card">`) and utility classes like `.card`, `.tag`, `.fadein` — keep class names consistent across edits.
- Small, self-contained JS snippets are used inline for UI polish (typing effect, intersection-observer animations) as in `Forms/Form's-1.html`. If adding JS, prefer embedding it at page bottom unless the user requests a separate `.js` file.
- Responsive adjustments are done with media queries inside the page's CSS. Follow the existing breakpoint values (980px, 560px) when adding responsive rules.

Safety and style
- Do not assume a build step (no bundlers or npm). Avoid adding package.json or node_modules unless requested.
- Keep changes minimal and reversible. Many files appear to be exercises — avoid large-scale refactors without explicit user approval.

Examples of safe edits
- Fix typos in text content, add missing alt attributes for images (`alt` present in `Form's-1.html` is correct), or adjust color tokens inside a linked CSS file.
- Add simple form validation using inline JS only when the page already contains an onsubmit handler (e.g., `id="contactForm"` in `Form's-1.html`).

When to ask the user
- If a change touches multiple pages or proposes reorganizing assets or introducing a build tool, confirm scope and desired structure first.
- If styles should be reused across multiple pages, ask whether to centralize them into a shared CSS file.

Files & locations to inspect when starting
- `Forms/Form's-1.html` — largest example with inline CSS, small JS, and image references.
- `Forms/Form-1.html`, `Form-Practice/Form.html` — smaller form pages that show table-based forms and linked CSS files.

If you make edits
- Run a quick visual check with a browser (user's environment) and report the files changed and why.

Ask for clarification when a change will affect multiple pages, when introducing new tooling, or when moving assets.
