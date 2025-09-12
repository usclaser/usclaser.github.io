# albee-research-site

This is a Jekyll-based static site for my research work!

## Details

- Hosting service: GitHub pages
- Domain service: whatever github provides internally for *.github.io domains

## Local Deployment

You'll need to install bootstrap locally, `npm init -y && npm install bootstrap`.

For serving content on localhost during development:

```bash
cd docs
bundle exec jekyll serve

# navigate to http://localhost:4000
```

For github pages deployment, see `.github/workflows/jekyll.yml`

## Notes

For anyone happening on this page, I highly recommend [this blog post](https://geekdude.github.io/tech/new-website/) for resources on
how to work with Jekyll/Github Pages.

## Usage

- `*.md` pages support markdown using markdownify.
- `publications.md` supports upload of citations following the format in `_publications/`
  - [ ] TODO: this might be cleaner to pull directly from a `.bib`
- new images and other assets should be stored in `assets/`
- special javascript for website features (like swapping content) should be stored in `assets/js/`