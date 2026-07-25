---
name: team-durham-brand-loop
description: |
  Team Durham brand production loop — STP positioning, visual direction, brand kit building, QA review, and evidence collection. Use for brand strategy, visual identity, brand kit creation, brand consistency review, and Team Durham workflows.
triggers:
  - "team durham"
  - "brand loop"
  - "brand strategy"
  - "brand kit"
  - "visual direction"
  - "brand consistency"
  - "brand review"
  - "aaker"
  - "ogilvy"
  - "glaser"
  - "munari"
od:
  mode: utility
  category: brand-production
---

# team-durham-brand-loop

> Team Durham brand production loop — strategy, visual, kit, QA, evidence.

## What it does

Runs the Team Durham brand production pipeline: Aaker (strategy) → Ogilvy (copy) → Glaser (visual) → Rand (kit) → Munari (QA) → Tufte (data). Each specialist owns their domain; the brand orchestrator coordinates.

## When to use

- Brand strategy and positioning (STP framework)
- Visual direction and identity systems
- Brand kit creation (10-section brand kits)
- Brand consistency review
- Copy and messaging work
- Brand presentation building

## The team

| Agent | Role | When to invoke |
|-------|------|----------------|
| **Aaker** | Brand Strategist | STP, positioning, brand personality, strategy packs |
| **Ogilvy** | Copywriter | Naming, taglines, copy packs, voice guides, messaging |
| **Glaser** | Visual Director | Visual direction, logo systems, color/typography exploration |
| **Rand** | Brand Kit Builder | 10-section brand kits, design tokens, production specs |
| **Munari** | QA Reviewer | Brand consistency, accessibility, usability, production readiness |
| **Tufte** | Data Analyst | Competitive intelligence, market research, claim validation |

## Pipeline

```
1. Aaker — define strategic positioning and voice
2. Ogilvy — craft copy, naming, messaging
3. Glaser — define visual hierarchy, palette, typography
4. Rand — build the 10-section brand kit
5. Munari — audit usability, accessibility, consistency
6. Tufte — validate claims with evidence
```

## Brand kit structure (10 sections)

1. Brand strategy (positioning, personality, archetype)
2. Visual direction (logo system, color, typography)
3. Voice and messaging
4. Design tokens (colors, type scale, spacing, radius)
5. Component library
6. Application examples
7. Accessibility rules
8. Production specs
9. Implementation guide
10. Brand compliance checklist

## Allura dashboard branding gate

Before Allura Dashboard UI work is declared ready, dispatch Team Durham:

1. **Aaker** — strategic positioning and voice for the dashboard surface
2. **Glaser** — visual hierarchy, palette usage, spacing rhythm, interface tone
3. **Munari** — audit usability, accessibility, consistency, production readiness
4. **Reality Checker / Evidence Collector** — verify claims with screenshots or artifact proof

If the task involves agent identity, authorization, trust, or audit UX, also dispatch:
5. **Agentic Trust Architect** — verify role, permission, evidence, delegation, audit language
6. **Workflow Architect** — verify state machine, handoff, empty/degraded/blocked states

## Required artifact sections

Durham's output must be a concrete rules artifact, not vibes:
- Dashboard positioning statement
- Visual principles (hierarchy, density, whitespace, surface depth, motion restraint)
- Token rules (approved semantic tokens, forbidden hardcoded values, contrast constraints)
- Component rules (cards, tables, nav, warnings, evidence panels, policy controls)
- State rules (loading, empty, degraded, blocked, denied, escalated, success)
- Copy rules (mission-control tone, no fake certainty, no inflated claims, no marketing fluff)
- Evidence rules (every "done"/"verified" claim links to proof)
- Accessibility rules (AA contrast minimum, visible focus, keyboard paths, screen-reader-safe labels)
- Anti-drift rules (explicit list of forbidden tokens/phrases/styles)

## group_id

Team Durham work uses `group_id: allura-team-durham`.

## RuVix enforcement

RuVix must reject or escalate brand work when:
- The artifact uses forbidden brand tokens or language
- A UI change lacks a source-of-truth doc or Notion card
- A "ready/done/ship" claim lacks evidence
- A governed action lacks audit, permission, or separation-of-duties consideration
- Copy implies certainty when an API/store is degraded
- Any direct mutation bypasses the approved audit wrapper or policy check