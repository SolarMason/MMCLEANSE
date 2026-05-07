# M&M Cleanse — Production PWA

Mobile-first, iOS-styled, fully functional PWA for M&M Cleanse. White & gold luxury aesthetic. Zero broken links. All CTAs hooked to real endpoints.

---

## File map

```
mm-cleanse/
├── index.html              ← The whole site (single-file, ~88KB)
├── manifest.webmanifest    ← PWA install metadata
├── sw.js                   ← Service worker (offline + caching)
├── browserconfig.xml       ← Microsoft/Windows tile config
├── robots.txt              ← SEO crawl directives
├── sitemap.xml             ← SEO sitemap
├── favicon.ico             ← Multi-res ICO (16/32/48)
├── favicon.svg             ← Modern vector favicon
├── og-image.png            ← Landscape share card (1200×630) — Facebook, X/Twitter, LinkedIn, Discord, Slack
├── og-image-square.png     ← Square share card (1080×1080) — iMessage, WhatsApp, Telegram, Signal, Instagram
├── og-image-vertical.png   ← Vertical share card (1080×1350) — Pinterest pin format
├── mm-cleanse.vcf          ← Digital business card (Save to Contacts on iOS/Android)
└── icons/                  ← Full Apple/Android/PWA/MS icon set
    ├── apple-touch-icon-{57,60,72,76,114,120,144,152,167,180}.png
    ├── apple-touch-icon.png (default 180×180)
    ├── android-chrome-{36,48,72,96,144,192,256,384,512}.png
    ├── favicon-{16,32,48}.png
    ├── mstile-{70,144,150,310}x*.png
    └── maskable-icon-512.png  (PWA adaptive icon)
```

---

## Deploy

This is a **static site** — drop it on any host (Netlify, Vercel, GitHub Pages, Cloudflare Pages, your own server, etc.). No build step required.

**Important for service worker:** The site **must be served over HTTPS** for the PWA / install / offline features to work. (HTTPS is automatic on Netlify, Vercel, Pages, etc.)

### Domain
Throughout the file, the canonical domain is `https://mmcleanse.com`. If your live domain differs (e.g. `solarmason.com/mmcleanse` or a Wix subpath), find/replace `mmcleanse.com` in `index.html`, `sitemap.xml`, and `manifest.webmanifest`.

---

## What's wired up (every CTA is real)

| Element | Action |
|---|---|
| All "Call Now" buttons | `tel:+15707061413` |
| All "Text us" buttons | `sms:+15707061413` |
| All email links | `mailto:Mmcleanse@yahoo.com` |
| Facebook links | Real M&M Cleanse Facebook page |
| **Quote form submit** | Composes a fully prefilled `mailto:` to `Mmcleanse@yahoo.com` with all form fields and opens the user's email app |
| Service cards | Scroll/jump to the quote form |
| All anchor links (#services, #faq, etc.) | Real in-page anchors |
| PWA shortcuts (long-press app icon) | Call / Quote / Services |

There are **no placeholder links and no JS handlers that go nowhere.** Every interactive element does what it says.

> **Heads-up about the form:** Without a backend, the form opens the user's mail app pre-filled and lets them hit Send. This is the most reliable zero-backend approach. If you want submissions to go straight to your inbox (no user mail-client step), I'd recommend wiring it to **Formspree**, **Web3Forms**, or **Netlify Forms** — a 5-min change in the form's submit handler.

---

## ⚠️ Before you go live — replace these placeholders

1. **Customer reviews** in the "Sparkling reviews. Real homes." section are illustrative examples I wrote (Sarah K. / Maria L. / Jenna & Rob T.) — they are **not real M&M customers**. Replace with actual reviews from your Facebook page, or delete the `<section id="reviews">` block.
2. **`aggregateRating`** in the JSON-LD structured data uses placeholder `5.0 / 5 reviews`. Update to match your real Facebook review count.
3. **Service area cities** are listed broadly across NEPA — confirm the list matches where you actually service.

---

## SEO checklist (all included)

- ✅ `<title>`, `<meta description>`, `<meta keywords>`, canonical URL
- ✅ Open Graph tags (Facebook/LinkedIn/iMessage share previews)
- ✅ Twitter/X card tags
- ✅ Geographic / local SEO (geo.region, geo.placename, ICBM)
- ✅ Schema.org `LocalBusiness` JSON-LD with services, hours, area served, ratings
- ✅ `robots.txt` + `sitemap.xml`
- ✅ Semantic HTML5 (`<header>`, `<main>`, `<nav>`, `<article>`, `<aside>`, `<footer>`)
- ✅ Skip-to-content link and proper ARIA labels
- ✅ All images have `alt` text
- ✅ `prefers-reduced-motion` and `:focus-visible` support

## PWA checklist

- ✅ Web App Manifest with full icon set (9 PNG sizes + maskable)
- ✅ Service worker with cache-first/network-first strategies and offline fallback
- ✅ `theme-color` for both light and dark mode
- ✅ Apple touch icons covering every iOS device generation (57px → 180px)
- ✅ iOS standalone-app mode (`apple-mobile-web-app-capable`)
- ✅ Microsoft tile icons + `browserconfig.xml`
- ✅ App shortcuts (Call / Quote / Services from long-press menu)
- ✅ `viewport-fit=cover` + `safe-area-inset-*` for iPhone notch/Dynamic Island
- ✅ Offline-capable after first visit

## Brand checklist

- ✅ White & gold throughout, every section
- ✅ iOS-style top app bar (frosted blur, auto-hide on scroll-down)
- ✅ iOS-style bottom tab bar on mobile (Home / Services / Call / Text / Quote)
- ✅ Glassmorphism cards, soft shadows, rounded iOS corner radii
- ✅ Cormorant Garamond display + Italianno script accents
- ✅ Promo strip (dismissible, sessionStorage-backed) for Mother's Day — easy to swap for any future promo
- ✅ Subtle gold sparkle accents and gentle reveal animations

---

## Updating the Mother's Day promo later

The Mother's Day campaign is intentionally NOT the centerpiece — the site is about the brand, not the promo. To swap it:

1. **Top promo strip:** Edit the text inside `<aside class="promo-strip">` in `index.html`.
2. **Promo card section:** Edit the contents of `<section id="promo">` — change the `$300`, the headline, and the bullet points.
3. **Form chip:** Update the "Mother's Day Sale" `<label class="chip">` checkbox to match the new promo name.

To remove the promo entirely, delete the `<aside class="promo-strip">` block and the `<section id="promo">` block. Nothing else depends on them.

---

Built with care. Sparkle on. ✨
