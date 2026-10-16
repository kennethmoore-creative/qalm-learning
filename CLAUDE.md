# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Purpose

This repo holds company documents and branding for **Qalm Learning**, a new
company. It is not a software project. There is no build, lint or test
tooling. The `.gitignore` is the stock R template, but the repo contains no R
code yet.

The repo is at a very early stage. `README.md` has an unfinished sentence
("We're going to"), and the only asset so far is a draft brand board.

## Brand (draft)

The source of truth is `assets/Qalm Learning Draft Brand.png`. Everything
below comes from that image and is still a draft.

- **Wordmark:** "Qalm" in a navy serif typeface, with an amber pen nib on the
  tail of the Q. "LEARNING" sits below in amber, in a widely spaced sans-serif.
- **Tagline:** none. The board shows "Confidence Today • Brighter Tomorrows",
  but Ken doesn't want it used anywhere.
- **Logo variations:** primary, horizontal, stacked, icon/favicon (Q with the
  nib) and monochrome.
- **Palette:** Navy (trust, focus, professional), Amber (energy, progress,
  optimism), Cream (clarity, calm, balance) and Sky (learning, growth,
  possibility). No hex values have been defined yet. If you need exact
  colours, ask the user rather than sampling them from the image.
- **Icon system:** an app icon (white Q and nib on a navy tile), a pen nib
  (simple secondary icon) and an open book (expanded secondary icon).
- **Spelling:** the board uses British spelling ("Colour Palette").

Company details: **Qalm Learning Pty Ltd**, ACN 702 322 950. The email is
info@qalmlearning.com. The repo is public, so never commit the street
address or phone number. They live only in the local, git-ignored
`letterhead.html`. The business is based in Melbourne but
works across Australia and internationally. Use Australian English.

## Conventions

- Put brand images and other binary assets in `assets/`.
- `letterhead.html` is an A4 letter template that you edit in the browser.
  It is git-ignored and exists only on Ken's machine because it contains
  private contact details.

## Website (`site/`)

- One static page (`site/index.html`, `site/css/style.css`) with no build
  step and no JavaScript. It covers two services: K-12 Tutoring and
  Educational Consulting.
- `.github/workflows/deploy.yml` deploys **only `site/`** to GitHub Pages on
  every push to `main`. The custom domain is qalmlearning.com, set in the
  repo's Pages settings rather than with a CNAME file. DNS is on Namecheap.
- `site/assets/` holds copies of the logo files plus `icon-nib.png` and
  `icon-book.png`, cropped from the brand board. Keep the palette in
  `style.css` `:root` in sync with `letterhead.html`.
- Check changes by screenshotting at both widths:

```
npx playwright screenshot --full-page --viewport-size=1280,900 --channel=chrome "file:///C:/Users/KenMoore/Documents/R/qalm-learning/site/index.html" desktop.png
npx playwright screenshot --full-page --viewport-size=390,844 --channel=chrome "file:///C:/Users/KenMoore/Documents/R/qalm-learning/site/index.html" mobile.png
```
