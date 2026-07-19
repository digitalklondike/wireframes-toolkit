---
name: setup
description: Audit and install the companion skills used by Wireframes Toolkit. Use when the user explicitly invokes setup, asks to prepare Wireframes dependencies, or wants to diagnose missing figma-use, impeccable, ui-ux-pro-max, or design-system skills. Check what is already available, request consent before installation, install only missing skills from approved public source locations, validate the result, and explain Figma connection or restart requirements.
---

# Wireframes Setup

Prepare the current Codex installation for the complete Wireframes workflow. Keep installation transparent and optional.

## Safety boundaries

- Compare the current available-skills catalog before running commands. Treat an exact name or a plugin-qualified name ending in `:<name>` as catalog-available, but do not claim that name matching verifies version, contents, or provenance.
- Never reinstall an available skill merely to standardize its location or version.
- Before any installation, show the missing skills, repositories, commands, and user-level scope. Request one explicit confirmation that names every package to be installed.
- Do not treat invoking this skill as permission to install third-party code. An explicit confirmation after the audit is still required.
- Install globally for Codex only with `-g -a codex -y`. Never use `--all` and never install an entire repository when a specific `--skill` selection is available.
- Run installation commands sequentially. Stop on the first failure and report its output; do not improvise a different source or broaden the install scope.
- Do not request or expose GitHub tokens, npm tokens, passwords, or other credentials.
- If the user asks only for an audit, report status without changing anything.

## Dependency matrix

| Skill | Role | Requirement | Approved source location |
|---|---|---|---|
| `figma-use` | Safe `use_figma` execution | Required for editable Figma operations | `openai/skills` |
| `ui-ux-pro-max` | UX research and pattern evidence | Recommended | `nextlevelbuilder/ui-ux-pro-max-skill` |
| `design-system` | Components, states, spacing, and type structure | Recommended | `nextlevelbuilder/ui-ux-pro-max-skill` |
| `impeccable` | Product UX critique and hardening | Recommended | `pbakaus/impeccable` |

The source locations above identify the intended public repositories; they are mutable upstream sources, not cryptographic pins. Disclose this before installation and never substitute a similarly named repository.

The Figma MCP connection is separate from `figma-use`. The Wireframes skill declares the Figma MCP dependency, but the user may still need to install, enable, authenticate, or reconnect the Figma plugin.

## Workflow

### 1. Audit

1. Inspect the available-skills catalog for all four names. Use `Already available` or `Missing` as the skill status.
2. Use filesystem checks only as secondary evidence when the catalog is ambiguous. Common user-level roots are `~/.agents/skills` and `~/.codex/skills`.
3. Resolve the installer executable before requesting consent. On Windows, prefer `npx.cmd` directly; on other platforms use `npx`. If it is unavailable, report the blocker and do not propose an installation command that cannot run.
4. Separately check Figma. Report `MCP unavailable` when no Figma tools are registered. When a read-only `whoami` tool is available, call it once: report `Connected` on success and `Needs reconnect` on an authentication or authorization failure. Use `Not tested` only when connectivity cannot be checked without expanding the requested scope.
5. Report the catalog match and its limitation: availability by name does not verify the installed skill's version or origin.

If all four skills are available, do not run an installer. Report that Wireframes is ready and mention only unresolved Figma authentication, if any.

### 2. Confirm

For missing skills, show only the commands that would actually run, using the executable resolved during the audit. Explain that skills execute with agent permissions, the approved repositories are mutable upstream sources, and selected skills should be reviewed before installation. Ask for one confirmation covering the complete proposed set.

### 3. Install

Use `npx.cmd` on Windows and `npx` on other platforms. Replace `npx` in the examples below with the resolved executable before showing commands for consent.

Install `figma-use` only when missing:

```powershell
npx skills add openai/skills --skill figma-use -g -a codex -y
```

Install `impeccable` only when missing:

```powershell
npx skills add pbakaus/impeccable --skill impeccable -g -a codex -y
```

Install the missing skills from the shared UI/UX repository in one command. Include only the missing `--skill` arguments:

```powershell
npx skills add nextlevelbuilder/ui-ux-pro-max-skill --skill ui-ux-pro-max --skill design-system -g -a codex -y
```

Run commands sequentially and preserve their real output. Do not suppress security or trust warnings.

### 4. Validate

1. Require a zero exit code from every installer.
2. Check for each installed skill's `SKILL.md` under the user-level Codex skill locations or installer-reported destination.
3. Do not claim the current task has dynamically loaded a newly installed skill unless it appears in the available-skills catalog.
4. Tell the user to start a new Codex task after installation so skill discovery and MCP wiring refresh safely.
5. In the final report, list each skill as `Already available`, `Missing`, `Installed`, `Failed`, or `Not requested`. Report Figma separately as `Connected`, `Needs reconnect`, `MCP unavailable`, or `Not tested`.

Do not start a wireframing task from this setup skill. Finish setup and direct the user to invoke `$wireframes-toolkit:wireframes` in a new task.
