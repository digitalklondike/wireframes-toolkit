# Composition and Revision Protocol

Use this reference for substantial new flows, first-draft quality problems, system-level revisions, or any component that must survive more than one width. It prevents generic table/card output, iconless first drafts, one-screen-only fixes, and accidental clipping.

## Contents

- Reference-backed composition
- Content morphology
- First-draft visual anchors
- Revision impact analysis
- Adaptive component stress testing
- Completion gates

## Reference-backed composition

Do not finish Mobbin research with a list of generic patterns such as “use cards” or “add filters.” Translate the evidence into a composition brief before drawing.

For each major screen family, record:

- screen job and dominant user decision;
- primary content form;
- dominant axis and reading order;
- density and whitespace rhythm;
- persistent versus progressively disclosed information;
- visual anchors such as icons, previews, thumbnails, diagrams, status marks, or grouped metadata;
- the reference structure worth adopting;
- the branded, decorative, or product-specific aspects to reject.

Inspect at least three useful screens across at least two products when results allow it. Use flow search for sequence and screen search for composition. Compare screenshots by silhouette as well as feature presence: identify where mass, whitespace, controls, content previews, and detail live.

Create two or three viable composition candidates when the screen job permits materially different structures. Choose one because it fits the actor, content, and decision—not because it is the most common result. Keep evidence links in working notes and cite any reference mentioned to the user.

Do not force variety for its own sake. Repeated jobs should remain consistent. Different jobs should not be flattened into the same table, uniform card grid, or dashboard shell merely because those components already exist.

## Content morphology

Select structure from the shape of the content:

- Use a table when users compare repeated fields across many homogeneous items.
- Use cards when items have heterogeneous summaries, visual identity, or independent actions.
- Use a list when scanning order matters more than comparison across columns.
- Use browse-detail or split view when users need context while inspecting one item.
- Use a timeline or activity stream when sequence and causality are primary.
- Use a stepper or staged flow when later decisions depend on earlier input.
- Use grouped forms when the main job is entering or configuring information.
- Use a canvas, map, diagram, or node view only when spatial relationships are meaningful.
- Use summary modules only for decisions that genuinely benefit from monitoring.

Mix structures when the product job changes across the screen. A page can combine a compact summary, a preview, a ranked list, and progressive detail without becoming high fidelity.

## First-draft visual anchors

Treat iconography and content previews as structural information in the first iteration, not polish for a later pass.

Before building, create a short icon map for:

- global navigation;
- primary and secondary actions;
- object or content types;
- status, warning, success, permission, and empty states;
- repeated entities that need quick differentiation.

Use one coherent vector library. Prefer Phosphor when the brief does not specify another system. Never substitute Unicode glyphs, hand-built line icons, or the same generic icon for semantically different entities.

Add a meaningful low-fidelity visual anchor wherever it improves scanning or comprehension: a grayscale thumbnail, document preview, mini-chart shape, process diagram, avatar placeholder, object icon, or status mark. Do not add decoration without an information role.

The first screenshot milestone must already contain the planned icons and anchors. Reject an iconless first draft unless the interface is genuinely text-only.

## Revision impact analysis

Classify every requested change before editing:

- **Local:** unique content or behavior on one screen.
- **State-level:** one variant of a reusable control or flow state.
- **System-level:** navigation, app shell, header, sidebar, toolbar, card, button, typography, spacing, icon mapping, or any pattern repeated across screens.

Treat system-level changes as global by default unless the user explicitly scopes an exception.

Before editing:

1. Enumerate affected screen roots.
2. Find the source component and every relevant instance.
3. Identify overrides and variants that must remain distinct.
4. If a stable pattern appears three or more times as copied frames, promote it to a component before changing it.
5. Record expected affected counts and representative screen IDs.

Apply the change to the source component, component set, variable, or shared shell. Do not patch one instance and leave siblings inconsistent. Model legitimate differences through variants or explicit properties.

After editing:

1. Recount affected instances and copied remnants.
2. Verify every relevant screen resolves to the intended source component or variant.
3. Capture at least one wide, one narrow, and one exceptional-state screenshot.
4. Check that unrelated overrides were preserved.
5. Report the component source and affected screen count.

## Adaptive component stress testing

Test reusable controls and content components at minimum, nominal, and expanded widths before using them throughout a flow. Also test realistic long text at approximately 130–150% of the default copy length.

### Buttons

- Use horizontal HUG sizing for ordinary labeled buttons.
- Keep a fixed, accessible control height and horizontal padding; do not use a fixed width merely to match siblings.
- Keep icon, label, and optional caret in one Auto Layout row with a deliberate gap.
- Make the disabled, loading, installed, and destructive variants preserve compatible geometry.
- Never hide a sizing defect with clipsContent.
- Verify the label and icon bounds remain inside the button at every tested width.
- If the parent becomes constrained, shorten a secondary label or use a recognizable icon-only variant before clipping the primary action.

### Cards and rows

- Make the outer component fill the available row when the layout expects shared width.
- Make the semantic content column fill; keep icon slots and trailing actions hug or fixed.
- Keep metadata and actions in explicit leading/trailing groups.
- At narrow widths, use a designed compact variant or stack the footer; do not rely on accidental wrapping.
- Keep CTA placement stable and visually attached to the item it affects.
- Test long names, descriptions, dates, counts, and creator labels.

### Containers

- Give flexible siblings real minimum widths or explicit reflow rules.
- Use FILL for widths derived from the parent and HUG for intrinsic content.
- Detect visible descendants outside the component and children larger than clipping parents.
- Screenshot both the component source and representative instances after a source edit.

## Completion gates

Do not accept the first draft until:

- the selected composition is traceable to content needs and, when available, inspected Mobbin evidence;
- different screen jobs are not flattened into one repeated table/card template;
- required icons and visual anchors are already present;
- repeated system regions are components or instances;
- a change-impact map exists for any revision touching shared UI;
- buttons and cards pass minimum, nominal, expanded, and long-content tests;
- zero visible content is clipped or hidden by a fixed-width control.
