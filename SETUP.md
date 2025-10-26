# Articles Site Setup Guide

This repository contains a Jekyll-based static site for publishing technical articles, similar to the design shown at https://ashashar.github.io/essays/intelligence.

## Local Development Setup

### Prerequisites
- Ruby (version 3.1 or higher)
- Bundler gem

### Installation Steps

1. **Install dependencies:**
   ```bash
   bundle install
   ```

2. **Serve the site locally:**
   ```bash
   bundle exec jekyll serve
   ```

3. **View your site:**
   Open http://localhost:4000 in your browser

## GitHub Pages Deployment

### Initial Setup

1. **Push to GitHub:**
   ```bash
   git add .
   git commit -m "Initial Jekyll site setup"
   git push origin main
   ```

2. **Enable GitHub Pages:**
   - Go to your repository settings on GitHub
   - Navigate to "Pages" section
   - Under "Source", select "GitHub Actions"
   - The workflow will automatically deploy your site

3. **Access your live site:**
   Your site will be available at: `https://rsinghvi.github.io/articles`

### Automatic Deployment

The site is configured with GitHub Actions for automatic deployment:
- Every push to the `main` branch triggers a new deployment
- The workflow builds the Jekyll site and deploys it to GitHub Pages
- Deployment typically takes 2-3 minutes

## Adding New Articles

### Create a new article:

1. **Create a new file** in the `_posts` directory with the format:
   ```
   YYYY-MM-DD-article-title.md
   ```

2. **Add front matter** at the top of your file:
   ```yaml
   ---
   layout: post
   title: "Your Article Title"
   date: 2025-10-26
   author: "Your Name"
   tags: ["tag1", "tag2", "tag3"]
   reading_time: 5
   excerpt: "A brief description of your article..."
   ---
   ```

3. **Write your content** in Markdown below the front matter

4. **Commit and push** to deploy:
   ```bash
   git add _posts/YYYY-MM-DD-your-article.md
   git commit -m "Add new article: Your Article Title"
   git push origin main
   ```

## Site Structure

```
├── _config.yml          # Site configuration
├── _layouts/             # Page templates
│   ├── default.html     # Base layout
│   └── post.html        # Article layout
├── _posts/              # Your articles (Markdown files)
├── _sass/               # Stylesheets
├── assets/css/          # Compiled CSS
├── .github/workflows/   # GitHub Actions deployment
└── index.html           # Homepage
```

## Customization

### Site Information
Edit `_config.yml` to update:
- Site title and description
- Your name and contact information
- Social media links
- Site URL

### Styling
- Edit files in `_sass/` directory to customize appearance
- Main styles are in `_sass/_layout.scss`
- Colors and typography in `_sass/_base.scss`

### Adding Pages
Create new `.md` files in the root directory with appropriate front matter for additional pages (like About, Contact, etc.)

## Features

- **Responsive design** that works on desktop and mobile
- **Clean, minimal aesthetic** similar to the reference site
- **Reading time estimation** for articles
- **Tag system** for categorizing content
- **SEO optimization** with meta tags and structured data
- **Syntax highlighting** for code blocks
- **Automatic deployment** via GitHub Actions

## Troubleshooting

### Local Development Issues

1. **Bundle install fails:**
   ```bash
   gem install bundler
   bundle install
   ```

2. **Jekyll serve fails:**
   ```bash
   bundle exec jekyll clean
   bundle exec jekyll serve --incremental
   ```

### Deployment Issues

1. **Check GitHub Actions:**
   - Go to the "Actions" tab in your repository
   - Look for failed workflows and check the logs

2. **Verify GitHub Pages settings:**
   - Ensure "Source" is set to "GitHub Actions"
   - Check that the repository is public or you have GitHub Pro

## Next Steps

1. Customize the site colors and typography in the SASS files
2. Add more articles to the `_posts` directory
3. Consider adding features like:
   - Search functionality
   - Article categories
   - Comment system
   - Analytics integration

Your site will be live at `https://rsinghvi.github.io/articles` once deployed!