# SEL-hw1 — Personal Portfolio

> A clean, responsive one-page portfolio website built with **pure HTML, CSS, and JavaScript** — no frameworks, no build step, no dependencies.

This repository contains the first homework for the **Software Engineering Lab** course at **SUT (2026 Summer)**. The goal was to implement a personal portfolio page with a focus on theming, clean code, and a proper Git workflow.

---

## Table of Contents

- [Features](#features)
- [Implementation Report](#implementation-report)
- [Branch Structure & Git Workflow](#branch-structure--git-workflow)
- [Commit History](#commit-history)
- [Getting Started](#getting-started)
- [Deployment (GitHub Pages)](#deployment-github-pages)
- [Live Demo (Frontend Launch)](#live-demo-frontend-launch)
- [Git Theory Questions](#git-theory-questions)
- [Customization](#customization)
- [License](#license)

---

## Features

- **Responsive Layout** — adapts seamlessly to small screens with a collapsible mobile menu.
- **Dark Theme by Default** — with a **light/dark theme toggle** button that persists user preference via `localStorage`.
- **Accessible Markup** — semantic HTML5 elements, ARIA labels, keyboard support, and reduced-motion support.
- **Smooth Scrolling** — for in-page navigation links.
- **CSS Custom Properties** — design tokens for easy theming and maintenance.

---

## Implementation Report

### Phase 1: Project Setup & Git Initialization

1. **Repository Creation:** Cloned the initial repository from `git@github.com:arkadashsiz/SEL-hw1.git`.
2. **Branching Strategy:** Adopted a feature-branch workflow to isolate development. Each new feature was developed in a separate branch and then merged into the `main` branch via Pull Requests.

### Phase 2: Dark Mode Implementation

- **Technology:** Used `data-theme` attribute on the `<html>` element.
- **JavaScript:** Added a `click` event listener to the `#themeToggle` button to toggle between `dark` and `light` values.
- **Persistence:** Integrated `localStorage` so the user's preference is remembered across sessions.
- **CSS Variables:** Defined color tokens in `:root` (dark) and `[data-theme="light"]` (light) for easy switching.

### Phase 3: Visual Improvements & Code Refinements

- **HTML Structure:** Removed duplicate sections (`#home`, `#about`) and ensured a logical hierarchy.
- **CSS Enhancements:** Applied consistent spacing, improved card styling, and made the mobile navigation functional.
- **Code Quality:** Removed redundant code and ensured the project structure aligns with the final version.

---

## Branch Structure & Git Workflow

The repository uses a **feature-branch workflow** to manage development. Below is a summary of all branches identified in the repository:

| Branch Name | Purpose | Status |
| :--- | :--- | :--- |
| `main` | Stable, production-ready branch. Deployed to GitHub Pages. | Active |
| `feature/dark-mode-button` | Implementation of the dark/light theme toggle and related JavaScript logic. | Merged |
| `feature/javascript` | Adding JavaScript features (mobile menu, dynamic year, etc.). | Merged |
| `fix_visual_box` | Hotfix branch for visual improvements (box-sizing, alignment, spacing). | Active |

**Workflow Steps:**

1. Created `feature/dark-mode-button` from `main`.
2. Developed the dark mode feature (HTML, CSS, JS).
3. Opened a **Pull Request (PR)** and merged it back into `main`.
4. Created `fix_visual_box` from `main` for post-merge visual refinements.
5. All changes are tracked with meaningful commit messages.

---

## Commit History

Below is a summary of the key commits made during this development cycle, based on the repository's history:

| Commit Message | Branch | Description |
| :--- | :--- | :--- |
| `Initial commit` | `main` | Repository setup with LICENSE file. |
| `add readme` | `main` | Initial README file. |
| `add dark mode button` | `feature/dark-mode-button` | Added theme toggle button and JavaScript logic. |
| `improve gitignore` | `fix_visual_box` | Improved .gitignore to exclude IDE and OS files. |
| `finished the java script file and added features` | `main` | Finalized JS features and styling. |

---

## Getting Started

The site is fully static. Simply open `index.html` in a browser, or run a local server:

```bash
npx serve .
# or
python -m http.server 8080
