# Wireframes Toolkit

Wireframes Toolkit is a public Codex plugin for researching, creating, extending, and auditing editable black-and-white product wireframes, especially in Figma.

It turns product briefs, requirements, journeys, and rough ideas into complete low- or mid-fidelity flows with intentional Auto Layout, reusable components, realistic states, responsive behavior, and screenshot-verified structural QA. The workflow is universal: supplied examples inform quality and construction, never the product domain or interface copy.

## What the plugin does

- Frames the actor, job to be done, entry point, success outcome, constraints, and business rules.
- Builds a minimum complete screen and state inventory before drawing.
- Optionally researches comparable real-product flows in Mobbin and synthesizes patterns instead of copying a competitor.
- Creates native editable Figma layers rather than flattened images.
- Uses nested Auto Layout and deliberate `FILL`, `HUG`, and `FIXED` sizing without empty Spacer layers.
- Promotes repeated shells, navigation, toolbars, tables, dialogs, and state panels into reusable components.
- Uses component variants for systematic states such as button appearance, active navigation, selection, loading, or disabled behavior.
- Covers relevant empty, loading, error, permission, success, destructive, quota, overflow, and recovery states.
- Keeps menus anchored to triggers, dialogs centered over full-screen scrims, search clearing inside the field, and standalone states centered in fill-remaining regions.
- Audits clipping, overflow, section collisions, duplicated actions, broken instances, fragile fixed widths, missing Auto Layout, and component duplication.
- Adapts layouts by recomposing for desktop, mobile, or responsive views instead of shrinking a desktop canvas.

The output stays monochrome and product-focused. This plugin is not intended for branded high-fidelity visual design, illustration, or marketing artwork.

## Research workflow

For substantial or unfamiliar flows, Wireframes can use the optional Mobbin app to inspect real screens and multi-step journeys before finalizing the screen inventory.

The skill searches one interaction at a time, uses the correct platform, inspects the returned images, compares multiple relevant products, and extracts sequencing, information hierarchy, action placement, progressive disclosure, edge states, and recovery behavior. Mobbin is treated as product evidence rather than an authority: branding, copy, data, and complete competitor layouts are never copied.

If Mobbin is unavailable, the workflow continues with `ui-ux-pro-max` and the built-in quality standard. Mobbin is never installed or authenticated silently.

The substantial-flow sequence is: Mobbin evidence → `ui-ux-pro-max` guidance → `design-system` structure → `impeccable` critique → editable Figma execution and QA.

## Install from GitHub

Requirements:

- Codex or the ChatGPT desktop app with plugin support;
- GitHub access to this public repository;
- a Figma connection for editable Figma work.

Add the public marketplace:

```powershell
codex plugin marketplace add digitalklondike/wireframes-toolkit
```

Install the plugin:

```powershell
codex plugin add wireframes-toolkit@wireframes-toolkit
```

On Windows PowerShell, use `codex.cmd` when the execution policy blocks `codex.ps1`.

Restart the ChatGPT desktop app and start a new Codex task after the first installation so skill discovery and Figma wiring refresh correctly.

## Prepare dependencies

Run the bundled setup skill once:

```text
$wireframes-toolkit:setup
```

Setup audits the current installation, reports Figma and optional Mobbin availability, shows the exact missing skill packages and sources, requests one explicit confirmation, and installs only approved missing skills.

Dependency behavior:

- `figma-use` is required before editable `use_figma` operations.
- `ui-ux-pro-max` is recommended for UX pattern and anti-pattern evidence.
- `design-system` is recommended for components, variants, spacing, and state structure.
- `impeccable` is recommended for final product UX critique and hardening.
- Mobbin is an optional Codex app for real-product reference research.
- Figma and Mobbin authentication are separate from skill installation.
- No third-party skill or app is installed without explicit user consent.

Manual skill installation is available when needed:

```powershell
npx skills add openai/skills --skill figma-use -g -a codex -y
npx skills add pbakaus/impeccable --skill impeccable -g -a codex -y
npx skills add nextlevelbuilder/ui-ux-pro-max-skill --skill ui-ux-pro-max --skill design-system -g -a codex -y
```

On Windows PowerShell, use `npx.cmd` when `npx.ps1` is blocked. External skill repositories are mutable upstream sources and skills execute with agent permissions, so review them before installation.

## Use the plugin

Invoke the main skill in a new task:

```text
$wireframes-toolkit:wireframes
```

Example requests:

```text
Use $wireframes-toolkit:wireframes to turn this PRD into a complete desktop Figma flow. Research comparable upload and document-management patterns in Mobbin first.
```

```text
Use $wireframes-toolkit:wireframes to audit these Figma screens for UX, Auto Layout, clipping, duplicated actions, missing states, and weak component reuse. Fix confirmed issues.
```

```text
Use $wireframes-toolkit:wireframes to extend this flow with empty, loading, permission, error, destructive confirmation, and recovery states.
```

For an audit-only request, the skill reports findings without modifying Figma. Ask it to fix or revise the flow when changes are desired.

## Update

Refresh the public marketplace and reinstall the current version:

```powershell
codex plugin marketplace upgrade wireframes-toolkit
codex plugin add wireframes-toolkit@wireframes-toolkit
```

Restart the ChatGPT desktop app and begin a new Codex task after updating.

## Repository layout

```text
.agents/plugins/marketplace.json
plugins/wireframes-toolkit/
  .codex-plugin/plugin.json
  skills/setup/
  skills/wireframes/
    SKILL.md
    agents/openai.yaml
    references/
```

The distributable plugin lives under `plugins/wireframes-toolkit`. Meaningful behavior changes increment the semantic version and are documented in `CHANGELOG.md`.
