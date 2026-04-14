# SLDS Component Selection Metadata

LLM-oriented index mapping UI concepts to the appropriate SLDS base component. Use this to pick the right component for a given job without reading through all 91 blueprint docs.

## File

| File | Purpose | Count |
|------|---------|-------|
| `components-metadata.json` | Component name-to-synonyms-and-variants mapping | 91 components |

## How to Use

To select a component, match the desired UI concept against both component **names**, **descriptions**, and **synonyms**. Each entry has:

- **description** — One sentence explaining what the component is and when to use it
- **synonyms** — Semantic keywords for concept matching (5-15 per component)
- **variants** — Named sub-types/visual variations available for the component

Example entry:

```json
"modals": {
  "description": "Modals display content in a layer above the app for tasks like creating or editing a record.",
  "synonyms": ["modal", "dialog", "popup", "overlay", "lightbox", "dialog-box", "window", "wizard", "confirmation-dialog"],
  "variants": ["base", "taglines", "headless", "footless", "directional", "small", "medium", "large", "full"]
}
```

This means the `modals` blueprint is appropriate when the concept involves dialogs, popups, overlays, wizards, or confirmation flows.

## Component Selection Priority

1. **Match synonyms first** — find components whose synonyms overlap with the UI concept you need
2. **Check variants** — a variant of an existing component is often better than a separate component
3. **Check the blueprint docs** — for detailed markup, states, and accessibility guidance, read `../design-system/ui/components/{name}/docs.mdx`

## Disambiguation: Similar Components

Some components serve overlapping purposes. Use this guide:

| Concept | Use this | Not this |
|---------|----------|----------|
| System-wide banner | `alert` | `toast`, `notifications` |
| Post-action feedback | `toast` | `alert`, `notifications` |
| Stacked reminder list | `notifications` | `toast` |
| Inline section advisory | `scoped-notifications` | `alert` |
| Expand/collapse section | `expandable-section` | `accordion`, `summary-detail` |
| Multiple expand/collapse sections | `accordion` | `expandable-section` |
| Summary always visible + toggle detail | `summary-detail` | `accordion` |
| Default tabs | `tabs` | `scoped-tabs`, `vertical-tabs` |
| Contained/nested tabs | `scoped-tabs` | `tabs` |
| Side tabs | `vertical-tabs` | `tabs` |
| Full record container | `cards` | `tiles` |
| Compact record summary | `tiles` | `cards` |
| Select one from list (native) | `select` | `picklist`, `combobox` |
| Select one with search | `combobox` | `picklist`, `select` |
| Select one (styled dropdown) | `picklist` | `select`, `combobox` |
| Record/entity search | `lookups` / `combobox` | `input` |
| Move items between two lists | `dueling-picklist` | `list-builder` |
| Add items shopping-cart style | `list-builder` | `dueling-picklist` |
| Modal dialog | `modals` | `prompt`, `popovers` |
| System alert requiring acknowledgment | `prompt` | `modals`, `alert` |
| Non-modal contextual info | `popovers` | `modals`, `tooltips` |
| Hover/focus hint text | `tooltips` | `popovers` |
| Flat tabular data | `data-tables` | `tree-grid` |
| Hierarchical tabular data | `tree-grid` | `data-tables`, `trees` |
| Navigation hierarchy | `trees` | `tree-grid` |
| Discrete step progress | `progress-indicator` | `progress-bar`, `path` |
| Continuous progress | `progress-bar` | `progress-indicator` |
| Sales/workflow stages | `path` | `progress-indicator` |

## Source

Generated from the `docs.mdx` files in `../design-system/ui/components/`. If components are added or changed upstream, regenerate this file.
