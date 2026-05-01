# Hosting & Environment Configuration

## GitHub Pages Deployment
This project uses **GitHub Pages** to serve the static frontend which acts as a learning portal. 
The portal relies on:
- `index.html`: The main entry point featuring the unified menu and navigation grid.
- `markdown_renderer.html`: A dynamic page that parses and displays markdown files from the 7-stage folder structure.
- `menu.json`: The configuration file that drives the top navigation and content links.

## URL
The live site is published at:
[https://rifaterdemsahin.github.io/claude/](https://rifaterdemsahin.github.io/claude/)

## Setup Workflow
1. Push changes to the `main` branch.
2. In the GitHub repository settings, navigate to **Pages**.
3. Select **Deploy from a branch** and choose the `main` branch and `/` (root) directory.
4. GitHub Actions will automatically build and deploy the `index.html` and static files.

## Debugging Local Environment
If you are developing locally:
1. Run a local web server (e.g., `python3 -m http.server 8000`).
2. Navigate to `http://localhost:8000`.
3. Open the developer tools or click the "Toggle Debug" button to enable the "7 stages" debug view.

## Technologies Used
- HTML5, CSS3 (CSS Grid/Flexbox)
- JavaScript (Fetch API)
- **Marked.js**: For rendering markdown files.
- **Prism.js**: For syntax highlighting in code blocks.
- **Mermaid.js**: For rendering architecture diagrams dynamically.
