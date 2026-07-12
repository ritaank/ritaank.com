# ritaank.com

Personal site built with [Zola](https://www.getzola.org/).

## Structure

- `content/_index.md`: homepage copy and homepage metadata.
- `content/about.md`: full About page at `/about/`.
- `content/admissions.md`: admissions page at `/admissions/`.
- `content/blog/_index.md`: writing section at `/blog/`.
- `templates/`: Tera templates for page layout.
- `templates/index.html`: homepage template.
- `templates/partials/nav.html`: top navigation.
- `sass/main.scss`: site styles, compiled by Zola.
- `static/`: static assets copied as-is.
- `public/`: generated build output; do not edit directly.

## Common Tasks

Install Zola if needed:

```sh
brew install zola
```

Run locally:

```sh
zola serve --interface 127.0.0.1 --port 1111
```

Build:

```sh
zola build
```

Verify key routes:

```sh
for route in / /about/ /blog/ /admissions/; do
  printf '%s ' "$route"
  curl -s -o /dev/null -w '%{http_code}\n' "http://127.0.0.1:1111$route"
done
```

## Editing Notes

- Edit Markdown in `content/` for copy changes.
- Edit `templates/` for layout changes.
- Edit `sass/main.scss` for styling.
- Rebuild or use `zola serve` after changes.
- Check `/` and `/about/` after bio or homepage edits; they intentionally use different copy.
