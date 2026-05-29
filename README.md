# Direct2Care Testimonials

Mobile-first landing pages for D2C testimonial videos. Each page lives at its own URL behind a QR code printed on a custom band-aid handed out at convention booths.

## Repo structure

```
d2c-testimonials/
├── index.html             ← root page (says "scan the band-aid")
├── template.html          ← master template (don't edit per-page; edit here for design changes)
├── logo.png               ← shared D2C logo
├── README.md
├── michaela/
│   └── index.html         ← published at /michaela/
└── hennazie/
    └── index.html         ← published at /hennazie/
```

Each employee gets a folder at the repo root containing only `index.html`.

## Live URLs

```
https://uplift-john.github.io/d2c-testimonials/michaela/
https://uplift-john.github.io/d2c-testimonials/hennazie/
```

That's the URL to encode in each band-aid's QR code.

## How to add a new testimonial

Send Claude these things in one message. The first four are required; the last three are optional:

1. Employee first name (e.g. *Michaela*)
2. Location (city or state — e.g. *Washington*)
3. Descript video ID (`{{VIDEO_ID}}` — the part after `/embed/` in the share URL — e.g. `0ktg6resbWU`). This is the **vertical (9:16) hero cut**.
4. Pronouns (*she/her*, *he/him*, or *they/them*) — used in the caption

> The employer is **not named** on the page — the caption just reads "…thanks to her employer." No employer field is needed.

Optional:

5. `{{FULL_VIDEO_ID}}` — Descript ID for the **full-length (4–7 min) story cut**, shown landscape (16:9) behind the collapsed "Hear {name}'s full story" toggle below the CTA. If you don't have one yet, leave the placeholder and swap it in later.
6. `{{HOOK_PHRASE}}` — a short emotional phrase shown above the video (e.g. *Grateful*, *She never misses a shift.*). Leave it blank and the element auto-collapses with no gap.
7. `{{LEARN_MORE_URL}}` — destination for the "See how Direct2Care works" primary button. Defaults to a placeholder if omitted.

Claude returns a ready-to-upload `index.html`. Create a new folder at the repo root named for the employee (lowercase, hyphenated for multi-word names), drop the file in, commit. Live in ~30 seconds.

## Publishing checklist

- [ ] New folder at repo root with employee's slug (lowercase, hyphenated)
- [ ] `index.html` placed in that folder
- [ ] Committed to `main` branch
- [ ] Verified URL loads on phone, video plays, logo renders
- [ ] Name spelled correctly in headline and caption
- [ ] QR code generated pointing to the live URL

## GitHub Pages setup (one-time)

Settings → Pages → Source: **Deploy from a branch** → Branch: **main**, Folder: **/ (root)**.

## Design changes

Edit `template.html`. Then any new pages generated from it pick up the change automatically. Existing published pages won't auto-update — they'd need to be regenerated and re-committed.

## Path note for the curious

Each employee `index.html` references the shared logo as `../logo.png` (one level up from the employee folder, where the logo lives at the repo root). If the structure ever changes — for example, moving employee folders deeper — the logo path in the template needs to update accordingly.
