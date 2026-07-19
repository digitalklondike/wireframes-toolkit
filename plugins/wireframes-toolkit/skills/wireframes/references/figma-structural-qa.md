# Figma Structural QA

Use this reference for the final programmatic and visual audit of a substantial Figma wireframe flow. It complements the universal quality standard; it is not a product-specific template.

## Contents

- Audit sequence
- State-region geometry
- Orientation and action duplication
- Reuse and variants
- False-positive controls
- Visual evidence and canvas checks

## Audit sequence

1. Enumerate pages, top-level sections, and screen roots.
2. Capture whole-section screenshots to judge flow organization and paired-screen alignment.
3. Capture representative dense, menu, modal, empty, no-results, error, recovery, and long-content screens at readable resolution.
4. Inspect structure with metadata first; use `use_figma` only for unique programmatic reads and follow `$figma-use`.
5. Run targeted checks, fix real failures, and repeat both the screenshot and structural check.

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

## False-positive controls

Do not report raw detector output without checking meaning.

- A full-width `FIXED` text node or divider can be intentional. Flag copied widths primarily on structural frames, rows, cards, and content columns whose width derives from their Auto Layout parent.
- Short avatar initials, compact chips, file-type labels, and tiny counters are not collapsed text. Treat text as suspicious when meaningful content has an implausibly narrow width, extreme height, clipping, or character-by-character wrapping.
- `itemSpacing = 0` is not proof that actions touch: `SPACE_BETWEEN` can create a large real gap. Measure adjacent child bounds and flag only when their visible gap is below the intended control spacing.
- An icon's internal vector frame may use `layoutMode = NONE`. Audit Auto Layout on semantic containers that position related siblings, not on the internal paths of imported SVG icons.
- A standalone `FIXED` modal width is usually intentional. Audit whether it fits its active viewport and content rather than demanding `FILL`.

## Visual evidence and canvas checks

- Assert zero `Spacer` layers, zero unintended groups, zero clipped visible descendants, and zero top-level section intersections.
- Verify predictable `FILL`, `HUG`, and `FIXED` behavior on the shell, content, split views, tables, cards, action groups, and state regions.
- Verify menus and popovers have a visible trigger, a small positive gap, logical edge alignment, and no scrim; verify dialogs have a full active-state scrim and are centered in the active viewport.
- Inspect whole sections for consistent gutters, section titles, paired-column alignment, and downstream movement after any section grows.
- Inspect individual screens for duplicate paths and actions, button separation, long labels, realistic density, icon visibility, and understandable icon-only controls.

Record confirmed issues by screen and node ID. Keep detector warnings separate from verified defects, and do not hand off a known structural or visual failure.
