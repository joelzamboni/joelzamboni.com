# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

### Local Development
- `hugo server -D` - Start local development server at http://localhost:1313/ with live reloading and draft content

### Build
- `hugo` - Build site for production (outputs to `public/` directory)
- `hugo --gc --minify` - Build with garbage collection and minification (production settings)

### Git Operations
- `git submodule update --remote --merge` - Update PaperMod theme to latest version
- `git clone --recurse-submodules <repo-url>` - Clone repository with theme submodule

## Architecture

This is a Hugo static site generator blog using the PaperMod theme as a Git submodule.

### Key Components
- **Content**: Blog posts in `/content/posts/` as Markdown files with YAML frontmatter
- **Theme**: PaperMod theme in `/themes/PaperMod/` (Git submodule)
- **Configuration**: `hugo.yaml` contains site settings, theme configuration, and social links
- **Deployment**: Automated via GitHub Actions workflow (`.github/workflows/website-deployment.yml`)

### Site Configuration
- Uses Home-Info Mode with welcome message and social icons
- Configured for light theme with toggle option
- Includes Google Analytics, RSS feeds, and social sharing
- Hugo version: 0.141.0 (as specified in GitHub Actions)

### Content Structure
Posts use standard Hugo frontmatter with title, date, draft status, and tags. The site focuses on philosophy, politics, and personal reflections with no specific technical content structure.

### Deployment
Site automatically deploys to GitHub Pages when changes are pushed to main branch. The workflow builds with Hugo extended version and includes submodule checkout.