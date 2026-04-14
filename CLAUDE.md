# SLDS (Salesforce Lightning Design System)

This directory contains SLDS v1 source and LLM-oriented reference material for styling, icons, and component selection.

## Subfolders

### `components/`
**Start here when choosing which SLDS component to use.** A single `components-metadata.json` file mapping all 91 SLDS component names to descriptions, semantic synonyms, and available variants. Includes a disambiguation guide for similar components. See its CLAUDE.md for usage.

### `icons/`
Icon name-to-synonyms metadata extracted from `@salesforce-ux/icons`. Five JSON files (utility, standard, action, custom, doctype) mapping each icon name to semantic keyword synonyms. Use this to select the right icon for a given concept. **Prefer utility icons first** — see its CLAUDE.md for selection priority.

### `styles/`
Lightweight styling reference with pointers to online SLDS docs and a summary of the local design-system structure. Covers token hierarchy, naming conventions, and CSS property ordering. Start here when deciding which tokens or classes to use.

### `design-system/`
The SLDS v1 source repo (`@salesforce-ux/design-system`). Contains component blueprints (markup + SCSS), design tokens (color palettes, spacing, typography, sizing, shadows), styling hooks (CSS custom properties), and guidelines. This is the canonical source for how SLDS components are built and styled. Use this for detailed markup examples and accessibility guidance after selecting a component via `components/`.
