---
name: faith-meats-brand
description: |
  Apply Faith Meats brand identity to artifacts — Snow canvas, Night ink, Gold accent, Crimson Pro + DM Sans typography, 5 flavor colors for global flavor cueing. Use for Faith Meats newsletters, company overviews, invoices, social posts, landing pages, and any Faith Meats branded content.
triggers:
  - "faith meats"
  - "faithmeats"
  - "halal jerky"
  - "faith meats brand"
  - "faith meats newsletter"
  - "faith meats invoice"
  - "sabir asheed"
  - "globally inspired"
od:
  mode: design-system
  category: design-systems
  design_system:
    requires: true
    path: "../../design-systems/faithmeats"
  craft:
    requires:
      - color
      - typography
      - accessibility-baseline
---

# faith-meats-brand

> Faith Meats brand content skill — premium halal beef jerky, globally inspired.

## What it does

Generates on-brand content and documents for Faith Meats Inc. — a premium halal beef jerky brand founded on ethical sourcing, global culinary exploration, and community.

## When to use

Use whenever the user asks to:
- Write copy, newsletters, emails for Faith Meats
- Create brand documents, company overviews, grant applications
- Generate social posts, landing pages, or marketing material
- Apply Faith Meats brand colors/voice to any content
- Reference "Faith Meats," "faith meats brand," "halal jerky," Sabir Asheed

## Brand identity

| Element | Value |
|---------|-------|
| **Brand Name** | `FAITH MEATS` |
| **Tagline** | `FAITH MEATS PREMIUM • HALAL JERKY` |
| **Slogans** | `"A Snack You Can Believe In"` · `"Snacking Done Right"` |
| **Product** | Premium halal beef jerky — All Natural Angus Beef |
| **Company** | Faith Meats, S.Corp | Auburn, WA 98002 |
| **Founder/CEO** | Sabir Asheed — sabir.asheed@faithmeats.com |
| **Positioning** | Elevating the jerky market through globally inspired recipes, premium Angus beef, and transparent, ethical production |
| **Tagline (imagery)** | "Globally Inspired." |

## Visual system

Load tokens from `design-systems/faithmeats/tokens.css`. Key rules:

- **Canvas:** Snow (`#FBF5F3`) — never pure white
- **Text:** Night (`#0B0808`) — warm near-black, never pure black
- **Accent:** Gold (`#C8AD55`) — dividers, borders, CTAs, highlights
- **Flavor colors:** 5 documented colors for flavor cueing
- **Typography:** Crimson Pro (headings, serif) + DM Sans (body, sans)
- **Tagline tracking:** wide (0.2em-0.4em) for premium feel
- **Radius:** 8px default — subtle, not cartoonish
- **Dividers:** thin Gold (`1px solid #C8AD55`)

## Flavor colors

| Flavor | Token | Hex | Inspiration |
|--------|-------|-----|-------------|
| Shawarma | `--flavor-shawarma` | `#2B4E27` | Middle Eastern — Cal Poly Green |
| Harissa Beef | `--flavor-harissa` | `#A3320B` | Moroccan — Brown |
| Korean BBQ | `--flavor-korean` | `#4C1A54` | Korean — Russian Violet |
| Balinese Curry | `--flavor-balinese` | `#D46313` | Balinese — Cocoa Brown |
| Honey Sriracha | `--flavor-sriracha` | `#C1292E` | Fusion — Fire Engine Red |

## Voice

Warm and genuine, with a passion for quality, ethics, and bringing positivity into people's snacking experiences.

**Pillars:** Authentic, Approachable, Conscientious, Adventurous, Inclusive, Inspiring, Knowledgeable, Positive, Purpose-driven.

**Must-Never-Use:**
- Corporate buzzwords ("synergy," "leverage," "optimize")
- Religious preaching or exclusionary language
- Overly technical halal terminology without explanation
- Aggressive sales language ("buy now," "limited time only")
- Any suggestion that halal is only for Muslim consumers
- Generic stock-photo imagery — show real connections, diversity, active lifestyles

## Content templates

### Newsletter
1. Header — Tagline + brand name + slogan + "Globally Inspired."
2. Welcome — Ethical sourcing, premium Angus beef, halal certification
3. Global Flavor Journey — All 5 flavors with cultural stories. Use flavor colors as badges
4. Health & Nutrition — Dietary icons: Zabiha Halal, Paleo, Whole30, Gluten Free, 0 Sugar, Low Fat
5. Community Connection — Diverse people united by food. Real stories, real voices
6. Adventure Fuel — Active lifestyles (hiking, cycling, yoga, road trips)
7. Footer — Slogan, contact, "Globally Inspired."

### Company Overview (Grant/Investor)
1. Header — Tagline + brand name + slogan
2. Mission & Vision — Purpose-driven, ethical sourcing, premium halal Angus beef
3. Market Need & Community Impact — Serving halal + broader health-conscious communities
4. Product Line — All 5 flavors with cultural inspiration
5. Leadership — Sabir Asheed, CEO, Auburn WA
6. Growth Initiative — Launch, marketing, reaching communities
7. Closing — Slogan + tagline

### Invoice
1. Accent Bar — 6-color gradient stripe (Gold → Green → Brown → Violet → Cocoa → Red)
2. Header — Brand info + invoice number + dates
3. From/Bill To — Company + client details
4. Line Items — Products with flavor color dots, qty, pricing
5. Totals — Subtotal, shipping, discounts, tax, total due
6. Payment Bar — Dark background with Net terms and due amount
7. Footer — Slogan + company info

## HTML coding standards

- HTML5 semantic layout (`<header>`, `<section>`, `<footer>`)
- Max content width: 640px (newsletters), 800px (documents/invoices)
- All CSS embedded in `<style>` inside `<head>` — no external files (except Google Fonts CDN)
- Google Fonts import: Crimson Pro + DM Sans
- Section spacing: generous padding (2-3rem)
- Rounded corners: 8px — subtle, not cartoonish
- Dividers: thin gold `1px solid #C8AD55`
- Responsive: `@media` queries for mobile
- Print: `@media print` rules to hide non-essential UI

## Verification checklist

- [ ] Brand colors match exact hex values (Snow `#FBF5F3`, Night `#0B0808`, Gold `#C8AD55`)
- [ ] Flavor colors used correctly
- [ ] Typography: Crimson Pro (headings) + DM Sans (body)
- [ ] Tagline present: "FAITH MEATS PREMIUM • HALAL JERKY"
- [ ] At least one slogan used
- [ ] Real flavors: Shawarma, Harissa Beef, Korean BBQ, Balinese Curry, Honey Sriracha
- [ ] Each flavor has its cultural story
- [ ] Tone matches all 9 voice pillars
- [ ] Halal certification + ethical sourcing mentioned
- [ ] Community/inclusivity messaging present
- [ ] Dietary badges included
- [ ] "Globally Inspired." theme visible
- [ ] Contact: Sabir Asheed, sabir.asheed@faithmeats.com, Auburn WA
- [ ] HTML is self-contained — no broken links
- [ ] Responsive layout works on mobile