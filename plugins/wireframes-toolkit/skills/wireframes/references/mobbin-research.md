# Mobbin Research

Use Mobbin to observe real product conventions before committing to a substantial UX flow. Do not treat prevalence as proof of quality; synthesize evidence against the current brief, constraints, accessibility needs, and product risks.

## When to research

Use Mobbin when at least one condition applies:

- the user explicitly asks for Mobbin references or best practices;
- the flow is new, unfamiliar, or spans three or more screens;
- the interaction has meaningful sequencing, permissions, recovery, or edge states;
- choosing the wrong pattern would create costly rework.

Skip it for small alignment repairs, obvious component cleanup, or audits that do not require a new interaction model.

## Search method

1. Choose the real target platform: `web` or `ios`.
2. Split the product problem into one-intent queries. Search upload, filtering, bulk actions, permissions, recovery, or another journey separately instead of combining unrelated needs.
3. Use flow search for sequencing and screen search for composition. Run at least one screen-level search for each major screen family whose layout is still undecided. Use section search only for marketing or website sections.
4. Keep result limits small enough to inspect every returned image. Compare at least two relevant products when results allow it.
5. Examine the images and screen order. Compare silhouettes, content mass, density, whitespace, dominant axis, visual anchors, persistent regions, and progressive disclosure—not only the presence of controls. Never describe or adopt a pattern from names, action labels, or metadata alone.
6. Run a second focused query only when the first result set leaves an important state or decision unresolved.
7. Inspect at least three useful screens across at least two products when results allow it. Do not stop after finding one familiar table, dashboard, or card grid.

## Synthesize instead of copying

For each useful pattern, capture:

- the user problem it solves;
- the recurring structure across products;
- the entry point and dominant next action;
- information order and progressive disclosure;
- content morphology and why the composition fits it;
- dominant axis, density, whitespace rhythm, and grouping;
- visual anchors such as icons, previews, thumbnails, diagrams, status marks, or metadata clusters;
- loading, empty, error, permission, destructive, and recovery behavior;
- what to adopt structurally;
- what to reject because it is branded, app-specific, inaccessible, outdated, or inconsistent with the brief.

Use the synthesis to shape the screen inventory, state matrix, and a layout-evidence matrix. For each major screen family, compare two or three viable compositions and select one based on the current actor, content, and decision. Do not copy product names, interface copy, data, visual styling, or a complete competitor layout.

Reject a synthesis that ends only in generic component nouns such as “cards, filters, table.” The result must explain the information shape, reading order, density, progressive disclosure, and visual anchors that should influence the first draft.

Do not force visual variety when jobs are identical, but do not flatten different jobs into the same repeated composition. See [Composition and Revision Protocol](composition-and-revision.md) for the required first-draft gate.

## Reporting and fallback

- When mentioning a Mobbin screen or flow to the user, provide its canonical `mobbin_url` as a Markdown link.
- State clearly when a conclusion is an inference from several references rather than a rule.
- If Mobbin tools are missing or unauthenticated, continue with `ui-ux-pro-max`, the current brief, and the built-in quality standard. Do not block Figma work unless the user explicitly requires Mobbin evidence.
- Do not install or authenticate the Mobbin plugin silently. Explain the missing capability and let the user enable it through Codex Plugins.
