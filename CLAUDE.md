# CLAUDE.md

This document provides guidance for AI assistants working with the OpenPublic repository.

## Project Overview

**OpenPublic** is a static website project with the tagline "in the open // for the public". The site is hosted on GitHub Pages at the custom domain **openpublic.cc**.

- **Author**: Hillary Hartley
- **License**: MIT License (2025)
- **Status**: Active

## Repository Structure

```
OpenPublic/
├── CLAUDE.md          # AI assistant guidance (this file)
├── CNAME              # GitHub Pages custom domain (openpublic.cc)
├── LICENSE            # MIT License
├── README.md          # Repository description
├── index.html         # Homepage
├── workshops.html     # Workshops page
├── styles.css         # Site-wide styles
└── hillary-hartley.jpg # Author photo
```

This is a static site with no build tools, frameworks, or dependencies.

## Technology Stack

- **Hosting**: GitHub Pages
- **Content Format**: HTML and CSS
- **Domain**: openpublic.cc (configured via CNAME)

No build step is required. HTML files are served directly by GitHub Pages.

## Development Workflow

### Making Changes

1. Edit HTML/CSS files directly
2. Commit changes with clear, descriptive messages
3. Push to the appropriate branch
4. GitHub Pages automatically deploys changes from the main branch

### File Conventions

- **HTML**: Pages use semantic HTML5
- **CSS**: All styles in `styles.css`
- **index.html**: Homepage at openpublic.cc
- **CNAME**: Do not modify unless changing the custom domain

### Branching

- Main branch is used for production deployment
- Feature branches should be created for new work
- Branch names should be descriptive of the changes being made

## Guidelines for AI Assistants

### Content Guidelines

1. **Keep it simple**: This is a static site - avoid suggesting build tools or frameworks unless explicitly requested
2. **Preserve the tone**: Match the existing minimalist, direct style ("in the open // for the public")
3. **Consistent styling**: Use the existing CSS classes and maintain visual consistency across pages

### What NOT to Do

- Do not add unnecessary build infrastructure (package.json, etc.) unless requested
- Do not modify the CNAME file without explicit permission
- Do not add complex tooling to this intentionally simple project

### What TO Do

- Maintain clean, readable HTML and CSS
- Use descriptive commit messages
- Respect the minimalist aesthetic of the project
- When adding new pages, follow the existing file naming conventions (lowercase, .html extension)

## GitHub Pages Notes

- Changes pushed to the main branch are automatically deployed
- HTML files are served directly by GitHub Pages
- The CNAME file configures the custom domain mapping to openpublic.cc

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
