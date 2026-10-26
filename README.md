# Marginalia

Marginalia is a single-page bookstore landing page for a fictional used-and-rare books shop. The site is designed as a warm, editorial storefront with a vintage bookshop aesthetic, using HTML and Tailwind CSS.

## Project overview

This project is a static website built with:

- HTML for the document structure
- Tailwind CSS for layout and styling
- A small custom CSS layer in `src/input.css` for reusable component classes
- A simple local development server powered by Python

The page includes:

- a top navigation bar
- a hero section with editorial typography
- a featured shelf section
- a brand story / “Why readers return” section
- a newsletter signup section
- footer information and contact details

## Project structure

```text
Marginalia/
├── index.html              # Main page markup
├── package.json            # Scripts and dependencies
├── package-lock.json       # Lockfile for installed packages
├── src/
│   ├── input.css           # Tailwind entry file and custom component classes
│   └── output.css          # Generated CSS file produced by Tailwind
├── .gitignore              # Git ignore rules
├── .env                    # Local environment config
└── README.md               # Project documentation
```

## How it works

### 1. HTML structure

The main content lives in `index.html`. It defines the page sections, typography, and the content for the bookstore storefront. The structure is intentionally semantic and includes anchors such as `#shelves`, `#why`, and `#newsletter` for in-page navigation.

### 2. Tailwind styling

The project uses Tailwind CSS via the `@tailwindcss/cli` package. The build pipeline is defined in `package.json`:

- `npm run build` compiles `src/input.css` into `src/output.css`
- `npm run dev` builds the stylesheet and serves the site locally

The stylesheet in `src/input.css` imports Tailwind and adds a few reusable classes:

- `.nav-color`
- `.book-box`
- `.grid-content`

These helpers keep the markup cleaner while preserving the custom bookstore aesthetic.

### 3. Generated CSS

`src/output.css` is the compiled stylesheet generated from the Tailwind source. This file is linked from `index.html`:

```html
<link rel="stylesheet" href="src/output.css">
```

### 4. Local development

The project is designed to run as a simple static site.

To install dependencies:

```bash
npm install
```

To build the CSS once:

```bash
npm run build
```

To start the local dev environment:

```bash
npm run dev
```

This starts a Tailwind watch build and serves the site with Python’s `http.server` on a local port, defaulting to `4173` unless `PORT` is set.

## Notes

- There is no JavaScript app framework here; this is a static landing page.
- The site is intentionally styled as a literary bookstore, with custom colors, serif typography, and editorial spacing.
- The visual language is driven by custom Tailwind utility classes and a few component-level CSS helpers.

## Typical workflow

1. Edit the HTML in `index.html` for content changes.
2. Update `src/input.css` for custom styles and reusable class variants.
3. Run `npm run dev` to rebuild CSS while previewing the page locally.
4. Open the local server in the browser to review the design.

This is a lightweight, easy-to-edit static site ideal for mockups, storefront showcases, or small marketing pages.
