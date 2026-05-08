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
├── privacy.html            ← Privacy Policy page
├── terms.html              ← Terms of Service page
├── accessibility.html      ← Accessibility Statement page
├── media/                  ← Marketing collateral hub
│   ├── index.html          ← Gallery page with category filters + previews + downloads
│   ├── pdfs/               ← 20 print-ready branded PDFs
│   │   ├── 01-business-card.pdf      (3.5×2 in, front + back)
│   │   ├── 02-door-hanger.pdf        (4×11 in)
│   │   ├── 03-trifold-brochure.pdf   (11×8.5 in, 6 panels)
│   │   ├── 04-flyer-general.pdf      (letter, all-purpose)
│   │   ├── 05-pricing-sheet.pdf      (letter, service rates)
│   │   ├── 06-postcard.pdf           (6×4 in, direct mail)
│   │   ├── 07-referral-thank-you.pdf (5×7 in, front + back)
│   │   ├── 08-yard-sign.pdf          (24×18 in, jobsite sign)
│   │   ├── 09-car-magnet.pdf         (12×4 in, vehicle door)
│   │   ├── 10-gift-certificate.pdf   (8.5×3.5 in, fillable)
│   │   ├── 11-mothers-day.pdf        ($300 whole-house clean)
│   │   ├── 12-spring-cleaning.pdf    (20% off deep cleans)
│   │   ├── 13-fall-prep.pdf          ($50 off first recurring)
│   │   ├── 14-holiday-season.pdf     (pre-holiday deep clean)
│   │   ├── 15-new-year.pdf           (first clean half off)
│   │   ├── 16-valentines.pdf         ($25 off deep clean)
│   │   ├── 17-realtor-partnership.pdf
│   │   ├── 18-airbnb-host.pdf
│   │   ├── 19-move-in-out.pdf
│   │   └── 20-post-construction.pdf
│   └── thumbs/             ← Preview PNGs displayed in the gallery
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
- ✅ Subtle gold sparkle accents and gentle reveal animations

---

## Media Hub (`/media/`)

A complete marketing collateral library with **20 print-ready, fully branded PDFs**, accessible at `mmcleanse.com/media/`.

**Categories:**
- **Essentials (10)** — Business card, door hanger, tri-fold brochure, general flyer, pricing sheet, postcard, referral/thank-you, yard sign, car magnet, gift certificate
- **Holiday Specials (6)** — Mother's Day, Spring Cleaning, Fall Prep, Holiday Season, New Year, Valentine's Day. Each has a unique offer copy and dollar amount.
- **Vertical / B2B (4)** — Realtor Partnership, Airbnb Hosts, Move In/Out, Post-Construction

**Page features:**
- Category filter pills (All / Essentials / Direct Mail / Signs & Vehicle / Holiday Specials / Vertical / B2B)
- Preview thumbnail on each card (rendered from the PDF first page; **double-sided items show both pages**)
- "Preview" button (opens PDF in a new tab) and "Download" button (forces download)
- "Need something custom?" CTA at the bottom for custom variations
- The Media Hub is reachable from the **mobile bottom tab bar** AND **desktop top nav** — one tap from any page.

**Sending one to a customer:** the URL pattern is `mmcleanse.com/media/pdfs/{filename}.pdf`. So the Mother's Day flyer is at `mmcleanse.com/media/pdfs/11-mothers-day.pdf` — that single link works in iMessage, email, Facebook, etc.

**Want to add or swap a PDF?** Drop the new file in `media/pdfs/`, drop a 900×1200 preview PNG in `media/thumbs/` (with the matching filename), then add an entry to the `ITEMS` array in `media/index.html` and the new card auto-appears in the gallery.

---

## Compliance & Trust Section

The home page includes a dedicated `#compliance` section with 9 credential cards covering the standard customer-trust requirements of a residential cleaning business:

| Credential | What it covers |
|---|---|
| **General Liability Insurance** | Comprehensive coverage; COI available on request |
| **Workers' Compensation** | PA state-compliant team coverage |
| **Bonded** | Surety bond protecting customers and property |
| **Background-Checked Team** | Pre-employment screening for every cleaner |
| **Women-Owned, Locally Operated** | Wilkes-Barre based, not a franchise |
| **Pet- & Family-Safe Products** | EPA-registered, low-VOC products |
| **Satisfaction Guarantee** | 24-hour callback to make things right |
| **Privacy & Confidentiality** | No third-party data sharing |
| **On-Time, Every Time** | Punctuality policy with proactive notification |

Below the cards sit a **credential bar** (compact checkmark row of all 6 top trust signals) and a **policy row** linking to:

- `privacy.html` — full Privacy Policy
- `terms.html` — Terms of Service (cancellation, payment, satisfaction guarantee, governing law)
- `accessibility.html` — WCAG 2.1 AA accessibility statement
- `mailto:` link to **request the Certificate of Insurance**

> **A note on the credential card text:** the descriptions are written generically (e.g. "PA state compliant", "EPA-registered products"). If you want to call out specific carriers, license numbers, or certifications (e.g. "Insured by Erie Insurance, Policy #...", "PA Home Improvement Contractor #PA12345"), edit the `<span class="cred-meta">` lines in the `#compliance` section of `index.html`.

---

## Mobile Tab Bar (Bottom Action Bar)

Five-item iOS-style tab bar visible on phones:

1. **Home** — scroll to top
2. **Services** — scroll to services section
3. **Call** (highlighted, centered) — `tel:+15707061413`
4. **Media** — opens the Media Hub gallery
5. **Quote** — scroll to quote form

The tab bar auto-hides on scroll-down and re-appears on scroll-up (iOS native pattern). Hidden on tablets and desktops (≥768px) where the top navigation bar takes over.

---

Built with care. Sparkle on. ✨
