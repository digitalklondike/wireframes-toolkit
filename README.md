# Wireframes Toolkit

A public Codex marketplace that distributes the `wireframes` skill for creating and auditing editable black-and-white Figma wireframes.

## Install from GitHub

Add the public marketplace:

```powershell
codex plugin marketplace add digitalklondike/wireframes-toolkit
```

Install the plugin:

```powershell
codex plugin add wireframes-toolkit@wireframes-toolkit
```

On Windows PowerShell, use `codex.cmd` when the local execution policy blocks `codex.ps1`. Restart the ChatGPT desktop app and begin a new Codex task after the first installation.

The repository is public, so recipients can install and update the marketplace without being added as GitHub collaborators.

Run the bundled dependency setup once:

```text
$wireframes-toolkit:setup
```

Setup checks what is already installed, shows the exact missing packages and sources, requests one confirmation, then installs only the approved missing companions. Start a new Codex task after setup and invoke `$wireframes-toolkit:wireframes`.

## Companion behavior

The plugin does not silently install third-party skills. Use `$wireframes-toolkit:setup` for the guided installation flow.

At the beginning of a substantial wireframing task, `wireframes` compares the available-skills catalog with its companion list:

- `figma-use` is required before any `use_figma` operation. If missing, editable Figma execution stops and Codex offers the verified installation command.
- `ui-ux-pro-max`, `design-system`, and `impeccable` are recommended. If any are missing, Codex mentions them once and continues with the built-in quality standard unless the user chooses to install them.
- No installation command runs without explicit user consent.

Install the required Figma execution skill:

```powershell
npx skills add openai/skills --skill figma-use -g -a codex -y
```

Install the recommended quality companions:

```powershell
npx skills add pbakaus/impeccable --skill impeccable -g -a codex -y
npx skills add nextlevelbuilder/ui-ux-pro-max-skill --skill ui-ux-pro-max --skill design-system -g -a codex -y
```

On Windows PowerShell, use `npx.cmd` when `npx.ps1` is blocked. Review external skills before installation because skills run with agent permissions.

The Figma MCP dependency is declared by `skills/wireframes/agents/openai.yaml`. The recipient may still need to authenticate or reconnect Figma after installing the plugin.

## Update

Refresh the GitHub marketplace and reinstall the current plugin version:

```powershell
codex plugin marketplace upgrade wireframes-toolkit
codex plugin add wireframes-toolkit@wireframes-toolkit
```

Start a new Codex task after updating so the new skill instructions are loaded.

## Repository layout

```text
.agents/plugins/marketplace.json
plugins/wireframes-toolkit/
  .codex-plugin/plugin.json
  skills/wireframes/
    SKILL.md
    agents/openai.yaml
    references/
```

## Development

The distributable plugin lives under `plugins/wireframes-toolkit`. Increment its semantic version and document meaningful behavior changes in `CHANGELOG.md` before sharing an update.
