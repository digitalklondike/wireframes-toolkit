# Companion Setup

Use this reference only when a companion skill is missing. Compare names against the current available-skills catalog; do not infer availability from filesystem paths alone.

## Required for editable Figma execution

`figma-use` is the mandatory prerequisite for every `use_figma` call. It is maintained in OpenAI's public skills repository.

```powershell
npx skills add openai/skills --skill figma-use -g -a codex -y
```

On Windows PowerShell, use `npx.cmd` instead of `npx` when the local execution policy blocks `npx.ps1`.

The Figma MCP connection is declared separately in `agents/openai.yaml`. Installing `figma-use` does not authenticate Figma; the user may still need to enable or reconnect Figma.

## Recommended quality companions

Install `impeccable`:

```powershell
npx skills add pbakaus/impeccable --skill impeccable -g -a codex -y
```

Install `ui-ux-pro-max` and `design-system` together from their shared repository:

```powershell
npx skills add nextlevelbuilder/ui-ux-pro-max-skill --skill ui-ux-pro-max --skill design-system -g -a codex -y
```

After installing skills, start a new Codex task if the current task does not discover them automatically.

## Runtime recommendation behavior

- Name only the missing companions.
- Explain the impact in one sentence: Figma execution is blocked without `figma-use`; the other companions improve research, system consistency, and critique but are optional.
- Offer the exact relevant command, but do not run it without explicit consent.
- If the user continues without optional companions, use `references/universal-quality.md` as the fallback and proceed.
