# Markdown to HTML Converter (Bootstrap + Marked + Highlight.js)

A production-ready, single-page web application that decodes an embedded markdown data URI, converts it to HTML using marked.js, and applies code syntax highlighting via highlight.js. The UI is built with Bootstrap 5. The app is entirely client-side and works seamlessly on GitHub Pages.

## Features
- Decodes and renders markdown from an embedded data URI (no backend required)
- Uses marked.js for fast, standards-compliant markdown parsing
- Applies syntax highlighting to code blocks with highlight.js (common languages)
- Clean, responsive Bootstrap 5 UI with action buttons
- Copy rendered HTML to clipboard
- Robust error handling and accessibility-friendly alerts
- Security-conscious rendering with DOMPurify (sanitization)

## Setup / Deployment
This is a static web app. You can run it in two ways:

1. Local:
   - Download or clone the repository
   - Open `index.html` in any modern web browser (Chrome, Firefox, Edge, Safari)

2. GitHub Pages:
   - The repository includes GitHub Pages configuration (no extra setup needed)
   - Visit the GitHub Pages URL provided after deployment

## Usage Guide
- The application automatically renders the embedded `input.md` data URI on page load.
- Click "Re-render" to re-process the markdown, if needed.
- Click "Copy HTML" to copy the current rendered HTML content to your clipboard.
- The original data URI is displayed in the "Source: Embedded data URI" panel for reference.

## Technical Overview
- Libraries:
  - Bootstrap 5 (CSS/JS via CDN)
  - marked.js (Markdown parser via CDN)
  - highlight.js (Syntax highlighting via CDN)
  - DOMPurify (Optional sanitization via CDN)
- Structure:
  - Single file: `index.html` contains inline CSS and JavaScript
  - No external build tools or servers required
- Data Handling:
  - The provided markdown is embedded as a constant JavaScript string containing a `data:text/markdown;base64,...` URI
  - The base64 content is decoded in the browser using `atob` + `TextDecoder`
  - The decoded string is passed to `marked.parse()`
  - The resulting HTML is sanitized (if DOMPurify is loaded) and injected into `#markdown-output`
  - highlight.js scans `pre code` blocks inside `#markdown-output` and applies syntax highlighting

## Project Structure
- `index.html`: Main single-page application with Bootstrap layout, inline CSS, and all logic.
- `README.md`: Documentation and usage instructions.
- `.gitignore`: Standard web project ignore patterns.

## License
This project is licensed under the MIT License. You are free to use, modify, and distribute this software with attribution.
