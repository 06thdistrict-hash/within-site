# within.ae

Marketing site for Within — budget planning for nights out and weekends away
in the UAE.

One self-contained file, `index.html`. No build step, no dependencies. Fonts
load from Google Fonts; all CSS, JavaScript and the favicon are inline.

## Hosting

Served by GitHub Pages from the `main` branch, repository root.
Live at https://06thdistrict-hash.github.io/within-site/

`.nojekyll` stops GitHub from running the page through Jekyll.

## Waitlist

Signups POST as JSON to `https://formsubmit.co/ajax/withinaeteam@gmail.com`.

1. FormSubmit sends a one-time activation link to that inbox the first time the
   form is submitted from the live URL. Until someone clicks it, submissions are
   accepted but never delivered. Submit one signup after the site is live, then
   click the link in the inbox.
2. After activating, FormSubmit issues a random endpoint string for the same
   inbox. Swap it in for the address in `ENDPOINT` near the bottom of the file,
   so the inbox is not sitting in the page source for scrapers.

## Custom domain

When within.ae is registered:

1. Add a `CNAME` file at the repository root containing `within.ae`.
2. At the registrar, create an ALIAS or ANAME record for the apex pointing at
   `06thdistrict-hash.github.io`, and a CNAME for `www` pointing at the same.
   If the registrar only supports A records at the apex, use GitHub's four:
   185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153.
3. In Settings → Pages, set the custom domain and tick "Enforce HTTPS" once the
   certificate is issued.
4. Change the footer's `within.ae` link from `#top` to `https://within.ae`.

## Editing

Open `index.html`. The palette and type are CSS custom properties on `:root`.
The marquee duplicates its content and animates to `translateX(-50%)` — edit
both `.marquee-group` blocks together or the loop will jump.
