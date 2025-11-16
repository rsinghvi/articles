# GitHub Copilot Instructions

## Project Overview
This is a Jekyll-based static blog site for publishing technical articles, hosted on GitHub Pages at https://rsinghvi.github.io/articles.

**Architecture**: Standard Jekyll site structure with custom layouts, Sass styling, and automated GitHub Actions deployment.

## Key Conventions

### Article Creation
- **File naming**: All articles must follow `YYYY-MM-DD-title.md` format in `_posts/` directory
- **Required front matter fields**:
  ```yaml
  layout: post  # Always 'post' for articles
  title: "Your Title"
  date: YYYY-MM-DD
  author: "Rahul Singhvi"  # Default author from _config.yml
  tags: ["tag1", "tag2"]
  reading_time: 8  # Manual estimate in minutes
  excerpt: "Brief description..."
  ```
- **Content**: Write in Markdown below front matter; syntax highlighting uses Rouge (specified in `_config.yml`)
- **Headers**: Use sentence case for all headers (first letter of first word uppercase, rest lowercase)

### URL Structure
- **Baseurl**: Site uses `/articles` baseurl (configured in `_config.yml`)
- **Permalinks**: Articles use `/:title/` format (no date in URL)
- **Links**: Always use Liquid filters for URLs: `{{ '/' | relative_url }}` or `{{ post.url | relative_url }}`

### Layout System
- **`default.html`**: Base template with header/footer, Inter font, SEO plugins
- **`post.html`**: Article template that wraps in default layout, includes:
  - Back-to-articles link
  - Reading time display
  - Tag pills
  - Previous/next post navigation

### Styling
- **Framework**: Custom Sass in `_sass/` directory (`_base.scss`, `_layout.scss`, `_syntax-highlighting.scss`)
- **Typography**: Inter font (300/400/500/600 weights) loaded from Google Fonts
- **Theme**: Clean, minimal design with `#2c3e50` text, `#fdfdfd` background, `#1a1a1a` headings
- **Compilation**: Sass compiled via `assets/css/main.scss` which imports from `_sass/`

## Development Workflow

### Local Development
```bash
# Install dependencies (first time or after Gemfile changes)
bundle install

# Run development server
bundle exec jekyll serve

# View at http://localhost:4000/articles (note the /articles baseurl)
```

### Deployment
- **Automatic**: Pushes to `main` branch trigger `.github/workflows/deploy.yml`
- **Build process**: GitHub Actions runs `bundle exec jekyll build` with production baseurl
- **Deployment**: Typically takes 2-3 minutes to go live

## Dependencies & Plugins
- **Jekyll version**: `~> 4.3.0` (see Gemfile)
- **Theme**: `minima` `~> 2.5` (though heavily customized)
- **Plugins** (via `_config.yml`):
  - `jekyll-feed`: Generates Atom feed
  - `jekyll-sitemap`: Auto-generates sitemap.xml
  - `jekyll-seo-tag`: Meta tags for SEO

## Common Tasks

### Adding a new article:
1. Create `_posts/2025-MM-DD-article-title.md` with proper front matter
2. Write content in Markdown
3. Commit and push to `main` - deployment is automatic

### Modifying styles:
- Edit Sass files in `_sass/` directory
- Changes apply on next Jekyll build (automatic in local `serve` mode)

### Updating site metadata:
- Edit `_config.yml` for title, description, author, social links
- Requires Jekyll restart (`Ctrl+C` and re-run `bundle exec jekyll serve`)

## Important Files
- **`_config.yml`**: Site-wide configuration (requires restart after edits)
- **`Gemfile`**: Ruby dependencies
- **`index.html`**: Homepage showing article list
- **`_layouts/post.html`**: Article template with navigation and metadata
- **`_sass/_base.scss`**: Core typography and base styles
