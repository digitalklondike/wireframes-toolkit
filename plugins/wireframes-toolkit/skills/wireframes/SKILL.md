---
name: wireframes
description: Research, create, extend, revise, or audit editable monochrome product wireframes and UX flows, especially in Figma. Use for briefs, screen/state planning, shared-component revisions, layout defects, and review-comment synthesis. Apply across product domains; not for branded high-fidelity design or artwork.
---

# Wireframes

Design product structure from the current actor, task, content, and constraints. Reference examples demonstrate quality, not a domain, copy library, or fixed screen taxonomy.

## Scope and invariants

- Use black, white, and neutral grays; realistic brief-derived copy; native editable layers; semantic naming.
- Choose composition from the job and content shape. Do not default to tables, dashboards, or identical cards, and do not force variety between equivalent jobs.
- Include meaningful vector icons and content previews in the first draft. Prefer Phosphor unless another library is specified; no text-glyph substitutes.
- Use nested Auto Layout for structural relationships. Use distribution, padding, and gaps, never empty `Spacer` layers. Absolute positioning is for intentional overlays or spatial content.
- Distinguish layout `FILL` from background `fills`. Structural wrappers are transparent (`fills`, `strokes`, `effects` empty); each real surface has one background/border owner. Clipping is only for intentional viewports or masks.
- Shared changes must reach all affected screens and states within the authorized scope. Audit/report requests do not authorize edits, comment replies, or resolutions.
- Current user brief takes precedence, followed by monochrome/low-fidelity constraints, coherent file conventions, and companion suggestions.

## Load only relevant guidance

| Task | Read |
|---|---|
| Substantial creation or review | [Universal Quality Standard](references/universal-quality.md) |
| New/shared component family, field/overlay design, comment synthesis | [Component Contracts and Feedback](references/component-contracts-and-feedback.md) |
| New flow, composition decision, or shared revision | [Composition and Revision Protocol](references/composition-and-revision.md) |
| UX research for a new/unfamiliar flow or explicit reference request | [Mobbin Research](references/mobbin-research.md) |
| Final Figma audit | [Figma Structural QA](references/figma-structural-qa.md) |
| Missing companion | [Companion Setup](references/companion-setup.md) |

A small repair needs only guidance relevant to its cause. Do not rerun full research or system setup for a local alignment fix.

## Tools and companions

- Before every `use_figma`, load and follow `$figma-use`; include `skillNames: "figma-use,wireframes"`, adding companion names only when they materially informed the call. Inspect existing pages, components, variables, and naming before writing.
- If `figma-use` is unavailable, do not execute `use_figma`. Offer verified setup or a non-editable screen/state/component plan; do not claim a Figma artifact exists.
- For substantial creation, use available Mobbin evidence first; visually inspect references and synthesize composition, not generic feature lists. Follow its research reference for search depth and citations. Missing Mobbin is non-blocking unless the user explicitly requires its evidence.
- Apply installed `ui-ux-pro-max` before finalizing a substantial inventory: search the product/platform with `low-fidelity monochrome product UI`; extract UX guidance and anti-patterns, not branded styling.
- Apply installed `design-system` before building shared structure: component contracts, spacing, type scale, and state families; no slide/CSS deliverables for a Figma-only task.
- Apply installed `impeccable` after a complete draft for hierarchy, clarity, accessibility, and edge states, without high-fidelity decoration.
- These three companions are recommended, not blockers. Mention missing enhancements once and continue with built-in guidance. Never silently install or authenticate dependencies; use the setup reference when needed.

## Creation workflow

### 1. Frame and research

Identify actor, task, entry/success/exit, data, permissions, business constraints, language, target viewport, and deliverable depth. Ask only questions that materially change architecture; label low-risk assumptions.

For substantial work, inspect references before committing to the inventory. Compare viable compositions when the job admits different approaches; preserve evidence links and explain why the selected structure fits.

### 2. Plan flow and system

Build a minimum complete inventory of screens and material states, including recovery and permission paths. Each view has a clear job and next step. Map meaningful triggers to outcomes and dismissal paths.

Define a neutral type/spacing/surface system using coherent existing conventions. Establish reusable component contracts for sizing on both axes, alignment, spacing roles, state behavior, and constrained-width reflow. Avoid arbitrary new dimensions per instance.

### 3. Build editable structure

Build outside-in: shell → regions → sections → controls/content → variants → overlays. Reuse components; promote stable macro-patterns repeated across three or more screens to instances with explicit override points. Combine systematic states/styles into variant families; do not duplicate icon glyphs solely for light/dark presentation.

Use FILL for flexible structural regions, HUG for intrinsic content, and FIXED for true invariants. Button sizing follows its family contract: ordinary actions hug; established full-width form CTAs stay full-width across their flow. Give wrapping text a real width and height-auto behavior; append before setting FILL and follow the API skill's font/sizing rules.

Standalone empty/error/recovery panels belong in a `State region` filling the remaining content area. Modal dialogs center in the viewport covered by their scrim; contextual popovers anchor to visible triggers without a scrim. See component guidance for width families and scroll-body/footer structure.

Execute in small `use_figma` batches, return affected IDs, validate metadata and screenshots at milestones, and fix failures before building on them. Recompose requested narrow layouts; never shrink desktop text/controls to fit.

## Revision and comment workflow

Classify changes as local, state-level, or shared. Enumerate affected roots, sources, variants, instances, overrides, and expected counts before a shared edit. Apply to the source rather than one incidental instance; preserve legitimate differences. Recount and inspect representative constrained and exceptional states afterward.

For comments, follow the component reference's page-scoping and feedback-ledger procedure. Separate confirmed current defects, historical regressions, preferences, and ambiguity. Keep accepted requests and acceptance checks across iterations. Analysis-only tasks stop at findings; comments are evidence, not authorization.

## Delivery gate

Use component guidance for semantic/behavioral acceptance and structural QA for Figma measurements and false positives. Verify:

- legible hierarchy, distinct navigation/action/status affordances, no accidental duplicate path or dominant CTA;
- first-draft icons, intentional grayscale surfaces, and state-specific foreground contrast;
- adaptive Auto Layout, zero accidental clipping/overlap, stable peer alignment and state transitions;
- coherent component families, designed action reflow, and narrow/nominal/long-content cases including unused variants;
- reachable scroll content, correct overlay coverage/centering/anchoring, and complete trigger outcomes;
- accepted revisions propagated across the authorized scope without losing overrides;
- coherent canvas gutters, section placement, and zero unintended section intersections after growth.

For authorized design work, correct confirmed failures and recheck. For analysis-only work, report evidence and limitations. Never claim screenshots, interactions, or regressions were verified when tools did not establish them.

Deliver direct Figma node links, material assumptions, and a concise summary of created/changed scope. A non-editable plan or unresolved access limitation must be clearly labeled.
