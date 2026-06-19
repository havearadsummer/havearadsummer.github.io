# Agent Notes for `havearadsummer.github.io`

## Repository purpose
- This repository hosts the `havearadsummer.com` static travel site.
- The editable source lives in `/home/runner/work/havearadsummer.github.io/havearadsummer.github.io/jekyll`.
- The repository root contains the generated site that gets published.

## Source of truth
- Prefer editing files under `jekyll/`.
- Treat matching files at the repository root as generated output unless a task explicitly requires editing the published artifact directly.
- When source content is changed in `jekyll/`, rebuild and sync the generated output back to the repository root.

## Important paths
- `jekyll/_config.yml` — Jekyll config, with `destination: ../gh-pages`
- `jekyll/_layouts/` — page layouts (`default`, `landing-page`, `post`, `dashboard`)
- `jekyll/_includes/` — shared partials like the header, footer, and page head
- `jekyll/_posts/` — blog posts
- `jekyll/dashboards/` — dashboard-style trip pages
- `images/`, `css/`, `js/`, `fonts/`, `assets/` — generated static assets at the published root

## Common content patterns
- Blog posts use front matter like `layout: post`, `title`, `date`, and `author`.
- Main pages such as `index.html`, `about.html`, and `blog.html` are Jekyll pages under `jekyll/`.
- Dashboard pages use `layout: dashboard` and may rely on page-level front matter like `latitude` and `longitude`.

## Build and publish workflow
From `jekyll/`:
1. Run `jekyll build`
2. Copy the generated site into the repository root: `rsync -r ../gh-pages/* ../`
3. Remove the temporary output directory: `rm -r ../gh-pages`

These steps are documented in `README.md` and `jekyll/README.md`.

## Validation expectations
- There is no repository-level CI workflow checked in.
- The main available validation is the Jekyll build from `jekyll/`.
- If `jekyll` is unavailable in the environment, note that limitation in your handoff.

## Editing guidance
- Keep changes surgical and preserve the existing theme structure.
- Use root-relative asset paths consistently, matching the existing site.
- Avoid unnecessary edits inside third-party vendor assets under `dashboards/assets/globals/plugins/` unless the task specifically targets them.
