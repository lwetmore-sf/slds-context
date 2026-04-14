# slds-context

LLM-oriented reference material for the Salesforce Lightning Design System (SLDS) v1. Provides AI coding assistants with the context they need to correctly apply SLDS styling, select icons, and follow design token conventions when building Lightning Web Components.

## Contents

| Directory | Description |
|-----------|-------------|
| `design-system/` | Full SLDS v1 source (`@salesforce-ux/design-system`) — component blueprints, design tokens, styling hooks, and guidelines |
| `icons/` | Icon name-to-synonyms metadata (utility, standard, action, custom, doctype) extracted from `@salesforce-ux/icons` for semantic icon lookup |
| `styles/` | Lightweight styling reference covering token hierarchy, naming conventions, and CSS property ordering |

## Usage

This repo is designed to be included in an AI assistant's context (e.g., via `CLAUDE.md` references) so it can:

- **Select icons** by matching concepts against icon names and synonym keywords
- **Apply tokens** using the correct hierarchy (component > semantic alias > primitive)
- **Follow conventions** like BEM naming (`slds-block__element_modifier`), property ordering, and utility-class-first styling

See the `CLAUDE.md` files in each subdirectory for detailed guidance.
