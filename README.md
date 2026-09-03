# Project Possibility website

Source for [projectpossibility.uk](https://www.projectpossibility.uk/), rebuilt as a
Jekyll site for GitHub Pages, page-for-page migration from the previous Squarespace site.

## Local dev

```bash
bundle install
bundle exec jekyll serve
```

Site will be at http://localhost:4000

## Structure

- `_config.yml` — site settings (charity number, donate/social links)
- `_layouts/default.html` — shared page shell
- `_includes/nav.html`, `_includes/footer.html` — header/footer
- `assets/css/style.css` — all styling
- Top-level `.md` files — one per page, each with `permalink` front matter matching the
  live site's URL structure where practical

## Pages migrated from Squarespace

- `/` — home (mission + Fire & Ice + Silent Auction + Great Toy Race)
- `/fire-and-ice/` — Fire & Ice event page
- `/silent-auction/` — Silent Auction prize list (was `/silent-auction-2026`)
- `/community-library/`
- `/movie-time/`
- `/classtronauts/` (was `/classtronauts-2024`)
- `/projects/` — Future Projects (News Radio, Moonbounce, Reclaim Your Space)
- `/partners/` (was `/partners-3`)
- `/get-involved/`
- `/thank-you/`

## Not yet migrated (needs Rob/James/Andy decision)

- Squarespace **store/checkout** for Fire & Ice tickets (`/store`, `/store/p/fire-ice-2026`)
  — GitHub Pages can't run a checkout. Plan: link out to JustGiving or another form,
  or use a separate ticketing tool.
- Silent auction **live bidding** — currently static prize list; original site may have
  allowed in-page bidding via Squarespace commerce. Static site shows current bids only;
  actual bids go via email per the mailto link.

## Deploying

Point GitHub Pages (repo Settings → Pages) at the `main` branch, or add a
`.github/workflows/pages.yml` Actions deploy — not yet configured. DNS for
projectpossibility.uk currently points at Squarespace; cutover needs a DNS change
once this is signed off and live.
