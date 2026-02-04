# CLAUDE.md

This document provides guidance for AI assistants working with the OpenPublic repository.

## Project Overview

**OpenPublic** is a static website project with the tagline "in the open // for the public". The site is hosted on GitHub Pages at the custom domain **openpublic.cc**.

- **Author**: Hillary Hartley
- **License**: MIT License (2025)
- **Status**: Early-stage / Coming Soon

## Repository Structure

```
OpenPublic/
├── CLAUDE.md          # AI assistant guidance (this file)
├── CNAME              # GitHub Pages custom domain (openpublic.cc)
├── LICENSE            # MIT License
├── README.md          # Repository description
└── index.md           # Homepage content
```

This is a minimal static site with no build tools, frameworks, or dependencies.

## Technology Stack

- **Hosting**: GitHub Pages
- **Content Format**: Markdown (.md files)
- **Domain**: openpublic.cc (configured via CNAME)

GitHub Pages automatically renders Markdown files as HTML. No build step is required.

## Development Workflow

### Making Changes

1. Edit Markdown files directly
2. Commit changes with clear, descriptive messages
3. Push to the appropriate branch
4. GitHub Pages automatically deploys changes from the main branch

### File Conventions

- **Markdown**: Use standard GitHub-flavored Markdown for all content
- **index.md**: Serves as the homepage at openpublic.cc
- **CNAME**: Do not modify unless changing the custom domain

### Branching

- Main branch is used for production deployment
- Feature branches should be created for new work
- Branch names should be descriptive of the changes being made

## Guidelines for AI Assistants

### Content Guidelines

1. **Keep it simple**: This is a static site - avoid suggesting build tools or frameworks unless explicitly requested
2. **Preserve the tone**: Match the existing minimalist, direct style ("in the open // for the public")
3. **Markdown formatting**: Use clean, readable Markdown with proper heading hierarchy

### What NOT to Do

- Do not add unnecessary build infrastructure (package.json, etc.) unless requested
- Do not modify the CNAME file without explicit permission
- Do not add complex tooling to this intentionally simple project

### What TO Do

- Maintain clean, readable Markdown
- Use descriptive commit messages
- Respect the minimalist aesthetic of the project
- When adding new pages, follow the existing file naming conventions (lowercase, .md extension)

## GitHub Pages Notes

- Changes pushed to the main branch are automatically deployed
- Markdown files are rendered as HTML by GitHub Pages
- The CNAME file configures the custom domain mapping to openpublic.cc
- Jekyll is the default static site generator (runs automatically, no configuration needed)

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
