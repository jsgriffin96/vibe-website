# Vibe a Website

Materials for the **Vibe a Website** workshop.

**👉 Pre-work checklist: https://jsgriffin96.github.io/vibe-website/**
**👉 Slides: https://jsgriffin96.github.io/vibe-website/slides.html**

CCIDM · College of Business Administration · Cal Poly Pomona

## The pre-work checklist

A ~15-minute setup checklist students complete before class, so class time goes to
building rather than installing. It covers ChatGPT (campus account), a text editor,
Netlify, and Shopify login — plus a fill-in **site brief** builder at the bottom of
the page, which is the actual homework.

The brief builder saves answers to the browser's local storage and has a copy-to-clipboard
button. Everything runs client-side; nothing is submitted anywhere.

## What's in this repo

| File | Purpose |
|---|---|
| `index.html` | The rendered checklist — fully self-contained (CSS, JS, and fonts embedded) |
| `slides.html` | The rendered workshop deck — the **audience** copy (see multiplex below) |
| `.nojekyll` | Tells GitHub Pages to serve the files as-is, without Jekyll processing |

## The slides

The deck has [reveal.js multiplex](https://quarto.org/docs/presentations/revealjs/presenting.html#multiplex)
turned on: when you advance the speaker copy, every browser viewing `slides.html`
advances with you. Students follow along on their own screens at their own zoom level.

Rendering produces **two** files:

| File | Who it's for |
|---|---|
| `slides.html` | Audience. Read-only — it follows the speaker, it can't drive. |
| `slides-speaker.html` | **You, locally.** Embeds the control secret. |

`slides-speaker.html` is gitignored here on purpose. Anyone who opens it can control
the deck for every connected viewer, so it must never be pushed to a public repo —
open it from your own machine on presentation day.

Both files share a socket ID baked in at render time, and they only sync if they
carry the **same** ID. Quarto reuses the existing ID as long as the previously
rendered `slides.html` / `slides-speaker.html` are still sitting in the source
folder — so ordinary re-renders are safe. Deleting those outputs first (or
rendering on a fresh clone or a different machine) mints a **new** ID and secret.

Either way, republish `slides.html` whenever you re-render, so the published
audience copy always matches your local speaker copy.

## Updating a page

The `.html` files here are **rendered output**, not source. The Quarto sources
(`prework-checklist.qmd`, `slides.qmd`, plus their theme and include files) live in
the private `ccidm-scripts` repo under `workshop-planning/vibe-website/`.

To publish a change:

1. Edit the `.qmd` in `ccidm-scripts`
2. `quarto render prework-checklist.qmd` (or `slides.qmd`)
3. Copy the result here — `prework-checklist.html` becomes `index.html`; `slides.html`
   keeps its name. Then commit and push.

GitHub Pages redeploys automatically on push to `main`, usually within a minute.
