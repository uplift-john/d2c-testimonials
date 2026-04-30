# Direct2Care Testimonials

Mobile-first landing pages for D2C testimonial videos. Each page lives at its own URL behind a QR code printed on a custom band-aid handed out at convention booths.

## Repo structure

```
d2c-testimonials/
├── template.html          ← master template (don't edit per-page; edit here for design changes)
├── logo.png               ← shared D2C logo
├── README.md
└── pages/
    ├── michaela/
    │   └── index.html     ← published at /michaela/
    └── [next-employee]/
        └── index.html
```

## Live URLs

Each subfolder publishes to:

```
https://uplift-john.github.io/d2c-testimonials/[employee-slug]/
```

That's the URL to encode in each band-aid's QR code.

## How to add a new testimonial

Send Claude these five things in one message:

1. Employee first name (e.g. *Michaela*)
2. Employer (e.g. *McDonald's*, *Chick-fil-A*)
3. Location (city or state — e.g. *Washington*)
4. Descript video ID (the part after `/embed/` in the share URL — e.g. `0ktg6resbWU`)
5. Pronouns (*she/her*, *he/him*, or *they/them*) — used in the caption sentence

Claude returns a ready-to-upload `index.html`. You drag it into a new `pages/[slug]/` folder in this repo, commit, and the URL is live in ~30 seconds.

## Publishing checklist

- [ ] New folder under `pages/` with employee's slug (lowercase, hyphenated)
- [ ] `index.html` placed in that folder
- [ ] Committed to `main` branch
- [ ] Verified URL loads on phone
- [ ] Video plays on tap with audio
- [ ] HubSpot form submits successfully (test once per testimonial isn't necessary — same form across all pages)
- [ ] Name spelled correctly in headline and caption
- [ ] QR code generated pointing to the live URL

## GitHub Pages setup (one-time)

Settings → Pages → Source: **Deploy from a branch** → Branch: **main**, Folder: **/ (root)**.

## Design changes

Edit `template.html`. Then any new pages generated from it pick up the change automatically. Existing published pages won't auto-update — they'd need to be regenerated and re-committed. Worth noting before making sweeping changes once you have many pages live.
