# Nalin Raut - Personal Website

Personal academic portfolio website built with [AcademicPages](https://github.com/academicpages/academicpages.github.io), a Jekyll template for academic personal websites.

## Setup

This site uses GitHub Actions to build and deploy. The workflow is configured in `.github/workflows/pages.yml`.

## Local Development

```bash
bundle install
bundle exec jekyll serve -l -H localhost
```

## Structure

- `_pages/` - Static pages (about, education, etc.)
- `_portfolio/` - Portfolio projects
- `_posts/` - Blog posts
- `_layouts/` - Page layouts
- `_includes/` - Reusable components
- `_sass/` - Stylesheets
- `assets/` - CSS, JS, and images

## Deployment

The site is automatically built and deployed via GitHub Actions when changes are pushed to the main branch.
