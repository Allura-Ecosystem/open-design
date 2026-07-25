---
name: allura-brand
description: |
  Apply Allura brand identity to artifacts — warm cream canvas, charcoal ink, Allura blue accent, IBM Plex Sans/Mono, evidence-first operator surfaces. Use for Allura Memory, Team RAM, RuVix, and Allura ecosystem work. Mandatory when the user says brand, on-brand, Allura visuals, dashboard, logo, colors, typography, or asks to stop generated logos.
triggers:
  - "allura brand"
  - "allura branding"
  - "on-brand allura"
  - "allura visuals"
  - "allura dashboard"
  - "allura memory command center"
  - "allura colors"
  - "allura typography"
  - "allura logo"
od:
  mode: design-system
  category: design-systems
  design_system:
    requires: true
    path: "../../design-systems/allura"
  craft:
    requires:
      - color
      - accessibility-baseline
---

# allura-brand

> Allura brand compliance skill — warm, governed, connected, evidence-first.

## What it does

Applies the Allura brand identity to any artifact. Allura is a governed memory engine for AI systems. The brand is warm, not cold; evidence-first, not hype; governed, not opaque.

## When to use

Use whenever work must follow Allura brand identity:
- README images, dashboard visuals, Memory Command Center UI
- Marketing/docs visuals, logo usage, color/token choices, copy voice
- Team Durham brand review for Allura work

## Brand core

- **Name in copy:** `allura` (always lowercase)
- **Title/legal:** `Allura Memory`
- **Tagline:** `MEMORY THAT SHOWS ITS WORK`
- **Positioning:** warm, connected, governed, auditable memory
- **Persona:** Maya, 31, Oakland, community organizer
- **Archetype:** Caregiver 50% · Creator 30% · Explorer 20%

## Visual system

Load tokens from `design-systems/allura/tokens.css`. Key rules:

- **Canvas:** Allura cream (`#f6f3ec`) — never pure white
- **Text:** Allura charcoal (`#1b1d21`) — never pure black
- **Accent:** Allura blue (`#2961b8`) — primary action, links, focus
- **Semantic:** green (`#298f57`), orange (`#f2752e`), red (`#bf332e`), gold (`#c89b3c`)
- **Typography:** IBM Plex Sans (display + body), IBM Plex Mono (code)
- **Radius:** 8px default — soft, rounded, not pill capsules
- **Shadows:** warm, soft (`rgba(27,29,33,0.06)`)

## Voice

Write like a warm, practical steward of memory.

**Use:** community, connection, belonging, together, warmth, inviting, welcoming, craft, care, celebrate, amplify, evidence, source, provenance, trust.

**Avoid:** "users" (→ "people"), frictionless, leverage, seamless, scalable, fake certainty, hype without proof, vague AI magic.

**Tone:** Formality 4/10 · Enthusiasm 6/10 · Technicality 3/10 · Humor 4/10.

## Anti-patterns (do not)

- No purple AI gradients — Allura is warm, not cyberpunk
- No dark cyberpunk panels
- No pure black text — use charcoal
- No pure white canvas — use cream
- No generated logos or logo-like marks — use real Allura assets only
- No fake metrics or vanity charts — show evidence, provenance, governance
- No "healthy/live/done" without proof — unknown is a valid state

## Memory Command Center rules

Every dashboard surface should show:
- active `group_id`
- source of truth
- freshness
- degraded state
- path to evidence

Every mutation surface should show or produce:
- intent, actor, source, policy, validation, audit receipt

## Logo and assets

Use real assets only. Known approved asset:
- `allura-memory/public/readme/allura-wordmark.png`

Do not create a new logo, mark, letterform, seal, mascot, or wordmark. If a logo asset is missing, say so and create a placeholder layout that reserves space for the real asset.

## Brand compliance checklist

- [ ] Real Allura asset used, or missing asset explicitly named
- [ ] No generated logos or logo-like marks
- [ ] Copy uses Allura voice and avoids banned phrases
- [ ] Colors/tokens trace back to Allura docs or approved assets
- [ ] Dashboard/README visuals show evidence, provenance, or governance
- [ ] Any claim of live/healthy/done has proof
- [ ] Accessibility: contrast, keyboard reachability, readable labels
- [ ] Degraded/unknown states visible when data is absent
- [ ] Project scope respected (Allura rules not applied to unrelated brands)