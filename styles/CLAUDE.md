# SLDS Styling Reference

Guidance for selecting and applying Salesforce Lightning Design System (SLDS) styles. The authoritative source for SLDS v1 is the `design-system` sibling repo and the online docs.

## Quick Reference: Online Docs

- **Component blueprints** (markup, variants, states): https://www.lightningdesignsystem.com/components/overview/
- **Utility classes** (margin, padding, sizing, text, etc.): https://www.lightningdesignsystem.com/utilities/
- **Design tokens**: https://www.lightningdesignsystem.com/design-tokens/
- **Styling hooks (CSS custom properties)**: https://www.lightningdesignsystem.com/components/styling-hooks/
- **Grid system**: https://www.lightningdesignsystem.com/utilities/grid/
- **Icons** (see `../slds-icons/`): https://www.lightningdesignsystem.com/icons/

## Local Source: design-system repo

The `../design-system/` repo is the SLDS v1 source. Key directories for styling:

| Path | What's there |
|------|-------------|
| `styling-hooks/` | CSS custom property definitions (~307 hooks) with type, syntax, scope, and accessibility comments |
| `design-tokens/primitive/` | Core token scales: 13 color palettes, spacing (NONE–XX_LARGE), font sizes/weights, border-radius, shadows, z-index |
| `design-tokens/aliases/` | Semantic aliases resolving to primitives (e.g., `SPACING_MEDIUM` → `1rem`) |
| `design-tokens/extensions/` | Theme-specific overrides for ui-force, ui-analytics, ui-marketing, ui-one |
| `ui/components/*/tokens/` | Per-component token overrides (91 files across 36 components) |
| `guidelines/SASS_CONVENTIONS.md` | Property ordering, BEM naming, nesting rules |

## Styling Conventions

All SLDS classes are prefixed with `slds-`. Use BEM naming:
- `.slds-block` — component
- `.slds-block__element` — descendant (double underscore)
- `.slds-block_modifier` — variant/state (single underscore)

CSS property ordering: mixins → appearance → layout → sizing → spacing → masking → typography → theming → interaction → animations.

## Token Hierarchy

Tokens cascade from general to specific. Prefer the most specific available:

1. **Component tokens** (`ui/components/*/tokens/`) — use when styling a specific SLDS component
2. **Semantic aliases** (`design-tokens/aliases/`) — e.g., `$spacing-medium`, `$font-size-large`
3. **Primitives** (`design-tokens/primitive/`) — raw palette values; avoid using directly in components

## Common Token Categories

| Category | Prefix | Example |
|----------|--------|---------|
| Spacing | `$spacing-` | `$spacing-medium` (1rem) |
| Font size | `$font-size-` | `$font-size-medium` |
| Font weight | `$font-weight-` | `$font-weight-bold` |
| Color | `$color-` | `$color-text-default` |
| Background | `$color-background-` | `$color-background-button-default` |
| Border | `$border-width-`, `$border-radius-` | `$border-radius-medium` |
| Shadow | `$shadow-` | `$shadow-drop-down` |
| Sizing | `$size-`, `$square-` | `$size-medium` |

## Key Rules

- Prefer SLDS utility classes over custom CSS when possible
- Use design tokens (not raw values) for colors, spacing, sizing, and typography
- Do not use `!important` reactively — only on utility/helper classes
- Do not use IDs for styling
- Keep selector nesting to 3 levels max
- Scope custom overrides with your own class, don't restyle SLDS classes directly:
  ```html
  <article class="slds-card myCard">...</article>
  ```
  ```css
  .myCard { background: white; }
  ```
