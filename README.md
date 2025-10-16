# README

## Overview
This static web page:
- Fetches the attached input.md file from the same directory.
- Converts the Markdown to HTML in the browser using Marked.
- Renders the HTML inside the element with id "markdown-output".
- Highlights fenced code blocks using Highlight.js (with a GitHub-like theme).
- Adds stable anchor links to headings for easy deep linking.

All logic runs client-side; no build step is required.

## Setup
Because the page fetches input.md via HTTP, serve the files from a local web server (opening via file:// may block fetch).

Options:
- Python 3: python -m http.server 8080
- Node (http-server): npx http-server -p 8080
- Bun: bunx serve .
- VS Code Live Server: Right-click index.html → "Open with Live Server"

Then open:
http://localhost:8080/

Ensure input.md is in the same directory as index.html.

## Usage
- Start a local server (see Setup).
- Open index.html through the server URL.
- The page automatically loads input.md, converts it to HTML using Marked, and displays it in the #markdown-output container. Code blocks are syntax highlighted by Highlight.js.
- To use your own Markdown: edit input.md and refresh the page. Caching is disabled for this fetch, so changes show on reload.

## Improvements from Previous Version (Round 2)
- Integrated Highlight.js directly through Marked’s highlight option for immediate, server-free syntax highlighting during render.
- Added a lightweight loading state and clear error handling to improve UX and debuggability.
- Included a polished, accessible base style and a GitHub-like code theme for better readability in both light and dark modes.
- Implemented automatic heading anchors so sections are linkable via URL hashes.
- Disabled request caching for input.md to ensure you always see the latest edits after refresh.