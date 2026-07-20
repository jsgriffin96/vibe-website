# Vibe a Website — Before You Arrive

Pre-work checklist for the **Vibe a Website** workshop.

**👉 Read it here: https://jsgriffin96.github.io/vibe-website/**

CCIDM · College of Business Administration · Cal Poly Pomona

## What this is

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
| `.nojekyll` | Tells GitHub Pages to serve the file as-is, without Jekyll processing |

## Updating the page

`index.html` is **rendered output**, not the source. The Quarto source
(`prework-checklist.qmd` plus its theme and include files) lives in the private
`ccidm-scripts` repo under `workshop-planning/vibe-website/`.

To publish a change:

1. Edit `prework-checklist.qmd` in `ccidm-scripts`
2. `quarto render prework-checklist.qmd`
3. Copy the result here as `index.html`, then commit and push

GitHub Pages redeploys automatically on push to `main`, usually within a minute.
