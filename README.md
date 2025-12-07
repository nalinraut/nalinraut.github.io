# Nalin Raut - Personal Website

Personal academic portfolio website built with [al-folio](https://github.com/alshedivat/al-folio), a beautiful Jekyll theme for academics.

## Setup

This site uses GitHub Actions to build and deploy. The workflow is configured in `.github/workflows/deploy.yml`.

## Local Development

```bash
bundle install
bundle exec jekyll serve -l -H localhost
```

## Structure

- `_pages/` - Static pages (about, education, experience, projects, blog)
- `_projects/` - Portfolio projects
- `_posts/` - Blog posts
- `_layouts/` - Page layouts
- `_includes/` - Reusable components
- `_sass/` - Stylesheets
- `assets/` - CSS, JS, and images

## Deployment

The site is automatically built and deployed via GitHub Actions when changes are pushed to the main branch.
