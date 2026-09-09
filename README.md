# The Renovation Price Book — validation MVP

Crowd-sourced price book of real UK renovation quotes ("Levels.fyi for home renovation").
Live at: https://duffdeal.github.io/renovation-price-book/

## What's here

- `index.html` — single-page MVP: Stat-Led hero (real £40bn/yr ONS figure), how-it-works,
  illustrative preview table (labelled as published-guide data), contribution form, FAQ.
- `styles.css` / `tokens.css` — Hallmark build (macrostructure: Stat-Led, theme: Newsprint,
  editorial genre, N6 masthead, Ft1 footer). Tokens referenced by name throughout.
- `.hallmark/log.json` — build log for future Hallmark runs.

## How the form works (no backend, no accounts)

1. The form POSTs via `fetch` to FormSubmit AJAX:
   `https://formsubmit.co/ajax/d5fa84b7b941fa5a51e745d3040d3bb0`
   (the hash is the FormSubmit alias for thomasalexanderjacks@gmail.com — activated 9 Sep 2026,
   bound to this Pages origin).
2. Each submission arrives as a **table-formatted email in the Gmail inbox**.
3. Antispam: hidden `_honey` field + client-side sanity checks (lowest ≤ highest, email format,
   postcode district present). `_captcha=false` (no reCAPTCHA key on a static site yet).

## If submissions arrive

- 100+ quotes in the first month → build the dataset + programmatic postcode pages.
- Test records: search Gmail `from:formsubmit.co subject:TEST` and delete them.

## Deployment

GitHub Pages from `main` (repo: duffdeal/renovation-price-book). Push to deploy; first
build takes ~60s. Changes to the form's endpoint require re-activating FormSubmit
(submit once, click the emailed link).
