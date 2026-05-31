# Yelen Law Offices, P.A.

Single-page landing site for Yelen Law Offices, P.A. — Immigration & Traffic Law.

- **Production:** https://browardimmigrationlaw.com/
- **Framework:** Hugo (extended)
- **Deploy:** GitHub Pages via `.github/workflows/hugo.yml` on push to `main`

## Local Development

```sh
hugo server          # dev server with live reload at http://127.0.0.1:1313/
hugo                 # production build into ./public
```

## Project Structure

- `layouts/index.html` — the entire site (single-page template)
- `content/_index.md` — homepage content placeholder
- `hugo.toml` — site configuration
- `static/` — static assets (favicons, etc.)

## Future Considerations

### Re-enable taxonomies when content scales

`hugo.toml` currently includes:

```toml
disableKinds = ["taxonomy", "term"]
```

This suppresses Hugo's default `/tags/` and `/categories/` pages, which
would otherwise render as empty list pages on this single-page site
(and produce a `WARN found no layout file for "html" for kind "taxonomy"`
warning on every build).

**Remove this line when any of the following begin:**

- Adding a blog, news, or "recent immigration updates" section
- Adding a multi-entry content type (case studies, FAQ entries, attorney
  directory, practice-area pages, etc.)
- Beginning active SEO discoverability efforts where additional indexed
  pages — including taxonomy indices — provide search value

When you re-enable, you'll also need to create templates at
`layouts/_default/taxonomy.html` and `layouts/_default/term.html` to
render the taxonomy and term pages.
