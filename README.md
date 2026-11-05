# help.houstonapartmentreviews.com

One-page apartment search form served by GitHub Pages, styled to match
[HoustonApartmentReviews.com](https://houstonapartmentreviews.com).

## What's here

- `index.html`: the form page. The header, footer and theme are the main
  site's (taken from its `/free-quote/` page); every menu and footer link goes
  back to houstonapartmentreviews.com, and the "Find Your Houston Apartment"
  buttons point to this page.
- The form is the secondchanceapartmentshouston.com form
  (`quad0028/sca-houston`, `/get-apartment-list/`): three steps that open as
  you answer, Houston areas and neighborhoods. The consent names the Houston
  Apartment Locators Group.
- `thank-you/index.html`: where the form lands after a send, with what
  happens next.
- `css/form.css`: the form's own styles, scoped under `.bca` so they never
  touch the main site's header and footer.
- `_astro/`, `images/brand/`, `fonts/`: the main site's stylesheets, logo,
  favicon and fonts, self-hosted.
- `sca-dropdown-validation.js`, `guest-card-copy-v1.js`,
  `_astro/form-area-context.js`: copied from sca-houston unchanged.
  `?area=` sets the heading to that area, as on sca-houston.
- `docs/`: the TREC Information About Brokerage Services and Consumer
  Protection Notice PDFs, linked at the bottom of the footer on every page.
- `banners/`: ad banners for the site.
- `CNAME`, `404.html` (sends to `/`), `robots.txt`.

## How the form sends a lead

1. It posts the lead as form data to the n8n webhook `NewWeb1` (the one
   sca-houston uses), with `formId` `har-secure-form` and `formTitle`
   "Houston Apartment Reviews - Get Started".
2. It sends an email copy to FormSubmit with sca-houston's FormSubmit key and
   the subject "Guest Card - Houston Apartment Reviews Referred By: the
   Houston Apartment Locators Group - Apartment Locators with Spirit Real
   Estate". FormSubmit emails the inbox behind that key.
3. It goes to `/thank-you/`.

`guest-card-copy-v1.js` only acts on the sca domains it lists, so on this
domain the email copy goes straight to FormSubmit.

The form and thank-you pages are `noindex, nofollow`. `robots.txt` allows
everything so search engines can read that tag.

## Deploying changes

GitHub Pages serves the `main` branch root. Merge to `main` and the site
updates in about a minute.
