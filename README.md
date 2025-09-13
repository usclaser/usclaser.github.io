# usclaser.github.io

Jekyll site for the Laboratory for Autonomous Systems in Exploration and Robotics (LASER) at USC Viterbi.

## Details

- Hosting service: GitHub pages
- Domain service: whatever github provides internally for *.github.io domains

## Local Deployment

Optional: install Bootstrap locally for development assets `npm init -y && npm install bootstrap`.

To serve locally with Jekyll:

```bash
bundle install
bundle exec jekyll serve
# then open http://localhost:4000
```

For github pages deployment, see `.github/workflows/jekyll.yml`

## Notes

For anyone happening on this page, I highly recommend [this blog post](https://geekdude.github.io/tech/new-website/) for resources on
how to work with Jekyll/Github Pages.

## Information architecture

- Home: overview, recent news, selected publications
- People: lab members and alumni
- Research: themes and current projects
- Publications: full list from `_publications/`
- News: announcements
- Join: recruiting info and how to apply
- Contact: email and links

Assets live under `assets/`. Site-wide includes in `_includes/`. Layouts in `_layouts/`. Publications live in `_publications/` as Markdown files with front matter.