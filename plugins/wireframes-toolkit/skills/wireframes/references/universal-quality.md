# Universal Wireframe Quality Standard

Use this reference to reason about unfamiliar products and screen types without falling back to a fixed template library.

## Contents

- Fidelity and universality
- Structural reasoning
- Information hierarchy
- Content standards
- Auto Layout standards
- Responsive transformations
- States and interactions
- Monochrome visual language
- Pattern primitives
- Failure modes
- Quality rubric

## Fidelity and universality

Aim for structured low-to-mid fidelity:

- neutral enough to invite structural feedback;
- detailed enough to test comprehension, behavior, data shape, and implementation;
- independent of any sample product, industry, brand, or copied interface;
- adaptable to tools, workflows, consumer apps, internal systems, services, and new product categories.

Do not confuse low fidelity with vague output. A good wireframe can contain realistic text, data, validation, permissions, and responsive behavior while remaining visually neutral.

## Structural reasoning

Start from verbs and objects, not screen categories:

- What must the user understand?
- What must the user find, create, compare, change, approve, monitor, or recover?
- What information must persist across steps?
- Which actions are primary, secondary, reversible, destructive, or unavailable?
- What changes when content is absent, delayed, long, invalid, or unauthorized?

Choose a composition that makes those answers obvious. Invent a new composition when common patterns do not fit.

## Information hierarchy

- Give every screen a clear title or orienting context.
- Place the primary task and decision path above supporting information.
- Group information by meaning and cadence, not merely by equal-sized boxes.
- Use proximity, alignment, whitespace, type weight, and grayscale contrast to show relationships.
- Keep actions near the content they affect.
- Use progressive disclosure for secondary detail and advanced controls.
- Avoid equal visual weight across unrelated content.
- Preserve a stable orientation model across a flow.

## Content standards

- Derive copy from the current brief and user vocabulary.
- Prefer specific labels such as `Invite teammate` over generic labels such as `Submit`.
- Use realistic values, counts, dates, statuses, and line lengths when they affect layout.
- Keep copy concise but not cryptic.
- Include helper text only when it prevents error or explains consequence.
- Use placeholders only when the content is genuinely unknown; label the intended content type.
- Never reuse names, organizations, metrics, or prose from unrelated reference files.
- Test at least one long-content or high-density case when the product may encounter it.

## Auto Layout standards

Auto Layout is the default construction method, not an optional cleanup step.

- Build page shells, navigation, content columns, sections, cards, lists, rows, forms, toolbars, tabs, controls, and action groups with Auto Layout.
- Nest containers according to semantic structure rather than placing every child in one large frame.
- Use parent padding and item spacing instead of manual child coordinates.
- Use `FILL` for flexible regions, `HUG` for intrinsic content, and `FIXED` only when the interface requires a stable dimension.
- Give text predictable wrapping behavior and enough width to avoid collapsed text columns.
- Use wrapping rows only when reading order remains clear.
- Keep minimum usable widths in mind before allowing siblings to fill equally.
- Make repeated patterns components when consistency or future editing benefits from reuse.
- Keep icons, badges, and labels inside their control's Auto Layout.
- Keep overlays absolute only relative to a stable Auto Layout container.

Accept absolute positioning for:

- modals, drawers, popovers, tooltips, and floating controls;
- chart marks and spatial visualizations;
- maps, node editors, whiteboards, and other genuinely freeform canvases;
- deliberate decorative or layered elements that affect comprehension.

Do not accept it for ordinary stacks, rows, cards, forms, navigation, or repeated content.

## Responsive transformations

Treat responsiveness as a change in composition and priority.

- Wide navigation may become compact navigation, a drawer, or bottom navigation.
- Multi-column regions may stack, paginate, collapse, or expose a focused detail view.
- Tables may prioritize columns, switch to labeled rows/cards, or use deliberate horizontal scrolling.
- Inline forms may become vertical; paired actions may reorder according to risk and platform conventions.
- Persistent side panels may become drawers or dedicated screens.
- Dense charts may simplify, change aspect ratio, or expose detail on demand.
- Long toolbars may collapse secondary actions into an overflow menu.

Never scale desktop text and controls down to make the same composition fit.

## States and interactions

Include only states that materially affect the flow, but do not omit predictable failure modes.

Consider:

- first use and empty state;
- loading and delayed data;
- partial content;
- inline validation and submission error;
- disabled and unavailable actions;
- success and next step;
- permissions and restricted content;
- destructive confirmation and undo;
- offline or connection loss;
- search with no results;
- overflow, pagination, and large datasets;
- long text, localization, and accessibility scaling.

Show overlays over a dimmed or otherwise contextualized origin screen. Make close, cancel, back, and escape paths clear.

## Monochrome visual language

Use black, white, and neutral grays only.

Recommended roles when the file has no existing system:

- primary ink: near-black;
- secondary ink: medium-dark gray;
- muted ink: medium gray with sufficient contrast;
- canvas: very light gray or white;
- surface: white or a subtly distinct light gray;
- border: light-to-medium gray;
- selected/primary control: near-black fill with white text;
- secondary control: white/light fill with dark border;
- disabled: lighter fill and text plus a clear disabled label or affordance.

Do not rely on hue to communicate status. Combine text, icon, fill value, border, and shape. Keep shadows absent or extremely restrained. Use radii consistently and modestly.

## Pattern primitives

Use these as composable primitives, never as a closed list of allowed screens:

- orientation: title, breadcrumb, progress, selected context;
- navigation: sidebar, tabs, segmented control, stepper, bottom navigation;
- discovery: search, filters, categories, saved views, results;
- input: fields, selection, upload, editor, inline creation;
- comparison: rows, cards, matrix, detail split view;
- monitoring: summary values, trends, alerts, activity;
- decision: review summary, evidence, approval, confirmation;
- communication: thread, timeline, comments, activity history;
- configuration: grouped settings, permissions, preferences;
- feedback: status, validation, empty/loading/error/success;
- contextual action: drawer, dialog, popover, menu, command surface.

Combine, transform, or discard these primitives according to the user's task.

## Failure modes

Reject or correct wireframes that:

- copy the theme or copywriting of unrelated examples;
- use a dashboard merely because the product has data;
- replace content reasoning with uniform cards;
- depend on color to explain state;
- use absolute coordinates for normal layout;
- contain nested groups where editable Auto Layout frames are needed;
- shrink desktop layouts for mobile;
- omit empty, error, or permission states when central to the task;
- use lorem ipsum where real content shape is knowable;
- show isolated modals or drawers without originating context;
- contain clipped text, ambiguous action priority, duplicate components, or generic layer names;
- add polish that makes stakeholders debate branding instead of product structure.

## Quality rubric

Score each dimension from 0 to 2. Fix every zero before delivery.

| Dimension | 0 | 1 | 2 |
|---|---|---|---|
| Task clarity | Primary job is unclear | Job is inferable | Job and next action are immediate |
| Hierarchy | Content has equal/noisy weight | Mostly organized | Meaning and priority are unmistakable |
| Content | Generic or copied | Partly realistic | Brief-derived and layout-realistic |
| Flow | Missing paths or outcomes | Happy path works | Relevant alternate states are covered |
| Auto Layout | Fragile absolute layout | Mixed construction | Structural relationships use nested Auto Layout |
| Reuse | Duplicated repeated elements | Some reuse | Components and instances are intentional |
| Responsiveness | Shrunk or ignored | Partial adaptation | Composition and priority adapt correctly |
| Monochrome | Depends on hue/polish | Mostly grayscale | Grayscale hierarchy works independently |
| Editability | Flattened or poorly named | Editable with cleanup | Native, semantic, maintainable layers |
| Validation | Known visual defects | Basic check only | Metadata and screenshots verified, defects fixed |

A strong result scores at least 17/20 and has no zero in Task clarity, Auto Layout, Editability, or Validation.
