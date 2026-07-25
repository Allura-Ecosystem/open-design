# Faith Meats Usage

Design System 2.0 package guide for Open Design agents and reviewers.

## Read Order

1. Read this file first to understand the package contract.
2. Read `DESIGN.md` for visual intent, constraints, and anti-patterns.
3. Paste `tokens.css` into the first artifact `<style>` block before writing component CSS.
4. Use `components.manifest.json` for the compact component inventory; open `components.html` when exact selectors or states matter.
5. Inspect `preview/` pages when a visual sanity check is useful.

## Design Highlights

- Snow canvas (`#FBF5F3`) as the primary page background — never pure white
- Night ink (`#0B0808`) for all text and headings — warm near-black
- Gold accent (`#C8AD55`) for dividers, borders, CTAs, highlights, emphasis
- 5 flavor colors for global flavor cueing (Shawarma, Harissa, Korean, Balinese, Sriracha)
- Crimson Pro (serif) headings + DM Sans (sans) body — craft editorial pairing
- Wide letter-spacing on tagline (0.2em-0.4em) for premium feel
- Subtle rounded corners (8px) — "not cartoonish"
- Thin Gold dividers (1px solid `#C8AD55`)
- Generous padding (2-3rem) — warm, breathable layout

## Do

- Preserve the schema token names exactly so cross-brand switching stays reliable.
- Use `--bg` (Snow) as the page background — never pure white.
- Use `--fg` (Night) for all text — never pure black.
- Use `--accent` (Gold) for dividers, borders, CTAs, highlights, emphasis.
- Use flavor color tokens (`--flavor-*`) for flavor cueing — each maps to a documented flavor.
- Use Crimson Pro for headings and DM Sans for body.
- Apply wide letter-spacing (`--tracking-tagline`) on the tagline for premium feel.
- Reuse component groups from `components.manifest.json` before inventing new controls.

## Avoid

- Avoid raw hex values outside the copied `:root` token block.
- Avoid redefining Tailwind or design-token values independently of `tokens.css`.
- Avoid pure white (`#FFFFFF`) as a page background — use Snow.
- Avoid pure black (`#000000`) for text — use Night.
- Avoid non-Gold dividers — dividers are thin Gold (`1px solid #C8AD55`).
- Avoid cartoonish rounded corners — 8px is the max default.
- Avoid corporate buzzwords ("synergy," "leverage," "optimize").
- Avoid aggressive sales language ("buy now," "limited time only").
- Avoid exclusionary religious language — halal is for everyone.
- Avoid generic stock photos — show real connections, diversity, active lifestyles.
- Avoid invented logos — use real Faith Meats assets only.

## Brand Verification Checklist

- [ ] Brand colors match exact hex values (Snow `#FBF5F3`, Night `#0B0808`, Gold `#C8AD55`)
- [ ] Flavor colors used correctly (Shawarma, Harissa, Korean, Balinese, Sriracha)
- [ ] Typography: Crimson Pro (headings) + DM Sans (body)
- [ ] Tagline present: "FAITH MEATS PREMIUM • HALAL JERKY"
- [ ] At least one slogan used ("A Snack You Can Believe In" or "Snacking Done Right")
- [ ] Real flavors referenced with cultural stories
- [ ] Tone matches all 9 voice pillars
- [ ] Halal certification + ethical sourcing mentioned
- [ ] Community/inclusivity messaging present
- [ ] "Globally Inspired." theme visible
- [ ] Contact: Sabir Asheed, sabir.asheed@faithmeats.com, Auburn WA