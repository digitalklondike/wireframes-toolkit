---
name: wireframes
description: Research, create, extend, revise, or audit universal black-and-white product wireframes and UX flows, especially in Figma. Use when Codex must turn briefs, requirements, journeys, rough ideas, or comparable-product evidence into structurally sound low- or mid-fidelity screens; plan screen inventories and states; create desktop, mobile, or responsive variants; propagate shared changes across an existing flow; or improve generic, iconless, clipped, or overly table-driven wireframes. Prioritize composition-level Mobbin evidence, first-draft iconography, Auto Layout, adaptive reusable components, realistic content, clear hierarchy, responsive reflow, cross-screen consistency, and visual validation. Apply to any product domain or screen type. Do not use for branded high-fidelity visual design, illustration, or marketing artwork.
---

# Wireframes

Create useful product structure, not decorative mockups. Treat any supplied examples as evidence of quality and construction only. Never copy their domain, information architecture, labels, people, numbers, or screen taxonomy unless the current brief independently requires them.

For substantial creation or review, read [Universal Quality Standard](references/universal-quality.md) before designing.

## Operating principles

- Derive every screen from the current user's goal, actor, content, actions, and constraints.
- Keep the result universal and monochrome: black, white, and neutral grays only.
- Prefer realistic, concise product content over lorem ipsum or arbitrary placeholders.
- Make behavior, hierarchy, states, and flow legible before adding detail.
- Select composition from the content shape and user decision. Do not default to a table, dashboard, or uniform card grid merely because it is familiar or already available.
- Include the planned icons and meaningful grayscale visual anchors in the first draft. Treat them as navigation and comprehension structure, not later polish.
- Use Auto Layout for every structural relationship. Treat absolute positioning as an exception that needs a clear reason.
- Create native, editable Figma structure. Do not flatten finished wireframes into images.
- Match the user's language for interface copy unless the brief specifies another language.

## Choose the output mode

### Write or modify Figma

1. Load and follow `$figma-use` before every `use_figma` call.
2. Pass at least `skillNames: "figma-use,wireframes"` to every `use_figma` call. Append any companion skill names that materially informed the operation.
3. Inspect the target file, page, components, variables, and naming before writing.
4. Reuse an existing neutral wireframe system when it fits. Do not inherit branded styling unless requested.
5. If no target file exists, create or request an editable Figma Design file using the supported Figma workflow.

### Review existing wireframes

Use screenshots and metadata first. Inspect with `use_figma` only when a unique programmatic read is necessary; load `$figma-use` before doing so. Report both UX issues and construction issues such as missing Auto Layout, duplicated components, ambiguous sizing, clipping, or fragile absolute coordinates.

### Work without an editable Figma file

Produce a screen inventory, flow, content hierarchy, state matrix, responsive behavior, and component plan. Clearly label assumptions. Do not pretend a Figma artifact was created.

## Companion skill routing

Before a substantial task, compare the current available-skills catalog with the companion list below. If any companion is missing, read [Companion Setup](references/companion-setup.md).

- Treat `figma-use` as required only for Figma operations that call `use_figma`. If it is missing, explain that editable Figma execution cannot start, show its verified installation source, and wait for installation or choose the non-editable output mode. Never call `use_figma` without it.
- Treat `ui-ux-pro-max`, `design-system`, and `impeccable` as recommended enhancements. Mention missing enhancements once per thread with one concise setup note, then continue with the built-in workflow and quality standard unless the user asks to install them.
- Never execute a companion installation command without explicit user consent. Do not repeatedly interrupt a wireframing task after the user declines or chooses fallback mode.

For substantial creation or revision, load and apply the following installed companion skills in addition to `wireframes`. Treat a new flow, three or more screens, an unfamiliar product model, or a system-level component change as substantial.

1. Use `$ui-ux-pro-max` before finalizing the screen inventory. Follow its required design-system search with the product type, platform, and `low-fidelity monochrome product UI` in the query. Extract product patterns, UX guidance, accessibility risks, and anti-patterns. Discard palette, font-pairing, effects, and branded-style recommendations unless the user explicitly asks to leave low fidelity.
2. Use `$design-system` before building reusable structures when the flow has a shared shell, repeated controls, variants, or three or more screens. Apply its component specification, state matrix, spacing, and typography-scale guidance to Figma components and variants. Do not run its slide workflow or generate CSS tokens for a Figma-only wireframe task unless explicitly requested.
3. Use `$impeccable` after the first structurally complete draft and before final Figma QA. Apply the product register and the relevant critique, layout, clarify, or harden lens to information architecture, hierarchy, cognitive load, copy, accessibility, and edge states. Do not let it convert the artifact into high fidelity or add decorative color, typography, or motion.

For a small scoped repair, skip the full companion sequence and load only the companion whose lens directly helps. If a companion skill is unavailable, continue with `wireframes`, state the fallback briefly, and do not block the task.

Resolve conflicts in this order: the current user brief, this skill's low-fidelity and monochrome constraints, the existing file's coherent conventions, then companion recommendations. Translate companion output into native editable Figma structure rather than code-only deliverables.

## UX reference research

For a substantial new flow, an unfamiliar product model, a complex interaction, or an explicit request for references or best practices, use Mobbin when its app tools are available. Read [Mobbin Research](references/mobbin-research.md) and [Composition and Revision Protocol](references/composition-and-revision.md) before searching, and complete the focused research before finalizing the screen inventory.

For substantial creation, use this order: Mobbin for real-product evidence, `ui-ux-pro-max` for guidance and anti-patterns, `design-system` for reusable structure, then `impeccable` for critique after the first complete draft.

- Treat Mobbin as evidence of real product conventions, not as an authority or a source to copy.
- Compare multiple relevant products and extract flow structure, information order, state coverage, action placement, recovery paths, and progressive disclosure.
- Extract composition as well as feature presence: content morphology, dominant axis, density, whitespace rhythm, visual anchors, persistent regions, and progressive disclosure. Produce a brief layout-evidence matrix before drawing.
- Use screen search to study layout and flow search to study sequence. Inspect at least three useful screens across at least two products when results allow it.
- Generate two or three viable composition candidates for materially different screen jobs, then choose deliberately. Do not translate every reference into the same table, card grid, or dashboard.
- Keep each search focused on one journey, screen, or section and use the requested platform.
- Inspect returned images; never infer a pattern from metadata alone.
- Cite the Mobbin links for references mentioned to the user.
- Skip Mobbin for small layout repairs, component-only cleanup, or a structural audit whose scope will not change.
- Keep Mobbin optional. If its tools are unavailable, continue with `ui-ux-pro-max` and the built-in quality standard. Mention the fallback only when the user explicitly requested Mobbin or when missing evidence materially limits the result.

## Workflow

### 1. Frame the product problem

Extract or infer:

- primary actor and job to be done;
- entry point, success outcome, and exit paths;
- required information and decisions;
- target platforms and viewport constraints;
- source data, permissions, risks, and business rules;
- required fidelity, flow depth, and deliverable scope.

Ask only questions whose answers would materially change the architecture. Continue with explicit assumptions when risk is low.

### 2. Design the flow before the screens

- Create the minimum complete screen/state inventory for the task.
- Give each screen one clear primary job and one dominant next action.
- Include alternate paths only when they affect comprehension or implementation.
- Select and combine interaction patterns from the content and behavior; never limit the solution to pattern names seen in examples.
- Map each major screen job to an appropriate content morphology such as table, list, browse-detail, timeline, staged flow, grouped form, canvas, or mixed composition. Use tables only for genuine repeated-field comparison.
- For substantial flows, write a concise composition brief from inspected references before committing to the first screen.
- Identify reusable regions and components before drawing.

### 3. Establish a neutral wireframe system

Use existing file conventions when they are coherent. Otherwise establish:

- grayscale surfaces, text, borders, controls, and disabled states;
- a compact neutral sans-serif type hierarchy;
- a consistent 4-point spacing family such as 4, 8, 12, 16, 24, 32, and 48;
- restrained corner radii and no ornamental shadows;
- clear interaction priority through size, weight, placement, and contrast rather than color;
- platform-appropriate frame widths derived from the brief, using common defaults only when unspecified.

Represent status without semantic color. Use labels, icons, shape, fill value, borders, and text.

### 4. Build Auto Layout first

Construct from the outside in:

1. page shell;
2. navigation and main content regions;
3. sections and responsive rows/columns;
4. cards, lists, forms, toolbars, and controls;
5. repeated components and their states;
6. overlays and intentional layered content.

Apply these rules:

- Use nested Auto Layout frames for stacks, rows, alignment, padding, gaps, wrapping, and responsive composition.
- Separate layout sizing from visual paint. `layoutSizingHorizontal = "FILL"` controls geometry; `fills` controls background paint. A structural container can and often should fill its parent while remaining visually transparent.
- Assign every container an explicit visual role before styling it: canvas, surface, structural wrapper, control, media/preview, or overlay. After creating an Auto Layout frame, set its appearance deliberately instead of accepting Figma defaults. Use `fills = []`, `strokes = []`, and `effects = []` for structural wrappers; give a deliberate fill or border only to a real surface.
- Keep one owner for each background and border. Do not repeat a card or panel fill on nested `Content`, `Copy`, `Heading`, `Metadata`, `Rating`, `Actions`, `Row`, or `Rail` frames unless that child is independently interactive or visually bounded.
- Never create empty `Spacer` layers or frames to push content apart. Use Auto Layout distribution such as `SPACE_BETWEEN`; when either side contains multiple children, wrap them in semantic groups such as `Leading content` and `Trailing actions` or `Primary navigation` and `Utility navigation`.
- Use `FILL`, `HUG`, and `FIXED` deliberately; append children before applying `FILL` as required by `$figma-use`.
- Reserve `FIXED` for true invariants such as icon slots, compact controls, stable sidebars, intentional modal widths, and bounded preview panes. Prefer `FILL` when a structural row, section, card, or content column derives its available width from its parent. A full-width child whose width merely repeats the parent's inner width should normally be `FILL`, not a copied pixel value.
- In repeated horizontal rows, let peer cards fill the row when they should share available space. Inside each card or list row, make the semantic content column fill while icons and trailing actions hug or stay fixed. Add minimum widths only when the content model requires them.
- Give wrapping text a real width and height-auto behavior. Test long labels and realistic content.
- Size every container to its tallest child. Use a consistent control height appropriate to the platform, commonly 44 px on desktop wireframes, and never hide a sizing defect with clipping.
- Turn repeated or stateful structures into components and instances. Create variants when differences are systematic.
- Audit the component source and every variant, including variants not currently placed on a screen. A correct visible instance does not prove that installed, disabled, loading, error, or compact variants are free of default fills, clipping, or fixed-width defects.
- Before distributing a reusable component, stress-test its source at minimum, nominal, and expanded widths and with 130–150% text expansion. Design a compact variant or explicit reflow when the narrow state changes topology.
- Treat reuse as a construction requirement, not optional cleanup. Any coherent macro-pattern used on three or more screens—such as an app shell, navigation, toolbar, table header or row, card, dialog shell, upload manager, or state panel—should normally be a component or instance with explicit override points.
- Model one semantic component family as a component set with variant properties such as `state`, `style`, `size`, or `selection`. Do not leave `Button/Primary`, `Button/Secondary`, and similar siblings as unrelated standalone components when they are variants of the same control.
- Keep one component per icon glyph and change presentation through supported instance overrides, variables, or component properties. Do not duplicate an icon library merely to create light and dark versions.
- Name layers by role: `Page shell`, `Primary navigation`, `Content`, `Section`, `Field`, `Actions`, `Modal`, and similar semantic names.
- Avoid generic names such as `Frame 123`, `Group`, or `Rectangle` in finished work.
- Use absolute positioning only for overlays, floating controls, chart marks, freeform canvases, or intentionally layered elements. Keep their containing structure in Auto Layout.
- Keep `clipsContent` off for ordinary structural containers. Enable it only for a deliberate viewport, scroll region, media mask, or bounded preview; never use clipping to conceal overflow, background seams, or undersized components.

### 5. Add content and behavior

- Use brief-derived labels, values, helper text, and actions.
- Show the shape and density of real data without polishing it into high fidelity.
- Preserve sufficient detail to test hierarchy and decisions; remove decorative detail that does not affect behavior.
- Add only relevant states: default, hover/focus when needed, empty, loading, error, validation, disabled, success, permissions, destructive confirmation, overflow, and long-content cases.
- Show drawers, dialogs, menus, and popovers in context over the originating screen.
- Anchor every open menu, dropdown, or popover to a visible trigger. Place it below or beside the trigger with a deliberate 4–8 px gap and align a logical edge; never overlap the trigger or leave the layer floating ambiguously. Show an active/open trigger state when the relationship would otherwise be unclear.
- Treat filters and selects as stateful controls, not decorative chips. Give the trigger a real caret icon, show an anchored open state with a visible current selection, and add an applied state whose label, count, and resulting content agree with the chosen value.
- Put the clear affordance for a populated search field inside the field at the trailing edge. Do not add a separate `Clear search` button unless clearing is a destructive or unusually consequential operation.
- Use one orientation path per view. When a breadcrumb is present, do not repeat the same path as subtitle copy above it.
- Avoid duplicate primary actions within one viewport. If a title row or persistent toolbar already exposes the empty-state action, either remove it from the state panel, demote one occurrence, or make the contextual difference explicit.
- Create an icon map before the first build milestone. Use one coherent icon library and real vector icons instead of text glyphs. If the brief does not specify a library, prefer Phosphor icons for neutral product wireframes. Cover navigation, actions, object types, and status/feedback states in the first draft; do not postpone them to polish. Give every icon-only action an unambiguous accessible name or tooltip.
- Use distinct semantic icons or grayscale content previews to differentiate repeated entities. Do not reuse one generic icon across unrelated objects merely because it is convenient.
- When space is constrained, preserve the recognizable icon and convert a secondary action to icon-only before allowing its label or control to clip. Keep primary or ambiguous actions labeled.
- Center dialogs within the active content viewport, excluding persistent navigation and headers. Put every standalone empty, no-results, error, blocked, and recovery panel inside a named `State region` that fills the remaining content area on both axes, then center the panel within that region unless the surrounding information architecture requires another alignment. Do not simulate centering with a fixed-height region that leaves unused space below it, and do not place a standalone state panel directly in a left-aligned content stack.
- Give dialogs a scrim that covers the entire active screen state and place the centered dialog above it. Contextual menus, dropdowns, and popovers should not dim the screen; their trigger, edge alignment, and small gap must communicate origin.
- Keep adjacent actions visually distinct. Use an explicit Auto Layout gap, normally 8–12 px on desktop, and audit nested trailing-action groups as well as the outer action row so button strokes never visually merge.
- Keep ordinary labeled buttons horizontal-HUG with a stable accessible height and padding. Do not assign a fixed width just to make siblings match. Verify that icon and label bounds remain inside every button variant, including disabled, loading, and installed states.
- Annotate assumptions or non-obvious behavior outside the product UI, not as fake interface copy.

### 6. Adapt; do not shrink

- Recompose layouts for each requested viewport.
- Convert grids to stacks, side regions to drawers or bottom navigation, dense tables to prioritized rows/cards or controlled horizontal overflow, and side-by-side actions to an appropriate mobile order.
- Preserve task priority, readable content, and usable control sizes.
- Do not force a desktop composition into a narrow frame by scaling it down.

### 7. Revise with impact analysis

Read [Composition and Revision Protocol](references/composition-and-revision.md) before any revision that touches navigation, shell, header, sidebar, toolbar, cards, buttons, spacing, typography, or another repeated pattern.

- Classify the request as local, state-level, or system-level before editing.
- Treat shared navigation and component changes as global by default unless the user explicitly scopes one screen.
- Enumerate affected screen roots, source components, instances, variants, and expected counts.
- Edit the component source, component set, variable, or shared shell. Never patch one instance when the change is semantic to the system.
- Promote stable copied patterns used three or more times to components before modifying them.
- After editing, recount instances and copied remnants, verify variant preservation, and inspect representative wide, narrow, and exceptional-state screenshots.
- Report the changed source component and the number of affected screens.

### 8. Execute incrementally in Figma

Follow `$figma-use` strictly:

1. inspect;
2. build the top-level skeleton with placeholders;
3. create or reuse repeated components;
4. populate one logical section at a time;
5. return all created and mutated node IDs;
6. validate structure and screenshot each milestone;
7. fix defects before continuing.

Keep each `use_figma` call small. Do not attempt an entire complex flow in one script.

### 9. Validate before delivery

Check all of the following:

- every structurally related group uses Auto Layout;
- the root frame and major regions resize predictably;
- no text, controls, or content are clipped, overlapped, or collapsed;
- no visible descendant extends outside its screen or intended clipping container;
- no structural wrapper carries an accidental white or near-white fill, stroke, or effect; each visible surface has one intentional owner;
- no empty `Spacer` layer exists; all separation comes from Auto Layout alignment, distribution, gaps, or padding;
- every interactive control that relies on an icon contains a visible icon, and constrained icon-only controls remain understandable;
- repeated structures are instances where reuse is valuable;
- macro-patterns repeated across three or more screens are instances rather than copied frames;
- systematic control families use variants, and icon glyphs are not duplicated by presentation color;
- hierarchy and primary actions remain obvious in grayscale;
- the first draft already includes the planned navigation, action, object, and status icons;
- different screen jobs use evidence-backed compositions rather than one repeated table/card template;
- buttons and reusable content components pass minimum, nominal, expanded, and long-content stress cases;
- system-level revisions resolve consistently across every affected instance and screen;
- each view has one canonical orientation path and no unexplained duplicate primary CTA;
- content is realistic and belongs to the current brief;
- relevant edge states and responsive transformations are present;
- overlays retain context and clear dismissal paths;
- layers and frames are semantically named;
- screenshots match metadata and intended structure.

For Figma flows, read [Figma Structural QA](references/figma-structural-qa.md) before the final audit. Count screen roots; assert zero `Spacer` layers; inventory fills, strokes, and effects on semantic structural wrappers; detect descendants outside screen bounds and children larger than clipping parents; verify flexible structural regions use `FILL`; verify standalone states have a fill-remaining `State region`; detect copied macro-patterns and split component families; compare repeated orientation paths and primary actions; and verify open menus have a small positive gap and aligned edge relative to their triggers. Check component sources and every variant, not only visible instances. Apply the reference's false-positive rules before reporting defects. Then visually inspect representative dense, modal, state, menu, long-content, and whole-section screenshots.

When a section or canvas group grows, recompute the positions of every downstream section row. Preserve the established horizontal and vertical gutters, move paired columns together, and assert zero pairwise intersections between top-level sections before handoff.

Run a targeted correction pass for any failure. Do not hand off known defects.

## Definition of done

Deliver native editable layers, structurally complete flows, intentional Auto Layout, reusable patterns, monochrome visual language, realistic content, relevant states, responsive behavior when requested, clean naming, and screenshot-verified output. Summarize assumptions and provide direct links to the created or modified Figma nodes.
