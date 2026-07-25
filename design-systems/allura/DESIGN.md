# Design System: Allura

> Category: Technology & Memory
> Warm, governed, connected, evidence-first. The AI memory layer for real life.

## 1. Visual Theme & Atmosphere

Allura's web language is a warm editorial system built around cream canvases, charcoal ink, and a restrained blue accent. The visual tone stays warm and human — never cold, cyberpunk, or generic AI SaaS. The interface is engineered to feel like a Memory Command Center: evidence-first, governed, auditable.

Across the Allura Memory dashboard and brand surfaces, the rhythm is consistent: warm cream backgrounds, paper-elevated cards, visible source/freshness/degraded-state badges, and calm control surfaces instead of decorative charts. The result is one system with two gears: operator mode (dense governance surfaces) and editorial mode (warm marketing/README moments).

Typography is the stabilizer. IBM Plex Sans carries hero and body hierarchy with compact line heights and controlled tracking, while IBM Plex Mono handles code, audit receipts, and technical metadata. The typography stays understated, but the scale range is wide enough to support both hero messaging and micro utility labels.

**Key Characteristics:**
- Warm cream canvas (`#f6f3ec`) as the signature atmosphere — never pure white
- Paper-elevated cards (`#fffdf8`) lifting onto the cream canvas
- Single blue accent family for action and link semantics (`#2961b8`)
- Warm semantic palette: green (`#298f57`), orange (`#f2752e`), red (`#bf332e`), gold (`#c89b3c`)
- Visible source/freshness/degraded-state badges — never fake metrics
- Calm control surfaces instead of decorative charts
- Soft, rounded corners (8px default) — not pill capsules
- Warm shadows (`rgba(27,29,33,0.06)`) — not harsh black drops
- IBM Plex Sans + IBM Plex Mono — the documented Allura families

## 2. Color Palette & Roles

> **Source:** `allura-memory/src/app/globals.css`, `docs/allura/BLUEPRINT.md` §0 Brand Identity, `docs/allura/DESIGN-ALLURA.md`

### Primary
- **Allura Cream** (`#f6f3ec`): Main canvas — the signature warm atmosphere. Never use pure white as the page background.
- **Allura Paper** (`#fffdf8`): Card and elevated surface — warm near-white that lifts onto the cream canvas.
- **Allura Charcoal** (`#1b1d21`): Primary text and dark-fill control color. Never use pure black — it fights the cream.

### Secondary & Accent
- **Allura Blue** (`#2961b8`): Primary action fill, links, focus states. The system's only persistent chromatic move for action semantics.
- **Allura Orange** (`#f2752e`): Warning/attention semantic, dashboard accent.
- **Allura Green** (`#298f57`): Success/healthy semantic.
- **Allura Red** (`#bf332e`): Error/destructive semantic.
- **Allura Gold** (`#c89b3c`): Highlight/badge semantic.

### Surface & Background
- **Surface Warm** (`#fbf8f0`): Intermediate tier between cream and paper.
- **Border** (`#d1c7b2`): Warm cream-aligned divider — the default card edge.
- **Border Soft** (`#e4dccb`): Lighter inner row separator.

### Neutrals & Text
- **Foreground 2** (`#374151`): Secondary text.
- **Muted** (`#6b6e73`): Helper copy, tertiary metadata.
- **Meta** (`#9ca3af`): Faint captions, micro labels.

### Semantic & Accent
- **Success** (`#298f57`): Healthy/permit states.
- **Warn** (`#f2752e`): Attention/defer states.
- **Danger** (`#bf332e`): Error/deny states.
- **Gold** (`#c89b3c`): Highlight/badge states.

### Gradient System
- Allura is overwhelmingly solid-surface driven. Visual richness comes from evidence cards, provenance flows, and audit receipts — not UI gradients. Avoid purple AI gradients entirely.

## 3. Typography Rules

### Font Family
- **Display:** IBM Plex Sans (hero, merchandising headings)
- **Body:** IBM Plex Sans (navigation, controls, dense copy)
- **Mono:** IBM Plex Mono (code, audit receipts, technical metadata)

### Type Scale (px)
| Token | Size | Use |
|-------|------|-----|
| `--text-xs` | 12px | Micro UI — fine print, micro labels |
| `--text-sm` | 14px | Control Label — buttons, helper labels |
| `--text-base` | 16px | Body Primary — reading baseline |
| `--text-lg` | 18px | Link/Action Heading |
| `--text-xl` | 24px | Card/Product Title |
| `--text-2xl` | 32px | Section Heading |
| `--text-3xl` | 40px | Hero Display L |
| `--text-4xl` | 48px | Hero Display XL — max hero |

### Leading
- Body: 1.6 (airy, readable)
- Display: 1.1 (tight, machined)

### Tracking
- Display: -0.01em (slight compression for headlines)
- Body: 0 (default)

## 4. Spacing

4px base grid. Scale: 4, 8, 12, 16, 24, 32, 48, 64.

## 5. Radius

- `--radius-sm`: 4px (inputs, small controls)
- `--radius`: 8px (default — cards, buttons)
- `--radius-lg`: 12px (elevated cards)
- `--radius-xl`: 16px (modals, large surfaces)
- `--radius-pill`: 9999px (badges, tags only — not buttons)

## 6. Shadow

Soft, warm shadows — never harsh black drops.
- `--shadow-sm`: 0 1px 2px rgba(27,29,33,0.04)
- `--shadow`: 0 4px 12px rgba(27,29,33,0.06)
- `--shadow-lg`: 0 18px 40px rgba(27,29,33,0.06)

## 7. Anti-Patterns (Do Not)

- **No purple AI gradients.** Allura avoids the generic AI SaaS look.
- **No dark cyberpunk panels.** The atmosphere is warm, not cold.
- **No pure black text.** Use charcoal (#1b1d21) — pure black fights the cream.
- **No pure white canvas.** Use cream (#f6f3ec) — white erases the brand atmosphere.
- **No generated logos or logo-like marks.** Use real Allura assets only.
- **No fake metrics or vanity charts.** Show evidence, provenance, or governance.
- **No "healthy/live/done" without proof.** Unknown is a valid state.
- **No broad secondary accent palettes** that compete with Allura blue.

## 8. Voice (Copy)

Write like a warm, practical steward of memory.

**Use:** community, connection, belonging, together, warmth, inviting, welcoming, craft, care, celebrate, amplify, evidence, source, provenance, trust.

**Avoid:** "users" (→ "people"), frictionless, leverage, seamless, scalable, fake certainty, hype without proof, vague AI magic.

**Tone target:** Formality 4/10 · Enthusiasm 6/10 · Technicality 3/10 · Humor 4/10.

## 9. Memory Command Center Rules

Every dashboard surface should show:
- active `group_id`
- source of truth
- freshness
- degraded state
- path to evidence

Every mutation surface should show or produce:
- intent
- actor
- source
- policy
- validation
- audit receipt

Do not call anything healthy, live, synced, or done unless there is evidence. Unknown is a valid state.