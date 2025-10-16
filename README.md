# README

## Overview
This is a static web page that:
- Loads the attached input.md file.
- Converts the Markdown content to HTML in the browser using Marked.
- Renders the result inside the element with id "markdown-output".
- Applies syntax highlighting to code blocks using Highlight.js.

## Setup
Because the page fetches input.md via HTTP, you should serve the files with a local web server (opening index.html via the file:// protocol may block fetch).

Options:
- Python 3: python -m http.server 8080
- Node (http-server): npx http-server -p 8080
- Bun: bunx serve .
- VS Code Live Server: Right-click index.html → "Open with Live Server"

Then open http://localhost:8080/ in your browser.

Ensure input.md is in the same directory as index.html.

## Usage
- Start a local server (see Setup).
- Visit the served index.html in your browser.
- The page automatically fetches input.md, converts it to HTML using Marked, and displays it in the #markdown-output container with syntax highlighting provided by Highlight.js.

To use your own Markdown:
- Replace the contents of input.md with your text.
- Reload the page to see the updated rendering.