# vecnode.github.io

Source for <https://vecnode.github.io/>, a [Jekyll](https://jekyllrb.com/) site
built on [al-folio](https://github.com/alshedivat/al-folio) v1.2.

Publishing is handled by GitHub Actions: `.github/workflows/deploy.yml` builds
the site with Jekyll and publishes `_site/` to GitHub Pages. The repository's
Pages source stays on **GitHub Actions** and `main` is the only branch that
deploys. Pull requests build without publishing.

> The archived sites at `/sites/` are a **separate repository**
> ([vecnode/sites](https://github.com/vecnode/sites)) with its own workflow.
> Nothing in this repo builds or deploys them — do not create a page at
> `/sites/` here, it would collide with that project site.

## Editing

| What | Where |
| --- | --- |
| Name, description, URL, feature flags | `_config.yml` |
| Social links (GitHub, email, RSS) | `_data/socials.yml` |
| GitHub users and repos on `/repositories/` | `_data/repositories.yml` |
| Home page | `_pages/about.md` |
| Navbar pages | `_pages/*.md` — `nav: true` puts a page in the navbar |
| Publications | `_bibliography/papers.bib` |
| Co-author links | `_data/coauthors.yml` |
| Blog posts | `_posts/YYYY-MM-DD-title.md` |
| Project cards | `_projects/*.md`, rendered on `/projects/` |
| News items on the home page | `_news/*.md` |

In `v1.x` al-folio is a thin starter rather than a vendored theme: layouts,
includes, styles and the Tailwind build come from the version-pinned
`al_folio_core` and `al_*` gems in `Gemfile`. This repository holds content and
deliberate overrides only, so theme fixes arrive by bumping a version in
`Gemfile`.

Pages currently parked (present at their URL, hidden from the navbar):
`/blog/`, `/projects/`, and `/publications/` is not present until there is a
bibliography to show.

## Local preview

Docker is the supported route — it carries the right Ruby, ImageMagick and the
pinned gems, and mirrors the CI build:

```bash
docker compose pull
docker compose up          # http://localhost:8080
```

`docker compose -f docker-compose-slim.yml up` uses a sub-100 MB image instead.
If the container cannot write `.jekyll-cache`, follow the commented-out
`GROUPID`/`USERID` block in `docker-compose.yml`.

To build without serving:

```bash
docker compose run --rm jekyll bundle exec jekyll build
```

## Upstream

al-folio is tracked as a second git remote so the theme can be diffed or
rebased against a later release:

```bash
git fetch al-folio --tags
git diff v1.2 al-folio/main -- _config.yml     # see what upstream changed
```

`classic-main` holds the previous hand-written single-page site, and
`pre-al-folio` tags it.
