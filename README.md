# help.houstonapartmentreviews.com

One-page apartment list site served by GitHub Pages, matching the design of
[HoustonApartmentReviews.com](https://houstonapartmentreviews.com).

## What's here

- `index.html` — landing page: light rose theme with Fraunces serif headings
  mirroring the main site, progressive-reveal form in a compact white card,
  Houston-specific copy (commute-focused)
- `thank-you/index.html` — post-submit page the form redirects to
- `css/site.css` — the main site's compiled stylesheet, self-hosted, plus an
  inline supplement for form utilities
- `images/` — self-hosted logo and favicon
- `CNAME`, `404.html`, `robots.txt`

## How the form works

The form posts FormData to the n8n webhook via fetch and mirrors a copy to
FormSubmit (email backup), then redirects to `/thank-you/`. Field names,
conditional reveals, validation, and the max-4 neighborhood limiter are
carried over unchanged from the original implementation.

## Deploying changes

GitHub Pages serves the `main` branch root. Merge to `main` and the site
updates in about a minute.
