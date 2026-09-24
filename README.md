# marcopiangerelli.it

Personal academic website of Marco Piangerelli, built with [Jekyll](https://jekyllrb.com/) and the [al-folio](https://github.com/alshedivat/al-folio) theme (v1.2).

- Content lives in `_pages/`, `_bibliography/papers.bib`, `_projects/`, `_news/`, `_posts/`, `_data/cv.yml` and `assets/`.
- Local preview: `bundle install && bundle exec jekyll serve` (Ruby 3.3), then open http://localhost:4000.
- Deployment: the `Deploy site` GitHub Action builds the site on every push to `alfolio` (the source branch of the current site) and publishes it to the `gh-pages` branch, which GitHub Pages serves at the custom domain in `CNAME`.
- The previous Alembic-based site is preserved untouched on the `master` branch and in the `legacy-alembic` tag.
