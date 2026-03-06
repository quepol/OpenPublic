# CLAUDE.md

This document provides guidance for AI assistants working with the OpenPublic repository.

## Project Overview

**OpenPublic** is a static personal website for Hillary Hartley with the tagline "in the open // for the public". The site is hosted on GitHub Pages at the custom domain **openpublic.cc**.

- **Author**: Hillary Hartley
- **License**: MIT License (2026)
- **Status**: Active

## Repository Structure

```
OpenPublic/
├── CLAUDE.md                    # AI assistant guidance (this file)
├── CNAME                        # GitHub Pages custom domain (openpublic.cc)
├── LICENSE                      # MIT License
├── README.md                    # Repository description
├── index.html                   # Homepage (hero, about, work, contact sections)
├── workshops.html               # Workshops offering page
├── speaking.html                # Speaking topics/engagements page
├── coaching.html                # Coaching services page
├── writing.html                 # Writing page (articles + books sections)
├── articles.html                # Articles listing/index page
├── resources.html               # Resources I Love page
├── styles.css                   # Site-wide styles (~22KB, 128+ CSS classes)
├── hillary-hartley.jpg          # Author photo
├── public-speaking-icon.svg     # Icon asset
├── relationship-icon.svg        # Icon asset
├── training-icon.svg            # Icon asset
├── articles/                    # Directory of individual full-text article pages
│   ├── 20140319-hello-world-we-are-18f.html
│   ├── 20250302-deleting-18f.html
│   └── ... (named YYYYMMDD-slug.html)
└── services/                    # Hidden/unlisted service pages
    └── foundations_2025.html    # Foundation Workshops pricing (not in nav)
```

This is a static site with no build tools, frameworks, or dependencies.

## Technology Stack

- **Hosting**: GitHub Pages
- **Content Format**: Semantic HTML5 and CSS
- **Domain**: openpublic.cc (configured via CNAME)
- **Fonts**: Google Fonts (Inter, Lora) — loaded via `<link>` in `<head>`
- **JavaScript**: Minimal vanilla JS inline in each page (navigation toggle only)

No build step is required. HTML files are served directly by GitHub Pages.

## Navigation Structure

The site uses a consistent nav across all pages with two dropdown menus:

```
Hillary Hartley // OpenPublic  |  What I Do  About Me  [Work Together ▾]  [Learn ▾]  Get in Touch
                                                          Workshops          Writing
                                                          Speaking           Resources I Love
                                                          Coaching
```

- **Nav logo** links to `index.html`
- Dropdowns use `aria-expanded`/`aria-haspopup` for accessibility
- Mobile nav toggle via hamburger (three `<span>` lines, `onclick="toggleNav()"`)
- Each page includes the same nav block and the same inline JS:
  ```js
  function toggleNav() { document.querySelector('.nav-links').classList.toggle('active'); }
  function closeNav() { document.querySelector('.nav-links').classList.remove('active'); }
  function toggleDropdown(el) { ... }
  ```

## Key CSS Classes

All styles live in `styles.css`. Important layout classes:

| Class | Purpose |
|---|---|
| `.container` | Max-width wrapper, centered |
| `.nav-container` | Top nav bar layout |
| `.nav-logo` / `.logo-accent` | Site logo and `//` accent color |
| `.nav-links` / `.nav-dropdown` / `.nav-dropdown-menu` | Navigation links and dropdowns |
| `.hero-bg` / `.hero-content` / `.hero-headline` / `.hero-subhead` | Hero section |
| `.section-title` / `.section-intro` / `.section-content` | Standard section structure |
| `.about-layout` / `.about-image` | About section two-column layout |
| `.article-card` / `.article-card-*` | Article listing cards |
| `.article-body` / `.article-page-*` | Individual full article pages |
| `.book-entry` / `.book-*` | Books section in writing.html |
| `.footer-container` / `.footer-text` | Footer |

### Article card links use modifier classes:
- `.article-card-link.hosted` — article hosted on this site (in `articles/`)
- `.article-card-link.external` — links to external publications

## Page Anatomy

Every HTML page follows this structure:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <!-- charset, viewport, title, meta description -->
    <!-- Google Fonts preconnect + link -->
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <nav>...</nav>          <!-- identical nav block on every page -->
    <section id="...">      <!-- main content sections -->
        <div class="container">...</div>
    </section>
    <footer>...</footer>
    <script>                <!-- inline JS for nav toggle only -->
        function toggleNav() { ... }
        function closeNav() { ... }
        function toggleDropdown(el) { ... }
    </script>
</body>
</html>
```

## Article Pages (articles/ directory)

Individual articles live in `articles/` with filenames `YYYYMMDD-slug.html`. They use the `.article-page-*` CSS classes:
- `.article-page-hero` — top banner
- `.article-page-title` — article title
- `.article-page-byline` / `.article-page-meta` / `.article-page-pub` — metadata
- `.article-body` — body content with styled `p`, `h2`, `h3`, `ul`, `ol`
- `.article-back` — "← Back to writing" link

## Services Directory

`services/foundations_2025.html` is an unlisted pricing page (not linked in nav). It should remain unlisted unless explicitly directed to add it to navigation.

## Development Workflow

### Making Changes

1. Edit HTML/CSS files directly
2. Copy the nav block from an existing page when adding new pages
3. Commit changes with clear, descriptive messages
4. Push to the appropriate branch
5. GitHub Pages automatically deploys from the `main` branch

### Adding a New Page

1. Copy an existing page as a template (e.g. `coaching.html`)
2. Update `<title>`, `<meta name="description">`, and page content
3. Keep the nav block exactly as-is (copy from any existing page)
4. Add link to nav dropdown in **every existing page** if it should appear in nav
5. Use lowercase `.html` filename

### Adding a New Article (full-text hosted article)

1. Create `articles/YYYYMMDD-slug.html` using `.article-page-*` CSS classes
2. Add a card entry to `articles.html` using `.article-card` with class `.hosted` on the link
3. Also add/update entry in the articles section of `writing.html`

### Branching

- `main` — production deployment (GitHub Pages serves from this branch)
- `master` — exists locally; `main` is the GitHub Pages source
- Feature branches should be descriptive of the change

## Guidelines for AI Assistants

### Content Guidelines

1. **Keep it simple**: Static site — no build tools or frameworks
2. **Preserve the tone**: Minimalist, direct ("in the open // for the public"); professional but personal
3. **Consistent styling**: Use existing CSS classes; do not add new classes unless necessary
4. **Nav consistency**: The nav block must be identical across all pages — copy/paste it when creating or editing pages

### What NOT to Do

- Do not add build infrastructure (`package.json`, `node_modules`, etc.)
- Do not modify `CNAME` without explicit permission
- Do not add new CSS frameworks or JavaScript libraries
- Do not add inline styles — use `styles.css` classes
- Do not link `services/foundations_2025.html` in navigation unless explicitly asked
- Do not create new CSS classes when existing ones cover the need

### What TO Do

- Maintain clean, readable, semantic HTML5
- Use descriptive commit messages
- Respect the minimalist aesthetic
- Copy the nav block exactly when creating new pages
- When adding articles, follow the `YYYYMMDD-slug.html` naming convention
- Keep inline JS minimal (nav toggle only)

## GitHub Pages Notes

- Changes pushed to `main` are automatically deployed
- HTML files are served directly — no build step
- `CNAME` maps the repo to openpublic.cc

## Useful Commands

```bash
# Check repository status
git status

# View recent commits
git log --oneline -10

# Push changes
git push -u origin <branch-name>
```

## Contact

For questions about this project, contact Hillary Hartley.
