# Allura Usage

Design System 2.0 package guide for Open Design agents and reviewers.

## Read Order

1. Read this file first to understand the package contract.
2. Read `DESIGN.md` for visual intent, constraints, and anti-patterns.
3. Paste `tokens.css` into the first artifact `<style>` block before writing component CSS.
4. Use `components.manifest.json` for the compact component inventory; open `components.html` when exact selectors or states matter.
5. Inspect `preview/` pages when a visual sanity check is useful.

## Design Highlights

- Warm cream canvas (`#f6f3ec`) as the signature atmosphere — never pure white
- Paper-elevated cards (`#fffdf8`) lifting onto the cream canvas
- Single blue accent (`#2961b8`) for action and link semantics
- Warm semantic palette: green, orange, red, gold
- IBM Plex Sans + IBM Plex Mono typography
- Soft, rounded corners (8px default) and warm shadows
- Evidence-first: visible source/freshness/degraded-state badges, never fake metrics

## Do

- Preserve the schema token names exactly so cross-brand switching stays reliable.
- Use `--accent` (Allura blue) for primary actions, links, focus states, and one clear focal element.
- Use `--bg` (cream) as the page background — never pure white.
- Use `--fg` (charcoal) for primary text — never pure black.
- Reuse component groups from `components.manifest.json` before inventing new controls.
- Show evidence, provenance, or governance rather than fake metrics.
- Treat "unknown" as a valid state — do not claim healthy/live/done without proof.

## Avoid

- Avoid raw hex values outside the copied `:root` token block.
- Avoid redefining Tailwind or design-token values independently of `tokens.css`.
- Avoid pure white (`#ffffff`) as a page background — use cream.
- Avoid pure black (`#000000`) for text — use charcoal.
- Avoid purple AI gradients — Allura is warm, not cyberpunk.
- Avoid generated logos or logo-like marks — use real Allura assets only.
- Avoid fake metrics, vanity charts, or "healthy/live/done" claims without evidence.