# mthodi.github.io

Personal academic website and portfolio hosted on GitHub Pages.

**Live Site**: https://mthodi.github.io

## Overview

Simple static website built with HTML and [LaTeX.css](https://latex.vercel.app/) for clean academic styling.

## Structure

```
docs/                      # GitHub Pages serves from here
├── index.html             # Homepage
├── publications/          # Publications page
│   └── index.html
├── datasets/              # Research datasets
│   └── index.html
├── blog/                  # Blog categories
│   ├── index.html
│   ├── ml/                # Machine learning posts
│   ├── webdev/            # Web development posts
│   └── papers/            # Paper reviews
└── css/                   # Custom navbar styles
    └── style.css

private/                   # GIT-IGNORED private content
├── cv/                    # LaTeX CVs and applications
├── knowledge-base/        # Personal achievements tracking
└── job-prep/              # Job research and preparation

source/                    # OLD Sphinx files (archived)
build/                     # OLD Sphinx build (archived)
```

## Development

The site is simple static HTML - just edit the files in `docs/` directly:

1. **Edit HTML files** in `docs/` directory
2. **Commit and push** to publish via GitHub Pages

### Styling

- **LaTeX.css**: All main content styling (loaded from CDN: https://latex.vercel.app/style.css)
- **docs/css/style.css**: Minimal navbar styling only (white background, red links, sticky positioning)

## Adding Content

### New Blog Post

1. Create HTML file in appropriate category (`docs/blog/ml/`, `docs/blog/webdev/`, etc.)
2. Copy structure from existing pages (navbar + main content)
3. Update category index to link to new post

Example:
```bash
# Create new ML post
touch docs/blog/ml/2024-10-10-my-post.html
# Edit the file with navbar and content
# Update docs/blog/ml/index.html to link to it
```

### New Publication

1. Edit `docs/publications/index.html`
2. Add new entry following existing format

### New Dataset

1. Edit `docs/datasets/index.html`
2. Add description and download links

## GitHub Pages

- Site is published from `/docs` folder on main branch
- Allow 1-2 minutes for deployment after push
- `.nojekyll` file ensures GitHub Pages serves files directly

## Private Content (Never Committed)

**CVs** (`private/cv/`):
- Main CV: `private/cv/main.tex`
- Compile with: `pdflatex main.tex`
- Job-specific CVs in `private/cv/applications/{company}/`

**Knowledge Base** (`private/knowledge-base/`):
- Track achievements, skills, projects
- Monthly progress logs

**Job Prep** (`private/job-prep/`):
- Company research and interview prep
- Application tracking

## Page Structure

All pages follow this simple structure:

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

## Features

- **LaTeX.css Styling**: Professional academic paper aesthetic
- **MathJax Support**: Render LaTeX math equations
- **Responsive Design**: Mobile-friendly
- **Simple & Fast**: No build process, just edit HTML
- **Clean Navigation**: Fixed navbar with centered content

## Privacy & Security

- The `private/` directory is **git-ignored** and never committed
- Always verify `.gitignore` before committing
- Never commit CVs, personal notes, or sensitive information
- Review changes before pushing: `git diff --cached`

## License

The code for this site is MIT licensed. Content (blog posts, research) remains copyrighted by Martin Thodi unless otherwise specified.

## Contact

- **Website**: https://mthodi.github.io
- **Email**: mart@gmail.com
- **GitHub**: [@mthodi](https://github.com/mthodi)

---

Built with HTML + [LaTeX.css](https://latex.vercel.app/) and hosted on [GitHub Pages](https://pages.github.com/).
