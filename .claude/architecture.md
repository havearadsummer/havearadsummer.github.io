# Have a Rad Summer - Architecture Summary

## Project Overview
Static travel blog built with Jekyll and hosted on GitHub Pages, documenting a family's 2016 summer travel experiences.

**Live Site:** www.havearadsummer.com

## Project Type
Jekyll-based static site generator with responsive design, interactive dashboards, and location-based content.

## Tech Stack

### Core Technologies
- **Jekyll** - Static site generator (Ruby-based)
- **Twenty Theme** (HTML5 UP) - Responsive multi-page template
- **Skel Framework** - Lightweight responsive framework
- **jQuery** - DOM manipulation and UI interactions

### Visualization & Dashboards
- **D3.js** - Data visualization
- **Rickshaw** - Time-series charting
- **Chart.js** - Simple charting
- **Google Maps API** - Geographic mapping
- **Pleasure Dashboard** (ThemeForest) - Material Design admin panel

### Additional Libraries
- **Disqus** - Blog comments
- **Font Awesome** - Icon library
- **Bootstrap 3.0.3** - Grid and components
- **Video.js** - Video player

## Directory Structure

```
/havearadsummer (root)
├── jekyll/              # Source directory (editable content)
│   ├── _config.yml      # Jekyll configuration
│   ├── _layouts/        # Page templates (default.html, post.html, dashboard.html)
│   ├── _includes/       # Shared components (head, header, footer)
│   ├── _posts/          # Blog posts (Markdown)
│   ├── dashboards/      # Interactive dashboard pages
│   └── [HTML pages]
├── css/                 # Responsive stylesheets
├── js/                  # Client-side JavaScript
├── fonts/               # Font Awesome & custom fonts
├── images/              # Travel photos (organized by location)
├── dashboards/          # Generated dashboard assets
├── 2016/                # Generated blog posts
├── index.html           # Homepage
├── blog.html            # Blog listing
├── about.html           # About page
├── 404.html             # Error page
└── feed.xml             # RSS feed
```

## Key Components

### 1. Layout System
- **default.html** - Base layout with header/footer
- **post.html** - Blog post layout with Disqus comments
- **dashboard.html** - Interactive dashboard layout with maps

### 2. Blog System
- Posts written in Markdown in `/jekyll/_posts/`
- Compiled to `/2016/[month]/[day]/[slug].html`
- Disqus integration for comments
- Previous/Next post navigation

### 3. Dashboard Pages
- Interactive trip summaries with Google Maps
- Location-based visualization
- Photo galleries with sliders
- Custom JavaScript initialization per location

### 4. Responsive Design
Breakpoint cascade managed by Skel framework:
- **Global**: 1400px containers
- **Wide**: up to 1680px
- **Normal**: up to 1280px
- **Narrow**: up to 980px
- **Narrower**: up to 840px
- **Mobile**: up to 736px

## Build & Deployment

### Build Process
1. Edit content in `/jekyll/` directory
2. Run `jekyll build` (outputs to `../gh-pages`)
3. Copy to root: `rsync -r ../gh-pages/* ../`
4. Clean up: `rm -r ../gh-pages`
5. Commit and push to GitHub (auto-deploys via GitHub Pages)

### Configuration
Jekyll config in [_config.yml](jekyll/_config.yml):
- Source: `/jekyll/`
- Destination: `../gh-pages`
- Markdown: kramdown
- Custom domain via CNAME file

## Content Organization

### Images
Organized by location in `/images/`:
- `/nice/` - Nice, France
- `/tuscany/` - Tuscany, Italy
- `/santabarbara/` - Santa Barbara, CA
- `/sansebastian/` - San Sebastian, Spain
- `/vernazzo/` - Vernazzo, Italy
- `/rome/` - Rome, Italy

### Posts
Blog posts in `/jekyll/_posts/` with YAML frontmatter:
```yaml
---
layout: post
title: "Post Title"
date: 2016-MM-DD
author: Author Name
---
```

## Key Features
- ✅ Responsive mobile-first design
- ✅ Location-based photo galleries
- ✅ Interactive maps and dashboards
- ✅ Blog with commenting system
- ✅ Timeline component for journey documentation
- ✅ SEO optimized with XML feed
- ✅ Custom domain support

## External Dependencies
- **Jekyll** (Ruby) - Build tool
- **GitHub Pages** - Hosting
- **Disqus** - Comments service
- **Google Maps API** - Mapping
- **Font Awesome** - Icons

## Architecture Notes
- Pure static site (no database, no server-side processing)
- No modern build tools (webpack, npm, bundling)
- Classic 2016-era jQuery-based architecture
- Content-focused with minimal dependencies
- Fully hosted on GitHub Pages
