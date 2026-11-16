# Frontend Mentor - QR code component solution (Tailwind CSS v4)

This is a solution to the [QR code component challenge on Frontend Mentor](https://frontendmentor.io), refactored from custom CSS into **Tailwind CSS v4** using a local CLI build workflow.

## Table of contents

- [Overview](#overview)
- [The challenge](#the-challenge)
- [Links](#links)
- [My process](#my-process)
- [Built with](#built-with)
- [Step-by-step setup & build workflow](#step-by-step-setup--build-workflow)
- [Key CSS-to-Tailwind refactoring decisions](#key-css-to-tailwind-refactoring-decisions)
- [What I learned](#what-i-learned)
- [Continued development](#continued-development)
- [Author](#author)

## Overview

### The challenge

Build a responsive QR code card component matching the Frontend Mentor design specifications, then refactor the styling into utility-first Tailwind CSS v4 without external CDN links or inline scripts in the HTML `<head>`.

### Links

## My process

### Built with

- Semantic HTML5 markup (`<main>`, `<footer>`, `<h1>`, `<p>`)
- [Tailwind CSS v4](https://tailwindcss.com) (`tailwindcss` & `@tailwindcss/cli`)
- Custom `@theme` CSS variables for exact Frontend Mentor HSL colors
- Flexbox layout utilities and mobile-first responsive sizing
- Git, GitHub, and GitHub Pages for version control and deployment

### Step-by-step setup & build workflow

1. **Repository & Project Setup:** Cloned the base QR code component repository into VS Code and prepared the workspace for refactoring.
2. **Local Tailwind CSS v4 Installation:** Installed Tailwind CSS and the CLI tool locally via npm so the HTML `<head>` remains clean with zero external CDN dependencies:
```bash
npm install tailwindcss @tailwindcss/cli
```
3. **Theme & Entry CSS Configuration (`style.css`):** Imported Tailwind CSS v4 (`@import "tailwindcss";`) and defined the exact Frontend Mentor HSL color palette inside `@theme`:
```css
@import "tailwindcss";

@theme {
--color-slate-light: hsl(212, 45%, 89%);
--color-slate-text: hsl(216, 15%, 48%);
--color-slate-dark: hsl(218, 44%, 22%);
}
```
4. **CLI Compilation & Watch Mode:** Ran the Tailwind CLI compiler to scan `index.html` and output the standalone stylesheet into `./src/output.css`:
```bash
npx @tailwindcss/cli -i ./style.css -o ./src/output.css --watch
```

5. **HTML Utility Refactoring (`index.html`):** Linked `./src/output.css` in the `<head>` and replaced custom CSS selectors with Tailwind utility classes (`flex`, `min-h-screen`, `bg-slate-light`, `rounded-[20px]`, `max-w-[320px]`, `text-slate-dark`, `text-slate-text`).

6. **Version Control & Deployment:** Added `node_modules/` to `.gitignore`, committed all source files and compiled CSS (`./src/output.css`), pushed to GitHub, and enabled **GitHub Pages** from the `main` branch.

### Key CSS-to-Tailwind refactoring decisions

- **Full-screen centering:** Replaced `display: flex; flex-direction: column; justify-content: center; align-items: center; min-height: 100vh;` with `flex flex-col justify-center items-center min-h-screen`.
- **Exact card geometry:** Used Tailwind arbitrary values (`max-w-[320px]`, `rounded-[20px]`, `rounded-[10px]`) alongside spacing utilities (`p-4`, `pb-10`, `px-3`, `pt-6`) to preserve the original proportions.
- **Brand color accuracy:** Mapped the style guide's HSL values into custom `@theme` tokens (`bg-slate-light`, `text-slate-dark`, `text-slate-text`) for readable, reusable classes.

### What I learned

- **Local Build Pipelines vs. CDNs:** Learned how Tailwind CSS v4 compiles only the utility classes used in `index.html` into a lightweight production CSS file (`./src/output.css`) via `@tailwindcss/cli`.
- **Tailwind v4 `@theme` Syntax:** Practiced configuring custom design tokens directly inside CSS using `@import "tailwindcss";` and `@theme` rather than a legacy JavaScript config file.
- **Clean Git Hygiene:** Reinforced using `.gitignore` to exclude `node_modules/` while keeping `./src/output.css` tracked so GitHub Pages serves the compiled styles without requiring a server-side build step.

### Continued development

In upcoming projects, I plan to build multi-component responsive layouts using Tailwind CSS Grid utilities, explore interactive state modifiers (`hover:`, `focus-visible:`), and integrate Vite for larger multi-page web applications.

## Author

- GitHub - [@cedrickmmk](https://github.com)
- Frontend Mentor - [@cedrickmmk](https://frontendmentor.io)
