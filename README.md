# Wireframes Toolkit

Wireframes Toolkit is a public Codex plugin for researching, creating, extending, and auditing editable black-and-white product wireframes, especially in Figma.

It turns product briefs, requirements, journeys, and rough ideas into complete low- or mid-fidelity flows with intentional Auto Layout, reusable components, realistic states, responsive behavior, and screenshot-verified structural QA. The workflow is universal: supplied examples inform quality and construction, never the product domain or interface copy.

## Install — follow these steps

There are two places where you will type things:

- **Windows PowerShell or macOS Terminal:** use it for commands beginning with `codex` or `codex.cmd`.
- **A new Codex task in the ChatGPT desktop app:** use its message box for commands beginning with `$wireframes-toolkit:`.

Copy one command at a time and press Enter after each command.

### Windows

1. Open the **Start** menu, search for **PowerShell**, and open it.
2. Check that the Codex CLI is installed:

   ```powershell
   codex.cmd --version
   ```

   If a version number appears, continue. If PowerShell says the command does not exist, install Codex CLI, close PowerShell, reopen it, and run the version check again:

   ```powershell
   npm.cmd install --global @openai/codex
   ```

3. Add the public Wireframes marketplace:

   ```powershell
   codex.cmd plugin marketplace add digitalklondike/wireframes-toolkit
   ```

4. Install Wireframes Toolkit:

   ```powershell
   codex.cmd plugin add wireframes-toolkit@wireframes-toolkit
   ```

5. Continue with [Finish setup in Codex](#finish-setup-in-codex).

### macOS

1. Press **Command + Space**, type **Terminal**, and open it.
2. Check that the Codex CLI is installed:

   ```bash
   codex --version
   ```

   If a version number appears, continue. If Terminal says the command does not exist, install Codex CLI, close Terminal, reopen it, and run the version check again:

   ```bash
   npm install --global @openai/codex
   ```

3. Add the public Wireframes marketplace:

   ```bash
   codex plugin marketplace add digitalklondike/wireframes-toolkit
   ```

4. Install Wireframes Toolkit:

   ```bash
   codex plugin add wireframes-toolkit@wireframes-toolkit
   ```

5. Continue with [Finish setup in Codex](#finish-setup-in-codex).

### Finish setup in Codex

These steps are the same on Windows and macOS:

1. Fully close and reopen the ChatGPT desktop app.
2. Start a **new Codex task**.
3. Paste the following into the **Codex message box**, not PowerShell or Terminal, and send it:

   ```text
   $wireframes-toolkit:setup
   ```

4. Setup reports what is already available and what is missing. If it proposes installing companion skills, review the listed sources and approve only if you agree.
5. If setup installs anything, fully restart the app and start another new Codex task.
6. To use the plugin, paste this into the Codex message box and add your request after it:

   ```text
   $wireframes-toolkit:wireframes

   Turn the attached product requirements into a complete desktop Figma wireframe flow.
   ```

7. For editable Figma work, complete the Figma connect or reconnect prompt if Codex shows one. Mobbin is optional and can be enabled separately when reference research is needed.

## What the plugin does

- Frames the actor, job to be done, entry point, success outcome, constraints, and business rules.
- Builds a minimum complete screen and state inventory before drawing.
- Optionally researches comparable real-product flows and screen compositions in Mobbin, then produces a layout-evidence matrix instead of copying a competitor.
- Chooses tables, lists, cards, split views, timelines, staged flows, forms, or mixed compositions from the content shape rather than defaulting to one generic layout.
- Includes navigation, action, object, and status icons plus meaningful grayscale visual anchors in the first draft.
- Creates native editable Figma layers rather than flattened images.
- Uses nested Auto Layout and deliberate `FILL`, `HUG`, and `FIXED` sizing without empty Spacer layers.
- Promotes repeated shells, navigation, toolbars, tables, dialogs, and state panels into reusable components.
- Classifies revisions as local, state-level, or system-level and propagates shared changes through component sources to every affected screen.
- Stress-tests buttons, cards, rows, and action groups at minimum, nominal, expanded, and long-content widths.
- Uses component variants for systematic states such as button appearance, active navigation, selection, loading, or disabled behavior.
- Covers relevant empty, loading, error, permission, success, destructive, quota, overflow, and recovery states.
- Keeps menus anchored to triggers, dialogs centered over full-screen scrims, search clearing inside the field, and standalone states centered in fill-remaining regions.
- Audits clipping, overflow, section collisions, duplicated actions, broken instances, fragile fixed widths, missing Auto Layout, and component duplication.
- Adapts layouts by recomposing for desktop, mobile, or responsive views instead of shrinking a desktop canvas.

The output stays monochrome and product-focused. This plugin is not intended for branded high-fidelity visual design, illustration, or marketing artwork.

## Research workflow

For substantial or unfamiliar flows, Wireframes can use the optional Mobbin app to inspect real screens and multi-step journeys before finalizing the screen inventory.

The skill searches one interaction at a time, uses the correct platform, inspects the returned images, compares multiple relevant products, and extracts sequencing, content morphology, composition, density, whitespace rhythm, visual anchors, information hierarchy, progressive disclosure, edge states, and recovery behavior. Mobbin is treated as product evidence rather than an authority: branding, copy, data, and complete competitor layouts are never copied.

If Mobbin is unavailable, the workflow continues with `ui-ux-pro-max` and the built-in quality standard. Mobbin is never installed or authenticated silently.

The substantial-flow sequence is: Mobbin evidence → `ui-ux-pro-max` guidance → `design-system` structure → `impeccable` critique → editable Figma execution and QA.

## What setup checks

- `figma-use` is required before editable `use_figma` operations.
- `ui-ux-pro-max` is recommended for UX pattern and anti-pattern evidence.
- `design-system` is recommended for components, variants, spacing, and state structure.
- `impeccable` is recommended for final product UX critique and hardening.
- Mobbin is an optional Codex app for real-product reference research.
- Figma and Mobbin authentication are separate from skill installation.
- No third-party skill or app is installed without explicit user consent.

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

### Windows

```powershell
codex.cmd plugin marketplace upgrade wireframes-toolkit
codex.cmd plugin add wireframes-toolkit@wireframes-toolkit
```

### macOS

```bash
codex plugin marketplace upgrade wireframes-toolkit
codex plugin add wireframes-toolkit@wireframes-toolkit
```

After updating, fully restart the ChatGPT desktop app and begin a new Codex task.

## Troubleshooting

- **`codex` or `codex.cmd` is not recognized:** install the Codex CLI with the npm command shown in the operating-system instructions, then reopen the terminal.
- **`npm` or `npm.cmd` is not recognized:** install Node.js with npm, reopen the terminal, and repeat the Codex CLI installation step.
- **The plugin installed but the skill is not visible:** fully restart the ChatGPT desktop app and start a new Codex task.
- **Figma tools are unavailable:** enable or reconnect Figma, then start a new task.
- **Mobbin is unavailable:** continue without it or enable the optional Mobbin plugin for real-product reference research.

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
