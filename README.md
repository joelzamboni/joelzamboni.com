# joelzamboni.com

This repository contains the source code for my personal blog at [joelzamboni.com](https://joelzamboni.com).

## Technology

This site is built using:
- [Hugo](https://gohugo.io/) - A fast and modern static site generator
- [PaperMod](https://github.com/adityatelange/hugo-PaperMod) - A minimalist, responsive Hugo theme (included as a Git submodule)

## Getting Started

### Clone the Repository

To clone this repository with the PaperMod theme submodule:

```bash
git clone --recurse-submodules git@github.com:joelzamboni/joelzamboni.com
cd joelzamboni.com
```

### Update Submodules

To update the PaperMod theme to the latest version:

```bash
git submodule update --remote --merge
```

### Making Changes

After making changes to the site:

```bash
git status           # Check which files have been modified
git add .            # Add all changes (or specify files)
git commit -m "Your commit message describing the changes"
git push             # Push changes to GitHub
```

## Local Development

To run the site locally:

```bash
hugo server -D
```

This will start a local server at http://localhost:1313/ with live reloading enabled.

## Build

To build the site for production:

```bash
hugo
```

The generated static files will be in the `public` directory.

## Deployment

This site is deployed using GitHub Pages. A GitHub Actions workflow automatically builds and deploys the site whenever changes are pushed to the main branch.

### Automated Deployment

The deployment process is handled by the workflow defined in `.github/workflows/website-deployment.yml`. This workflow:

1. Builds the Hugo site
2. Publishes the generated files to GitHub Pages

No manual deployment steps are required - simply push your changes to the main branch, and the site will be automatically updated.
