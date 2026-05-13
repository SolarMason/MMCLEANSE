# NEPA-PRO Clean — clean.nepa-pro.com

Sister site to lawncare.nepa-pro.com. Same architecture, broader service catalog.

## Quick deploy

Drop the contents of this folder at the root of `clean.nepa-pro.com` (Cloudflare Pages, Vercel, Netlify, etc.). No build step. No backend.

## File map

```
index.html              # Full SPA (88 KB)
manifest.json           # PWA manifest
service-worker.js       # Cache-first PWA SW
sitemap.xml             # SEO
robots.txt              # Allow all major + AI crawlers
llms.txt                # AI/LLM summary
PRICING_LOGIC.md        # Profit math for every cell
assets/
  ├─ icon-180/192/512.png + maskable
  ├─ apple-touch-icon.png
  ├─ favicon-16/32.png
  ├─ og-image.png + .jpg     # 1200×630
  └─ qr.svg + qr.png         # QR to clean.nepa-pro.com
```

## What this scores

- **SEO**: Comprehensive meta + canonical + og:* + twitter:*, JSON-LD HouseCleaningService + Service (with 32 offers) + FAQPage, sitemap.xml, robots.txt with all major bots whitelisted, semantic HTML5, alt text everywhere, fast (single file, inline CSS, no blocking JS).
- **AI/LLM search**: llms.txt summary, FAQ structured data, plain-language Q&A copy, ClaudeBot/GPTBot/PerplexityBot allowed.
- **PWA**: Standalone display, maskable icons, theme color, shortcuts, install prompt UI, service worker with offline shell, beforeinstallprompt handled.
- **iOS native feel (mobile)**: SF Pro font stack, backdrop-blur top bar, segmented control for frequency picker, safe-area-inset padding, pill buttons, accordion FAQ, tap haptic-style press states.
- **Desktop (≥ 1024px)**:
  - Sticky backdrop-blurred nav with hover-and-click mega menus
  - **Recurring mega menu** — 4×3 pricing matrix (12 cells, all direct-to-Stripe)
  - **One-Time mega menu** — 3 columns × 3–4 tiers (Deep, Move-In/Out, Airbnb)
  - **Specialty mega menu** — 3 columns × 3 tiers (Construction, Clean-Out, Organizing)
  - **Service Area mega menu** — cities pill-grid + coverage info
  - Hero splits 2-col with Quick-Pick Weekly card on right
  - Packages 2×2, services 2×2, values 3-col, footer 3-col, FAQ 2-col
- **Profit**: every cell verified ≥$65/hr net (lowest $71.43/hr — XL Monthly recurring). See `PRICING_LOGIC.md` for full math.

## Stripe references

All IDs in this site come from the live `acct_*` you're logged into. To update a price, edit the unit_amount on the relevant Stripe `price_*` and the site picks it up — no code change needed, since the displayed amount mirrors the data passed to the payment link.

### Products (10)
| Service | Product ID |
|---|---|
| Small Recurring | prod_UVk9Is29eiLVV1 |
| Medium Recurring | prod_UVkAhmBGmmwCYr |
| Large Recurring | prod_UVkAWPQS0cb5UO |
| XL Recurring | prod_UVkAq5Wd4Y66kq |
| Deep Cleaning | prod_UVkAUsYlZsM9hL |
| Move-In/Out | prod_UVkAWU8geel2ba |
| Airbnb Turnover | prod_UVkAN4Oo3ZUhPW |
| Post-Construction | prod_UVkAjCWvVsEF38 |
| Clean-Out | prod_UVkA1tKC3zMMQf |
| Organizing | prod_UVkAgreOds1GR7 |

### Payment links (32) — full URL list

**Recurring:**
- Small: $125 Weekly / $140 Bi-Weekly / $175 Monthly
- Medium: $195 / $225 / $275
- Large: $275 / $315 / $375
- XL: $395 / $445 / $525

**Deep:** $255 / $415 / $575 / $815
**Move-In/Out:** $275 / $445 / $615 / $865
**Airbnb:** $175 / $265 / $345
**Post-Construction:** $545 / $895 / $1,395
**Clean-Out:** $445 / $895 / $1,795
**Organizing:** $245 / $475 / $925

All payment links are embedded in `index.html` inside the JS data objects (`RECURRING`, `DEEP`, `MOVE`, `AIRBNB`, `CONSTRUCTION`, `CLEANOUT`, `ORGANIZING`). The same data drives the mobile cards, the desktop mega menus, the hero quick-pick, and the JSON-LD `Service.offers`.

## Brand voice & messaging

- **Tone**: confident, transparent, direct. No fluff, no superlatives.
- **Trust signals**: insured, bonded, background-checked, veteran owned, all-electric work vehicle (NEPA-PRO fleet).
- **Cross-promote with lawn care**: footer link + FAQ bundle-discount mention (10% off).
- **Custom job CTA**: hourly rate displayed ($85/hr / $145/hr 2-crew, 2hr minimum) with phone/text/email options.

## Updating prices

1. Open Stripe Dashboard → Products → select the service
2. Archive the old price, create a new one
3. Recreate the payment link with the new price
4. Edit `index.html` — replace the `url` and `amount` in the relevant data object
5. Redeploy

No CSS/HTML changes needed for price updates. The JS rebuilds everything from data.

## Contact

Noel Segui · 570-677-7971 · noel@solarmason.com · NEPA-PRO Clean · Clarks Summit, PA
