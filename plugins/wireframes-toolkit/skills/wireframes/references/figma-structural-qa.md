# Figma Structural QA

Use this reference for the final programmatic and visual audit of a substantial Figma wireframe flow. It complements the universal quality standard; it is not a product-specific template.

## Contents

- Audit sequence
- Surface ownership and default paint
- State-region geometry
- Orientation and action duplication
- Reuse and variants
- Revision propagation
- Adaptive component geometry
- False-positive controls
- Visual evidence and canvas checks

## Audit sequence

1. Enumerate pages, top-level sections, and screen roots.
2. Capture whole-section screenshots to judge flow organization and paired-screen alignment.
3. Capture representative dense, menu, modal, empty, no-results, error, recovery, and long-content screens at readable resolution.
4. Inspect structure with metadata first; use `use_figma` only for unique programmatic reads and follow `$figma-use`.
5. Run targeted checks, fix real failures, and repeat both the screenshot and structural check.

## Surface ownership and default paint

Figma Auto Layout frames may retain a default white fill even when they exist only to arrange children. These fills can remain invisible on a white canvas and appear later as rectangular seams inside gray cards, selected states, dialogs, or alternate variants.

For frames, components, component variants, and instances:

- distinguish layout `FILL` sizing from the `fills` paint property;
- inventory visible white and near-white fills, strokes, and effects on semantic structural names such as `Content`, `Copy`, `Heading`, `Metadata`, `Rating`, `Actions`, `Row`, `Rail`, `Grid`, and `Section`;
- verify that canvas, card, panel, field, button, menu, dialog, drawer, tile, media, icon well, selection, and scrim layers own paint intentionally;
- require ordinary structural wrappers to use empty fills, strokes, and effects unless they are independently bounded or interactive;
- require one semantic owner for each background and border, rather than repeating the same paint on nested descendants;
- inspect the component source and every variant, including unused installed, disabled, loading, error, compact, or selected variants;
- after a source fix, recount instances and confirm that all affected screens update without losing legitimate overrides.

Do not rely on a white-canvas screenshot alone. Use programmatic paint inspection, then capture a representative screen where the component sits on a contrasting neutral surface. A hidden default fill is a structural defect even when the current background masks it.

## State-region geometry

For every standalone empty, no-results, blocked, error, permission, unavailable, or recovery panel:

- require a semantic `State region` between the state panel and the ordinary page stack;
- make the region `FILL` horizontally and fill the remaining vertical area when its parent provides bounded height;
- place title rows, breadcrumbs, search, filters, and other persistent context before the region in normal flow;
- center the state panel against the region's bounds, not the screen canvas and not a guessed fixed-height box;
- allow non-centered placement only when nearby content is part of the same decision and document the reason in the audit.

Programmatically compare the panel and region centers with a small tolerance such as 8 px. Also verify that the region occupies the remaining parent height after padding, gaps, and preceding siblings. A perfectly centered panel inside a short fixed region is still a failure if large unused space remains below the region.

## Orientation and action duplication

- Normalize path text before comparison by ignoring separators, whitespace, and case. Flag a subtitle path that repeats the same hierarchy already expressed by a breadcrumb.
- Extract dominant action labels from the title row, persistent toolbar, and state panel. Flag an equivalent primary action repeated in the same viewport unless one occurrence is deliberately secondary or has a distinct contextual scope.
- Treat a repeated action as an information-hierarchy issue, not merely a copy issue: the user should not have to choose between two visually equal entrances to the same operation.

## Reuse and variants

- Count coherent frame names and structures across screen roots. A macro-pattern present on three or more screens is a component candidate; shared shells and navigation are components even before that threshold when multiple states are planned.
- Audit app shells, headers, sidebars, toolbars, search controls, tables, rows, cards, dialog shells, upload managers, and state panels before auditing small atoms. Repeating the large structure creates more maintenance risk than repeating a divider.
- Require instances for stable repeated structures and expose only the text, icons, visibility, state, and content slots that legitimately vary.
- Combine a semantic family into a component set with variant axes such as `state`, `style`, `size`, and `selection`. Flag sibling standalone definitions such as `Button/Primary`, `Button/Secondary`, and `Button/Disabled` when they describe one control family.
- Keep one component per icon glyph. Use supported fill overrides, variables, or component properties for neutral light/dark presentation; flag duplicate icon libraries whose only difference is fill color.

## Revision propagation

For every change to navigation, shell, header, sidebar, toolbar, card, button, spacing, typography, or another repeated pattern:

- enumerate the source component, variant set, and all affected instances before editing;
- treat the change as global unless the user explicitly scopes a local exception;
- verify that every affected screen points to the intended source or variant after editing;
- flag any copied frame that remains after the pattern has been promoted to a component;
- compare expected and actual affected counts;
- inspect at least one wide, one narrow, and one exceptional-state screen;
- confirm that unrelated instance overrides survived the source edit.

Do not accept a screenshot-only local patch as evidence of a complete system revision.

## Adaptive component geometry

Stress-test reusable buttons, cards, rows, navigation items, and action groups at minimum, nominal, and expanded widths, plus realistic text expansion.

- Prefer horizontal-HUG buttons with fixed accessible height and padding. Flag fixed button widths that are not true invariants.
- Compare the bounds of icon and label descendants against every button variant. Any visible descendant outside the control is a failure even when the parent clips it.
- Require disabled, loading, installed, and destructive variants to preserve compatible geometry.
- Make card content columns fill while icon slots and actions hug or remain intentionally fixed.
- Require an explicit compact variant or designed stacked footer when a narrow card changes topology; flag accidental wrapping.
- Inspect component sources as well as instances. A wide instance can hide a broken source, and a correct source can still have an invalid width override.
- Inspect unused variants as well as placed instances. A family is not complete while an unplaced variant still contains accidental paint, clipping, or incompatible geometry.

## False-positive controls

Do not report raw detector output without checking meaning.

- A full-width `FIXED` text node or divider can be intentional. Flag copied widths primarily on structural frames, rows, cards, and content columns whose width derives from their Auto Layout parent.
- Short avatar initials, compact chips, file-type labels, and tiny counters are not collapsed text. Treat text as suspicious when meaningful content has an implausibly narrow width, extreme height, clipping, or character-by-character wrapping.
- `itemSpacing = 0` is not proof that actions touch: `SPACE_BETWEEN` can create a large real gap. Measure adjacent child bounds and flag only when their visible gap is below the intended control spacing.
- An icon's internal vector frame may use `layoutMode = NONE`. Audit Auto Layout on semantic containers that position related siblings, not on the internal paths of imported SVG icons.
- A standalone `FIXED` modal width is usually intentional. Audit whether it fits its active viewport and content rather than demanding `FILL`.
- A fixed button width can be intentional for icon-only controls, keypads, or equal-choice layouts. Require evidence from the interaction model; ordinary labeled action buttons should normally hug.
- A white or near-white fill is not automatically wrong. Screen roots, cards, panels, headers, fields, menus, dialogs, buttons, tiles, icon wells, and media previews may be legitimate surfaces. Confirm the semantic role and parent-child contrast before clearing paint; never mutate solely from a name heuristic.

## Visual evidence and canvas checks

- Assert zero `Spacer` layers, zero unintended groups, zero accidentally painted structural wrappers, zero clipped visible descendants, and zero top-level section intersections.
- Verify predictable `FILL`, `HUG`, and `FIXED` behavior on the shell, content, split views, tables, cards, action groups, and state regions.
- Verify menus and popovers have a visible trigger, a small positive gap, logical edge alignment, and no scrim; verify dialogs have a full active-state scrim and are centered in the active viewport.
- Inspect whole sections for consistent gutters, section titles, paired-column alignment, and downstream movement after any section grows.
- Inspect individual screens for duplicate paths and actions, button separation, long labels, realistic density, first-draft icon visibility, and understandable icon-only controls.
- Inspect whole-flow composition for unjustified repetition. Flag different screen jobs that have been reduced to the same table, dashboard, or uniform card template without content-based reasoning.

Record confirmed issues by screen and node ID. Keep detector warnings separate from verified defects, and do not hand off a known structural or visual failure.
