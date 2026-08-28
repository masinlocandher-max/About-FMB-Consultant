# Francine Marie Bautista — Consultant Profile

Live address: **https://francinemariebautista.com/fmbconsultant/**

A dedicated consultancy profile website for Francine Marie Bautista (FMB), adapted from the editorial visual language of the separate Miss Intercontinental application profile.

## Positioning

This version presents FMB as an independent consultant working across brand strategy, strategic communications, public relations, reputation and perception, creative direction, storytelling, community and cultural projects, tourism/place branding, training, and practical digital initiatives.

The site is designed to answer three questions quickly:

1. What problems can FMB help solve?
2. How does she think and work?
3. What kind of engagement is a good fit?

## Visual direction

The consultancy version intentionally keeps the established FMB editorial system and existing core profile photography for continuity. Miss Intercontinental-specific portfolio concepts are not carried over. Consultancy case studies and portfolio imagery can be added separately once the final work selection is approved.

## Status

Prepared as a first consultancy-ready version. Portfolio/case-study imagery is intentionally excluded for now.

## Repository layout

```
CNAME                    francinemariebautista.com (apex domain for this repo)
index.html               root redirect -> /fmbconsultant/
404.html                 fallback page
.nojekyll                serve files as-is, no Jekyll processing
fmbconsultant/index.html the consultancy profile page
```

The page lives in `fmbconsultant/` so that, with the apex domain attached to this
repository, GitHub Pages serves it at exactly `francinemariebautista.com/fmbconsultant/`.
Anyone landing on the bare domain is redirected to the same place.

## Deployment

### 1. Enable GitHub Pages

Repository **Settings → Pages**:

- **Source:** Deploy from a branch
- **Branch:** `main` / `/ (root)`

The `CNAME` file in this repo sets the custom domain automatically; leave
**Enforce HTTPS** checked once the certificate has been issued (can take up to
an hour after DNS resolves).

### 2. Point DNS at GitHub

At the registrar for `francinemariebautista.com`:

| Type  | Name  | Value |
| ----- | ----- | ----- |
| A     | `@`   | `185.199.108.153` |
| A     | `@`   | `185.199.109.153` |
| A     | `@`   | `185.199.110.153` |
| A     | `@`   | `185.199.111.153` |
| CNAME | `www` | `masinlocandher-max.github.io` |

(AAAA records for the same host — `2606:50c0:8000::153` through `…8003::153` —
can be added for IPv6.)

Remove any existing A/ALIAS/CNAME records on `@` that point somewhere else, or
the domain will keep resolving to the old host.

### 3. Verify

- `https://francinemariebautista.com/fmbconsultant/` — the profile page
- `https://francinemariebautista.com/` — redirects to the profile page

If the domain is already serving another site, put that site's files at the root
of this repo (or move this repo's Pages setup under whichever repository owns the
domain, keeping the `fmbconsultant/` folder intact) — only one repository can
hold the apex domain at a time.

## Search visibility

The page is currently `noindex,nofollow` and labelled a draft edition. Remove the
`<meta name="robots">` tag in `fmbconsultant/index.html` when it is ready for
public launch.
