# Design System: Faith Meats

> Category: Food & Beverage
> Premium halal beef jerky. Globally inspired, ethically sourced, community-rooted.

## 1. Visual Theme & Atmosphere

Faith Meats' web language is a warm editorial system built around a Snow canvas, Night ink, and a Gold accent. The visual tone is warm, genuine, and premium — never corporate, never aggressive. The interface is engineered to feel like a craft food brand: ethical sourcing, global culinary exploration, and community connection.

Across newsletters, company overviews, and invoices, the rhythm is consistent: Snow backgrounds, generous padding (2-3rem), thin Gold dividers, and flavor colors as section accents and badges. The result is one system with two gears: editorial mode (newsletters, company overviews) and transaction mode (invoices, order forms).

Typography is the stabilizer. Crimson Pro carries hero and heading hierarchy with wide letter-spacing on the tagline for premium feel, while DM Sans handles body copy, navigation, and dense commerce text. The typography stays warm and readable, with a serif/sans pairing that signals craft and quality.

**Key Characteristics:**
- Snow canvas (`#FBF5F3`) as the primary page background — never pure white
- Night ink (`#0B0808`) for all text and headings — warm near-black
- Gold accent (`#C8AD55`) for dividers, borders, CTAs, highlights, emphasis
- 5 flavor colors for global flavor cueing (Shawarma, Harissa, Korean, Balinese, Sriracha)
- Crimson Pro (serif) headings + DM Sans (sans) body — craft editorial pairing
- Wide letter-spacing on tagline (0.2em-0.4em) for premium feel
- Subtle rounded corners (8px) — "not cartoonish" per guidelines
- Thin Gold dividers (1px solid `#C8AD55`)
- Generous padding (2-3rem) — warm, breathable layout

## 2. Color Palette & Roles

> **Source:** Faith Meats Brand Guidelines (official) + `faith-meats-brand-content` skill

### Primary Colors
- **Snow** (`#FBF5F3`): Always the primary page background. Never use pure white.
- **Night** (`#0B0808`): Always body text and headings. Warm near-black.
- **Gold** (`#C8AD55`): Accents — dividers, borders, CTAs, highlights, emphasis.

### Flavor Colors (Secondary)
Each maps to a global flavor for visual cueing. Use as section accents, badges, or decorative elements.

| Flavor | Token | Hex | Cultural Inspiration |
|--------|-------|-----|---------------------|
| **Shawarma** | `--flavor-shawarma` | `#2B4E27` | Middle Eastern — Cal Poly Green |
| **Harissa Beef** | `--flavor-harissa` | `#A3320B` | Moroccan — Brown |
| **Korean BBQ** | `--flavor-korean` | `#4C1A54` | Korean — Russian Violet |
| **Balinese Curry** | `--flavor-balinese` | `#D46313` | Balinese/Indonesian — Cocoa Brown |
| **Honey Sriracha** | `--flavor-sriracha` | `#C1292E` | Fusion — Fire Engine Red |

### Color Applications
- **Background:** Snow (`#FBF5F3`) — always the primary page background
- **Text:** Night (`#0B0808`) — always body text and headings
- **Accents:** Gold (`#C8AD55`) — dividers, borders, CTAs, highlights, emphasis
- **Flavor colors** — section accents, badges, decorative elements
- **Logo on Snow** — standard full-color logo
- **Logo on Gold** — white/negative space treatment
- **Logo on Night** — gold/light treatment

### Semantic (mapped from flavor palette)
- **Success** (`#2B4E27`): Cal Poly Green (Shawarma flavor color)
- **Warning** (`#D46313`): Cocoa Brown (Balinese flavor color)
- **Danger** (`#C1292E`): Fire Engine Red (Sriracha flavor color)
- **Gold** (`#C8AD55`): Highlight/badge semantic

## 3. Typography Rules

### Font Family
- **Headings:** Crimson Pro (Bold, SemiBold) — `h1`-`h4`, hero text, pull quotes
- **Body:** DM Sans (Regular, Light) — body paragraphs, descriptions, navigation
- **Mono:** JetBrains Mono — code, receipts, technical metadata

> **Note:** Basic Sans is the documented brand body font but isn't on Google Fonts. DM Sans (or Nunito Sans) is the approved web substitute.

### Type Scale (px)
| Token | Size | Use |
|-------|------|-----|
| `--text-xs` | 12px | Micro UI — fine print |
| `--text-sm` | 14px | Control Label — buttons, helper labels |
| `--text-base` | 16px | Body Primary — reading baseline |
| `--text-lg` | 18px | Action Heading |
| `--text-xl` | 24px | Card/Product Title |
| `--text-2xl` | 32px | Section Heading |
| `--text-3xl` | 44px | Hero Display L |
| `--text-4xl` | 56px | Hero Display XL — max hero |

### Leading
- Body: 1.65 (airy, readable)
- Display: 1.15 (tight, editorial)

### Tracking
- Display: -0.015em (slight compression for headlines)
- Tagline: 0.2em-0.4em (wide, premium feel) — use `--tracking-tagline: 0.3em`

### Usage
- **Crimson Pro Bold** — `h1`-`h4`, hero text, pull quotes
- **Crimson Pro SemiBold** — secondary headings, emphasis
- **DM Sans Regular** — body paragraphs, descriptions, navigation
- **DM Sans Bold** — strong emphasis, CTAs, labels
- Gold color accent on key headings or taglines
- Wide letter-spacing on the tagline for premium feel

## 4. Spacing

4px base grid. Generous padding (2-3rem) per brand guidelines. Scale: 4, 8, 12, 16, 24, 32, 48, 64.

## 5. Radius

Subtle rounded corners — "not cartoonish" per guidelines.
- `--radius-sm`: 4px (inputs, small controls)
- `--radius`: 8px (default — cards, buttons)
- `--radius-lg`: 12px (elevated cards)
- `--radius-xl`: 16px (modals, large surfaces)
- `--radius-pill`: 9999px (badges, tags only)

## 6. Shadow

Soft, warm shadows.
- `--shadow-sm`: 0 1px 2px rgba(11,8,8,0.05)
- `--shadow`: 0 4px 12px rgba(11,8,8,0.08)
- `--shadow-lg`: 0 18px 40px rgba(11,8,8,0.10)

## 7. Dividers

Thin Gold dividers — `1px solid #C8AD55`. The signature separator across all surfaces.

## 8. Brand Personality

| Trait | Meaning |
|-------|---------|
| **Principled** | Strong values of integrity, care, and social responsibility |
| **Mindful** | Considerate of sustainability, ethical sourcing, carbon footprint |
| **Adventurous** | Creative flavors, taste exploration, bridging cultures |
| **Discerning** | Selective about ingredients, production methods |
| **Nurturing** | Focused on nourishing customers, providing high-quality nutrition |
| **Confident** | Believes in redefining/elevating the jerky market |
| **Celebratory** | Positive, brings people together, celebratory of diversity |

## 9. Voice

Warm and genuine, with a passion for quality, ethics, and bringing positivity into people's snacking experiences.

| Pillar | How It Sounds |
|--------|---------------|
| **Authentic** | Speak genuinely about values, ingredients, and sourcing. |
| **Approachable** | Friendly yet confident. "Whether you grew up with shawarma after Friday prayers or you're discovering it for the first time..." |
| **Conscientious** | Considerate of ethics, sustainability, responsible practices. |
| **Adventurous** | Sense of exploration, excitement for new flavors. "Let our jerky transport you." |
| **Inclusive** | Celebratory of diversity, bringing people together. |
| **Inspiring** | Motivates people to live actively and eat/snack well. |
| **Knowledgeable** | Expertise on nutrition, ingredients, processes. |
| **Positive** | Upbeat, passionate, constructive tone. No negativity. |
| **Purpose-driven** | Committed to meaningful principles. Mindful, ethical eating. |

### Must-Never-Use
- Corporate buzzwords ("synergy," "leverage," "optimize")
- Religious preaching or exclusionary language
- Overly technical halal terminology without explanation
- Aggressive sales language ("buy now," "limited time only")
- Any suggestion that halal is only for Muslim consumers
- Generic stock-photo imagery — always show real connections, diversity, active lifestyles

## 10. Anti-Patterns (Do Not)

- **No pure white canvas.** Use Snow (`#FBF5F3`) — white erases the warm brand atmosphere.
- **No pure black text.** Use Night (`#0B0808`) — it's a warm near-black.
- **No non-Gold dividers.** Dividers are thin Gold (`1px solid #C8AD55`).
- **No cartoonish rounded corners.** 8px is the max default — subtle, not playful.
- **No corporate buzzwords.** See Must-Never-Use list above.
- **No aggressive sales language.** The tone is warm and genuine, not pushy.
- **No exclusionary religious language.** Halal is for everyone, not only Muslim consumers.
- **No generic stock photos.** Show real connections, diversity, active lifestyles.
- **No invented logos.** Use real Faith Meats assets only.

## 11. Global Flavors (Product Line)

| Flavor | Color | Cultural Inspiration | Story Angle |
|--------|-------|---------------------|-------------|
| **Shawarma** | Cal Poly Green (`#2B4E27`) | Middle Eastern | Nostalgia for shawarma after Friday prayers. Aromatic, meaty, portable homage. |
| **Harissa Beef** | Brown (`#A3320B`) | Moroccan | Smoky marketplace aromas, slow-roasted spices, family heritage. |
| **Korean BBQ** | Russian Violet (`#4C1A54`) | Korean | Tribute to a fallen friend Jay. Fans requested this — taste of K-Town grill. |
| **Balinese Curry** | Cocoa Brown (`#D46313`) | Balinese/Indonesian | Inspired by a beloved family member's homeland. Island flavors, family recipes. |
| **Honey Sriracha** | Fire Engine Red (`#C1292E`) | Fusion | The iconic rooster sauce story. Sweet honey + chili heat. |

## 12. Brand Identity

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