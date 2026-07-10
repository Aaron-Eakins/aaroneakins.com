# Backlog: aaroneakins.com (2026-07-10)

Deferred items from the July 10 ticket pass. Not scheduled; captured so they don't get lost.

## 1. Per-page og:image for each write-up

Today every page shares `https://aaroneakins.com/img/preview.jpg`. Link previews for
`flour-city-labs.html` and `site-infrastructure.html` therefore look identical to the resume.

Plan:
- Create `img/og-flour-city-labs.jpg` and `img/og-site-infrastructure.jpg` at 1200x630.
- Point each page's `og:image` at its own file. Leave `index.html` on `preview.jpg`.
- Add `<meta property="og:image:width">` / `height` so scrapers size the card without fetching.
- Verify with a link-preview debugger after deploy, since Open Graph output is cached by
  consumers and won't refresh on its own.

## 2. Nav link to the GitHub profile on index.html

The sticky nav on `index.html` currently carries email and LinkedIn. The GitHub profile is
the most relevant of the three for the projects the page now leads with, but it's absent.

Plan:
- Add `github.com/Aaron-Eakins` to the nav's right-hand link group, after LinkedIn.
- Watch the narrow-viewport wrap: three links plus separators may need the nav to stack or
  the labels to shorten on small screens. Check at 375px before shipping.

## 3. Site-infrastructure page: Nginx security headers

`site-infrastructure.html` describes the droplet, Nginx, Git deploy, and Let's Encrypt, but
says nothing about response headers because none are configured yet.

Plan:
- First do the actual work: add HSTS, `X-Content-Type-Options`, `X-Frame-Options` (or a
  frame-ancestors CSP), and `Referrer-Policy` to the Nginx server block.
- Only then write it up. This item is blocked on the config change, not on the copy.
- A short paragraph in the write-up beats a bullet list, matching the page's existing voice.

## Not doing

Adding a sentence about improving the AI-assisted workflow to the Flour City Labs write-up.
Revisit once it can be phrased concretely rather than as an aspiration.
