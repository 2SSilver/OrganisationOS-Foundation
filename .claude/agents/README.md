# .claude/agents/ — Claude Code mirror

These agent definitions mirror `.github/agents/` (the Copilot-CLI-native location). Claude Code does not yet read `.github/agents/` natively, so the harness ships this mirror as a thin wrapper (§14 of the Implementation Guideline).

**Source of truth:** `.github/agents/`. When you edit an agent definition, edit it in `.github/agents/` and copy the change here so both stay identical. The monthly DRI (§13.5) includes a check that the two folders have not drifted.

Adopters on Cursor / Codex CLI invoke the same agents via their tool's mechanism (skills, prompt files, etc.).
