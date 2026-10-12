# Bipul Roy — Academic Website

Adapted from [sbryngelson/academic-website-template](https://github.com/sbryngelson/academic-website-template) (MIT License).

## Pages

Home, About, Experience, Research, Publications, Software and Contact.

## Editing

- `_config.yml` — name, links, colors, navigation and settings
- `_pages/` — main page content
- `_data/software.yml` — GitHub projects
- `assets/ref.bib` — manuscripts (update editorial status and verified DOIs)
- `images/bipul-roy.jpg` — headshot from previous site
- `assets/geospatial.css` — design refinements
- `images/research/` — project illustrations

The previous single-page portfolio has been retained at `previous-site.html` for reference but excluded from Jekyll output.

## Run locally

```bash
bundle install
bundle exec jekyll serve
```

Open `http://localhost:4000`.

## Publish to GitHub Pages

After reviewing and merging this PR into `main`:
1. Repository Settings → Pages → Source: **GitHub Actions**.
2. The included `.github/workflows/deploy.yml` deploys the website on every push to `main`.
3. Check https://Bipul-roy-AI.github.io/ after a successful workflow run.

## Credit

Jekyll academic website template © [sbryngelson](https://github.com/sbryngelson/academic-website-template), licensed under MIT (see `LICENSE`). Profile and project content adapted from Bipul Roy's previous public portfolio and GitHub repositories.
