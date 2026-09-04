# Project Possibility website

Source for [projectpossibility.uk](https://www.projectpossibility.uk/), rebuilt as a
Jekyll site for GitHub Pages, page-for-page migration from the previous Squarespace site.

## Content rule: no placeholder or invented information, ever

**Nothing goes on this site unless it is true and traceable to a real source.** This is a
registered charity. Made-up figures, filler text, and plausible-sounding guesses cause real
problems later: they mislead donors, contradict our Charity Commission filings, and go stale
without anyone noticing.

This specifically bans:

- **Placeholder text** of any kind: lorem ipsum, "TBC", dummy names, sample content copied
  from a theme or template.
- **Made-up numbers**: amounts raised, income and expenditure, participant counts, bid values,
  distances, dates. If it is a number, it needs a source.
- **Invented specifics**: school names, partner names, prize donors, quotes, testimonials,
  volunteer counts, staffing claims.
- **Copying a figure into the site as static text** when it will change later. Snapshot figures
  go out of date silently. Link to the authoritative source instead.
- **Plausible-sounding filler** written to make a section feel complete. An honest gap is
  better than confident-sounding invention.

If a fact cannot be verified, either leave it out or ask Rob. Never bridge the gap with a guess.

### Sources of truth

| Claim type | Verify against |
|---|---|
| Charity number, registration date, structure, trustees, policies, what/who/how/where | [Charity Commission register entry](https://register-of-charities.charitycommission.gov.uk/en/charity-search/-/charity-details/5226236) |
| Income, expenditure, accounts, annual returns | Charity Commission register: **link to it, do not copy figures into the page** |
| Past event content, dates, venues, prize lists | The live Squarespace site, or Rob |
| Amounts raised | The relevant JustGiving page |
| Anything else | Ask Rob. James and Andy are trustees too, so anything that changes how the charity presents itself gets flagged before it goes live |

### Before pushing content

1. For each factual claim, name the source. No source means it does not ship.
2. Check every external link actually resolves.
3. Prefer linking to a live source over restating a number that will drift.

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
