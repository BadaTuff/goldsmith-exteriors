# Goldsmith Exteriors — website

Static marketing site for **Goldsmith Exteriors** (pressure washing / exterior cleaning, Cambridge, MN).
Built by BTuff. Plain HTML + CSS + vanilla JS — **no framework, no build step, no backend.**
Fully portable: any host (or any future dev) can pick it up and run it as-is.

- **Phone (confirmed):** 763-339-1628
- **Paradigm:** luxury-bezel on Goldsmith's dark brand (Anton + Manrope, cyan + green + gold)
- **Pages:** `index.html` (home) · `services.html` · `about.html` · `contact.html`

## Structure
```
goldsmith-exteriors/
├── index.html        # home
├── services.html     # service detail
├── about.html        # about / owner story (placeholder copy)
├── contact.html      # contact + free-quote form
├── css/styles.css    # entire design system
├── js/main.js        # nav, scroll reveal, before/after slider
└── assets/           # drop logo + job photos here
```

## Preview locally
From this folder:
```
python3 -m http.server 8000
```
Then open **http://localhost:8000** in your browser.
Stop it with Ctrl-C when done.

## Deploy to Vercel (when ready)
This is a static site, so Vercel needs zero config.
1. `vercel` from this folder (or drag-drop the folder in the dashboard), **or** push to a Git repo and import it.
2. No build command, output dir = project root.
3. Add the custom domain in Vercel → Settings → Domains.

## The remaining 10% (what to collect from the owner)
- [ ] **Real logo file** → `assets/`, then wire favicon + swap the inline SVG mark if desired
- [ ] **Before/after + job photos** → swap the `.ba__pane` backgrounds and `.media-card` placeholders (biggest visual upgrade)
- [ ] **Owner story** (the recording) → replace placeholder copy in `about.html`
- [ ] **Exact service list + wording** → verify against the flyer (`<!-- TODO -->` markers in `services.html` / `index.html`)
- [ ] **Lead email** → replace `hello@goldsmithexteriors.com` everywhere
- [ ] **True service-area radius** → confirm town list in `index.html`
- [ ] **Hours** → confirm in `contact.html`
- [ ] **Guarantee wording** → confirm the callout claim on `index.html`
- [ ] **Licensed/insured?** → only add that claim if it's true (intentionally left off)
- [ ] **Quote form** → wire to Web3Forms/Formspree endpoint (no backend needed) — until then, call/text/email are the live path

## Brand tokens (in css/styles.css `:root`)
- bg `#0A0E13` · cyan `#2FC9EC` (water) · green `#29C46E` (CTA) · gold `#E8C079` (Goldsmith accent)
- Display: Anton · Body: Manrope

## Notes
- Accessibility: semantic landmarks, skip link, focus-visible rings, reduced-motion guard, aria labels.
- SEO: per-page titles/descriptions, Open Graph, LocalBusiness JSON-LD on home.
- Mobile: sticky bottom Call / Free-Quote bar, hamburger nav, fluid type.
