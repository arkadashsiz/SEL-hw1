# Portfolio

A clean, responsive one-page portfolio website built with **pure HTML, CSS, and JavaScript** — no frameworks, no build step, no dependencies.

## Features

- Responsive layout that adapts to small screens and mobile menus
- Dark theme by default with a **light/dark theme toggle** (persisted via `localStorage`)
- Accessible markup: semantic HTML, ARIA labels, keyboard support, reduced-motion support
- Smooth scrolling and a collapsible mobile navigation
- CSS custom properties (design tokens) for easy theming

## Getting started

The site is fully static. Simply open `index.html` in a browser, or run a local server:

```bash
npx serve .
# or
python -m http.server 8080
```

## Project structure

```
.
├── index.html                  # Single-page markup
├── style.css                   # Design tokens, dark/light themes, responsive rules
├── script.js                   # Theme toggle, mobile menu, dynamic year
├── README.md
└── .github/
    └── workflows/
        └── deploy.yml          # Auto-deploy to GitHub Pages on push to main
```

## Deploying to GitHub Pages

1. Push this repository to GitHub and enable **Pages → Source → GitHub Actions** in the repo settings.
2. The `.github/workflows/deploy.yml` workflow automatically builds and deploys the site whenever you push to the `main` branch (or a manual `workflow_dispatch` run).

The site will be available at `https://<username>.github.io/<repository>/`.

## Customization

- **Content**: Edit the headings, about text, cards, and skills list in `index.html`.
- **Colors and typography**: Adjust the CSS variables at the top of `style.css` (both `:root` and `[data-theme="light"]`).
- **Theme persistence key**: Change `STORAGE_KEY` in `script.js` if needed.

## License

MIT — free to use and modify.