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

## Live
- **Production:** https://goldsmith-exteriors.vercel.app
  (Vercel project `goldsmith-exteriors`, team `bt-uff-security-s-projects`)
- **Custom domain:** `goldsmithexteriors.com` + `www` are added to the project. They go
  live once Namecheap DNS points at Vercel — `A @ → 76.76.21.21` and
  `CNAME www → cname.vercel-dns.com`. HTTPS auto-provisions after DNS resolves.
- **Redeploy:** `vercel --prod --yes --scope bt-uff-security-s-projects` from this folder.
  Static site, zero config.
- GitHub Pages was retired in favor of Vercel.

## Backlog — collect from the owner, then patch in
Photo slots were removed from the **live** site so nothing reads as unfinished.
The original slot markup is preserved on the **`photos-pending`** branch — when the
photos land, restore/fill from there and redeploy.
- [ ] **Hero + owner/crew photos** → real images for the home hero, "Why Goldsmith", and the about hero (slots on `photos-pending`)
- [x] **Real before/after job photos** → the shed demo/haul-away pair is live on the home page
- [x] **Logo + favicon** → wired (`assets/logo-mark.png`, `logo-lockup.png`, `favicon.png`)
- [ ] **Owner story** → replace the generic about-page copy with the owner's real words (TODO markers in `about.html`)
- [ ] **Exact service list + wording** → verify against the flyer (TODO markers in `services.html` / `index.html`)
- [ ] **True service-area radius** → confirm the town list in `index.html`
- [ ] **Hours** → confirm in `contact.html` (currently "Mon–Sat, 8am–6pm")
- [ ] **Guarantee wording** → confirm the callout claim on `index.html`
- [ ] **Licensed/insured?** → only add if true (intentionally left off)
- [ ] **Quote form** → optional: wire to Web3Forms/Formspree (no backend); call/text is the live path
- [ ] **Lead email** → optional: add a contact email if the owner wants typed leads

## Brand tokens (in css/styles.css `:root`)
- bg `#0A0E13` · cyan `#2FC9EC` (water) · green `#29C46E` (CTA) · gold `#E8C079` (Goldsmith accent)
- Display: Anton · Body: Manrope

## Notes
- Accessibility: semantic landmarks, skip link, focus-visible rings, reduced-motion guard, aria labels.
- SEO: per-page titles/descriptions, Open Graph, LocalBusiness JSON-LD on home.
- Mobile: sticky bottom Call / Free-Quote bar, hamburger nav, fluid type.
