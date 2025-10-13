# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal academic website/portfolio hosted on GitHub Pages (mthodi.github.io). The site uses **simple static HTML** with LaTeX.css for clean academic styling. It serves as:

1. **Public Portfolio**: Research, publications, datasets, and technical blog
2. **Private Career Management**: CVs, job applications, and knowledge base (git-ignored)

**PhD Research Focus**: PhD work on optimizing peering decisions using causal machine learning, BGP, and network optimization. The is an intersection of Internet measurements, machine learning, and network protocols.

## Architecture

### Site Structure

- **Simple Static HTML** - No build process required
- **LaTeX.css** - Academic paper styling loaded from CDN
- **Custom navbar CSS** - Minimal styling for navigation
- GitHub Pages serves directly from `/docs` folder

### Directory Structure

```
mthodi.github.io/
├── docs/                # GitHub Pages serves from here
│   ├── index.html       # Homepage
│   ├── publications/    # Publications page
│   ├── datasets/        # Research datasets
│   ├── blog/            # Blog posts by category
│   │   ├── ml/          # Machine learning posts
│   │   ├── webdev/      # Web development posts
│   │   └── papers/      # Paper reviews
│   └── css/             # Custom navbar styles
│       └── style.css
├── private/             # GIT-IGNORED private content
│   ├── cv/              # LaTeX CVs and applications
│   ├── knowledge-base/  # Personal achievements tracking
│   └── job-prep/        # Job research and preparation
├── source/              # OLD Sphinx files (archived, not used)
└── build/               # OLD Sphinx build (archived, not used)
```

### Styling

**LaTeX.css** (from CDN):
- Handles all typography, spacing, and content styling
- Academic paper aesthetic
- Responsive design
- URL: https://latex.vercel.app/style.css

**Custom CSS** (`docs/css/style.css`):
- Minimal navbar styling only
- Fixed/sticky navbar with white background
- Red text links (#8B0000)
- Centered content (max-width: 80ch)

## Development Workflow

### Editing Content

1. **Edit HTML files** directly in `docs/` directory
2. **Commit and push** to publish via GitHub Pages

No build process, no dependencies, just plain HTML!

### Page Structure

All pages follow this template:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Page Title - Martin Thodi</title>

    <!-- LaTeX.css for styling -->
    <link rel="stylesheet" href="https://latex.vercel.app/style.css">

    <!-- Custom navbar styles -->
    <link rel="stylesheet" href="../css/style.css">

    <!-- MathJax for math rendering -->
    <script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
</head>
<body>
    <!-- Navigation -->
    <nav class="navbar">
        <div class="nav-container">
            <a href="../index.html" class="nav-home">Martin Thodi</a>
            <ul class="nav-links">
                <li><a href="../index.html">about</a></li>
                <li><a href="../publications/index.html">publications</a></li>
                <li><a href="../datasets/index.html">datasets</a></li>
                <li><a href="../blog/index.html">blog</a></li>
            </ul>
        </div>
    </nav>

    <!-- Main Content -->
    <main>
        <h1>Page Title</h1>
        <!-- Your content here -->
    </main>
</body>
</html>
```

### Adding Blog Posts

1. Create HTML file in appropriate category:
   - `docs/blog/ml/` - Machine learning posts
   - `docs/blog/webdev/` - Web development posts
   - `docs/blog/papers/` - Paper reviews

2. Copy structure from existing pages
3. Update category index to link to new post

Example:
```bash
# Create new post
touch docs/blog/ml/2024-10-10-my-post.html

# Edit the file with navbar + content
# Update docs/blog/ml/index.html to link to it
```

### Managing Publications

1. Edit `docs/publications/index.html`
2. Add new entry following existing format
3. Include links to papers, slides, datasets

### Managing Datasets

1. Edit `docs/datasets/index.html`
2. Add description and citation information
3. Include download links

### Private Content (Never Committed)

**CVs** (`private/cv/`):
- Main CV template: `private/cv/main.tex`
- Compile: `pdflatex main.tex`
- Job-specific CVs in `private/cv/applications/{company}/`

**Knowledge Base** (`private/knowledge-base/`):
- Track achievements, skills, projects
- Monthly progress logs
- Used when updating CV or writing reports

**Job Prep** (`private/job-prep/`):
- Company research and application tracking
- Interview preparation notes
- Safe space for AI-assisted job preparation

## Features

- **LaTeX.css Styling**: Professional academic paper aesthetic
- **MathJax Support**: Full LaTeX math rendering
- **Responsive Design**: Mobile-friendly layout
- **Simple & Fast**: No build process, just edit HTML
- **Clean Navigation**: Fixed navbar, centered content
- **Minimal CSS**: Only custom styling for navbar

## Content Conventions

### Blog Posts

- Use semantic HTML (h1, h2, p, ul, etc.)
- Include publication date and metadata
- Code blocks with `<pre><code>` tags
- Math equations with MathJax syntax

### Publications

- Include author, title, venue, year
- Links to paper, slides, datasets
- Use consistent formatting

### Datasets

- Clear description of dataset
- Citation information
- Download button styled inline or with CSS

## Important Notes

### Security

- **Never commit private/ directory** - protected by .gitignore
- Always verify git status before committing
- Review `git diff --cached` before pushing

### GitHub Pages

- Site serves from `docs/` folder on main branch
- Include `.nojekyll` file (prevents Jekyll processing)
- Allow 1-2 minutes for deployment after push

### HTML Best Practices

- Use semantic HTML5 elements
- Keep structure simple and clean
- Let LaTeX.css handle all styling
- Only add custom CSS for navbar

## Common Tasks

**Add new blog post:**
1. Create HTML file: `touch docs/blog/ml/2024-10-10-post.html`
2. Copy navbar and structure from existing post
3. Add content in `<main>` section
4. Update `docs/blog/ml/index.html` to link to it

**Update homepage:**
1. Edit `docs/index.html`
2. Update About, Updates, Publications, or Contact sections
3. Commit and push

**Add publication:**
1. Edit `docs/publications/index.html`
2. Add entry in appropriate section
3. Include all links

**Update CV:**
1. Edit `private/cv/main.tex`
2. Run `pdflatex main.tex` twice
3. Review `private/cv/main.pdf`

**Prepare job application:**
1. Research in `private/job-prep/companies/`
2. Create custom CV in `private/cv/applications/{company}/`
3. Use AI assistance for tailoring content

**Preview changes:**
1. Open `docs/index.html` in browser
2. Or use simple server: `python -m http.server -d docs 8000`
3. Navigate to http://localhost:8000

## AI Assistant Usage

This repository is designed for collaboration with AI coding assistants:

- Public content: Assist with writing posts, editing HTML, content organization
- Private content: Help with CV writing, job prep, company research
- All `private/` content stays local and is never committed
- No complex build system to understand - just HTML!

## Styling Guidelines

### Using LaTeX.css

LaTeX.css handles:
- All typography (headings, paragraphs, lists)
- Content spacing and layout
- Code blocks and quotes
- Tables and figures
- Responsive design

Just use semantic HTML and LaTeX.css does the rest!

### Custom Navbar CSS

The `docs/css/style.css` file only contains:
- Fixed navbar styling
- White background, red links (#8B0000)
- Centered nav container (max-width: 80ch)
- Content centering (max-width: 80ch)
- Responsive mobile styles

**Do not add content styling** - let LaTeX.css handle it!

## Troubleshooting

**Links broken**: Check relative paths (../ for parent directory)

**Styling looks wrong**: Ensure LaTeX.css CDN link is present

**Math not rendering**: Check MathJax script is loaded

**GitHub Pages not updating**:
- Verify docs/ is committed
- Check Pages settings (source: main branch, /docs folder)
- Wait 1-2 minutes for deployment

**LaTeX CV issues**: Run pdflatex twice for references

## Migration Notes

This site was previously built with Sphinx. Old files are in `source/` and `build/` directories but are no longer used. The site now uses simple static HTML with LaTeX.css.

**Old Sphinx files**: Archived for reference, not used in production
**Current approach**: Direct HTML editing, no build process
