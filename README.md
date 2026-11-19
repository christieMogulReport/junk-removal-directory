# Junk & Dumpster Guide

Static directory site (Python + Markdown) for the niche **junk removal and dumpster rental**. Brand owner: Black Swan Sibyl (Christie Justice). Same generator pattern as `shred-directory` and `directory-site`. **Not yet deployed**: no GitHub repo, domain, or CNAME exists yet (`base_url` in `config.yml` is a placeholder).

## Commands
```bash
python3 build.py            # build into dist/ (drafts excluded)
python3 serve.py            # build and preview at http://127.0.0.1:8000
python3 build.py --drafts   # include draft: true pages
```
The first run creates a local `.venv` and installs `requirements.txt`.

## Add a page
Create `content/pages/<slug>.md` with front matter: `title`, `slug`, `description`, `last_updated` (YYYY-MM-DD), optional `draft`, optional `show_in_index: false` (keeps a page off the homepage guide list), optional `listings` (each with `name`, `url`, optional `affiliate_url`, `summary`, `category`). Quote any value containing a colon. Tables are supported. Homepage intro is `content/home.md`; site settings and footer links are in `config.yml`.

Differences from the sibling build.py: Markdown `tables` extension, `show_in_index`, `footer_links` in config, and the homepage list is headed "Guides".

## Rules for content
- Only real, sourced information. Cite the source for prices, weights, and fees; show ranges; say "confirm with your hauler".
- Before adding an affiliate link, fill `affiliate_disclosure` in `config.yml`.
- Queue: `PAGE_IDEAS.md`. Record each shipped page in `PUBLISH_LOG.md`.

## Deploy (when set up)
Same as siblings: push to `main`; `.github/workflows/pages.yml` builds and deploys to GitHub Pages; add `static/CNAME` for a custom domain. `data/` and `tools/` are gitignored (private earnings and outreach notes).
