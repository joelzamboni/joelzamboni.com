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

## Creating New Blog Posts

### File Creation
- Create new posts in `/content/posts/` directory
- Use kebab-case for filenames: `my-post-title.md`
- Files must have `.md` extension

### Frontmatter Format
Every post must begin with YAML frontmatter enclosed in `---`:

```yaml
---
title: 'Your Post Title Here'
date: 2025-07-21T00:00:00-04:00
draft: false
description: "Compelling 150-160 character meta description for SEO and social sharing"
tags:
    - tag1
    - tag2
---
```

**Important Notes:**
- **Title**: Use single quotes around the title
- **Date**: Use current date in ISO 8601 format with timezone offset (-04:00 for EDT)
- **Draft**: Set to `false` for published posts, `true` for drafts
- **Description**: REQUIRED for SEO - write compelling 150-160 character description that includes target keywords
- **Tags**: Use existing tags when applicable (see below)

### Available Tags
Common tags used across the blog:
- `ai` - Artificial intelligence and machine learning topics
- `automation` - Process automation and efficiency
- `devops` - Development operations and infrastructure
- `philosophy` - Philosophical discussions and thought experiments
- `work` - Future of work and career topics
- `future` - Predictions and forward-looking perspectives
- `politics` - Political analysis and social systems
- `humanity` - Human nature and social issues
- `religion` - Spiritual and religious topics

### Content Structure Patterns
1. **Opening**: Start with a compelling hook or introduction that frames the discussion
2. **Headings**: Use `##` for main sections (not `#` which is reserved for the post title)
3. **Style**: Mix conceptual discussion with concrete examples
4. **References**: Include cultural references, book quotes, or metaphors when relevant
5. **Blockquotes**: Use `>` for emphasis or notable quotes
6. **Bold text**: Use `**text**` for key concepts or important points

### Example Post Template
```markdown
---
title: 'Your Compelling Title Here'
date: 2025-07-21T00:00:00-04:00
draft: false
description: "Hook readers with clear value proposition and target keywords in 150-160 chars"
tags:
    - relevant-tag-1
    - relevant-tag-2
---

Start with an engaging introduction that hooks the reader and establishes the context for your discussion.

## Main Concept or Problem

Introduce the central idea or challenge you're addressing. Use concrete examples or metaphors to make abstract concepts accessible.

## Key Insight or Analysis

Develop your main argument with supporting evidence, examples, or logical progression. Consider using:

**Bold text** for emphasis on crucial points.

> Blockquotes for notable quotes or key takeaways

## Practical Implications

Connect your ideas to real-world applications or consequences. How does this affect readers' lives or understanding?

## Conclusion or Call to Action

Wrap up with a thought-provoking conclusion that synthesizes your points and leaves readers with something to consider.
```

### Writing Tips
- Maintain a conversational yet intellectually engaging tone
- Balance abstract concepts with concrete examples
- Use analogies and references to popular culture when appropriate
- Focus on thought-provoking content that challenges conventional thinking
- Keep paragraphs concise and readable

## SEO Configuration

### Current SEO Setup (Implemented August 2025)
The site has been fully optimized for search engines with the following implementations:

#### Technical SEO
- **Production URLs**: `baseURL` configured correctly as `https://joelzamboni.com`
- **XML Sitemap**: Auto-generated at `/sitemap.xml` on every build
- **Robots.txt**: Auto-generated, includes sitemap reference
- **Meta Tags**: All posts have required meta descriptions for SERP optimization
- **Structured Data**: Schema.org JSON-LD markup for Person/Organization and BlogPosting
- **Canonical URLs**: Implemented via PaperMod theme
- **OpenGraph & Twitter Cards**: Social media meta tags for sharing

#### Content SEO
- **Meta Descriptions**: All posts include 150-160 character descriptions with target keywords
- **Internal Linking**: Strategic cross-linking between related AI, philosophy, and politics posts
- **E-E-A-T Signals**: About page with author bio, Contact page, and Privacy Policy
- **Topic Clusters**: Organized content around main themes (AI, Philosophy, Politics, Religion)

#### Site Structure
- **Navigation Menu**: About, Tags, Contact pages accessible from header
- **Essential Pages**: 
  - `/about/` - Author bio and expertise signals
  - `/contact/` - Contact information and social links  
  - `/privacy/` - Privacy policy for trust signals
- **Tag Organization**: Consistent tagging strategy for content discovery

### SEO Maintenance Guidelines

#### For New Posts
1. **Always include `description` field** in frontmatter (150-160 characters)
2. **Add internal links** to related posts within the first few paragraphs
3. **Use target keywords** naturally in title, description, and headings
4. **Include TLDR sections** - these often appear in featured snippets

#### For Site Updates
- **Never change `baseURL`** without redirects - breaks all search rankings
- **Maintain URL structure** - keep `/posts/post-name/` format for consistency
- **Update sitemap automatically** - handled by Hugo, no manual intervention needed

#### SEO Monitoring
- **Google Search Console**: Monitor organic traffic and ranking changes
- **Core Web Vitals**: Track loading performance via PageSpeed Insights  
- **Keyword Tracking**: Monitor rankings for target terms like "AI future of work", "philosophy consciousness"

### Key SEO Files
- `hugo.yaml` - Contains schema configuration, site metadata, and SEO settings
- `/content/about.md` - Author authority and expertise signals
- `/content/privacy.md` - Trust and compliance signals
- Individual post frontmatter - Meta descriptions and keyword targeting

**Note**: Sitemap.xml and robots.txt are auto-generated on every build. Never edit them manually.