# Changelog

## 0.1.6

- Distinguish layout `FILL` sizing from Figma's `fills` paint property.
- Require explicit visual roles for containers and transparent fills, strokes, and effects on structural Auto Layout wrappers.
- Add one-owner surface rules to prevent nested white rectangles and doubled borders inside cards, panels, controls, and alternate backgrounds.
- Audit component sources and every variant, including unused installed, disabled, loading, error, selected, and compact states.
- Reserve `clipsContent` for deliberate viewports, scroll regions, masks, and previews instead of hiding construction defects.
- Add false-positive-aware paint inspection and contrasting-surface screenshot checks to final Figma QA.

## 0.1.5

- Require composition-level Mobbin synthesis instead of reducing research to generic tables, cards, and filters.
- Add a content-morphology workflow and layout-evidence matrix for more varied, task-appropriate first drafts.
- Make navigation, action, object, and status icons plus meaningful grayscale visual anchors mandatory in the first iteration.
- Add revision impact analysis so shared navigation, shell, component, spacing, and typography changes propagate across all affected screens.
- Add minimum, nominal, expanded, and long-content stress tests for buttons, cards, rows, and action groups.
- Explicitly reject fixed-width button clipping, accidental narrow-card wrapping, one-screen-only system fixes, and iconless first drafts.

## 0.1.4

- Add optional Mobbin research routing for substantial flows, unfamiliar product models, and explicit best-practice requests.
- Require focused one-intent searches, visual inspection, multi-product comparison, synthesis instead of copying, and canonical Mobbin links.
- Extend setup diagnostics with separate Mobbin availability while keeping it non-blocking and never silently installed.
- Expand the public README with plugin capabilities, workflow, usage examples, installation, dependencies, and update instructions.
- Rewrite installation as exact, separate Windows and macOS steps, including where terminal commands and in-app skill commands must be entered.

## 0.1.3

- Require fill-remaining state regions so empty, no-results, blocked, and recovery panels center against the real content area.
- Promote repeated app shells, toolbars, tables, rows, dialogs, and state structures to reusable macro-components after three screens.
- Require variants for systematic component families and prevent icon-library duplication by monochrome fill.
- Add false-positive-aware Figma QA for fixed widths, compact text, action gaps, duplicated paths, and repeated primary actions.

## 0.1.2

- Add the explicit `$wireframes-toolkit:setup` dependency audit and installer workflow.
- Install only missing companion skills after one clear confirmation.
- Keep Figma MCP connection status separate from the `figma-use` skill.

## 0.1.1

- Move repository ownership and plugin metadata to `digitalklondike`.
- Update the private marketplace installation URL.

## 0.1.0

- Package the universal `wireframes` skill as a private Codex plugin.
- Declare the Figma MCP tool dependency.
- Add runtime companion-skill preflight and verified install sources.
- Keep `impeccable`, `ui-ux-pro-max`, and `design-system` optional with a built-in fallback.
- Preserve monochrome, Auto Layout, responsive, state, and visual-QA requirements.
