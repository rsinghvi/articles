# Articles

A Jekyll-based static site for publishing technical articles.

🌐 **Live Site**: https://rsinghvi.github.io/articles

## Quick Start

1. **Clone and install:**
   ```bash
   git clone https://github.com/rsinghvi/articles.git
   cd articles
   bundle install
   ```

2. **Run locally:**
   ```bash
   bundle exec jekyll serve
   ```

3. **View at:** http://localhost:4000

## Features

- 📱 Responsive, mobile-friendly design
- ✨ Clean, minimal aesthetic inspired by modern blog designs
- 🏷️ Article tagging and categorization
- ⏱️ Reading time estimation
- 🎨 Syntax highlighting for code blocks
- 🚀 Automatic deployment via GitHub Actions
- 🔍 SEO optimized with meta tags

## Adding Articles

Create a new file in `_posts/` with the format `YYYY-MM-DD-title.md`:

```yaml
---
layout: post
title: "Your Article Title"
date: 2025-10-26
author: "Your Name"
tags: ["testing", "software-quality"]
reading_time: 8
excerpt: "Brief description of your article..."
---

# Your article content in Markdown
```

## Current Articles

- [Understanding Mutation Testing: A Comprehensive Guide](/_posts/2025-10-26-mutation-testing-guide.md)

## Tech Stack

- **Jekyll** - Static site generator
- **GitHub Pages** - Hosting
- **GitHub Actions** - CI/CD
- **Sass** - CSS preprocessing

See [SETUP.md](SETUP.md) for detailed setup instructions.
