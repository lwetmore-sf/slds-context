# SLDS Icon Metadata

Icon name-to-synonyms mappings extracted from `@salesforce-ux/icons@10.13.0` (a dependency of the `design-system` repo). Each JSON file maps icon names to a `synonyms` array of semantic keywords that describe the icon's meaning and visual appearance.

## Files

| File | Sprite | Count |
|------|--------|-------|
| `utility-icons-metadata.json` | utility | ~530 |
| `standard-icons-metadata.json` | standard | ~400 |
| `action-icons-metadata.json` | action | ~80 |
| `custom-icons-metadata.json` | custom | ~100 |
| `doctype-icons-metadata.json` | doctype | ~30 |

## Icon Selection Priority

1. **Always prefer `utility` icons first.** They are the most versatile, have the broadest coverage, and are used inline throughout the Salesforce UI.
2. Fall back to `standard` icons for object-specific representations (e.g., Account, Contact, Opportunity).
3. Use `action`, `custom`, or `doctype` only when utility and standard don't have a suitable match.

## Usage

To select an icon, match the desired concept against both icon **names** and **synonyms**. Example entry:

```json
{ "search": { "synonyms": ["magnifyingglass", "look", "find"] } }
```

This means the `utility:search` icon is appropriate when the concept involves searching, finding, or looking up information.

## In LWC / SLDS

Reference icons as `{sprite}:{name}` — e.g., `utility:search`, `standard:account`. The SVG sprites live in `@salesforce-ux/icons` at `dist/salesforce-lightning-design-system-icons/{sprite}-sprite/svg/symbols.svg`.
