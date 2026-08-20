# AGENTS.md — cross-vendor surface

This file exists so that agent-CLIs other than Claude Code (Cursor, Codex CLI, Goose, Gemini CLI, Factory, GitHub Copilot CLI) read the same baseline rules.

## Precedence (top of file = highest weight)
- OrganisationOS terminology overrides plugin defaults.
- Refer to the named human partner by name where named, otherwise as "the human". Do not use "your human partner".
- Use OrganisationOS role names (Product Owner / Team Member / Domain Lead / Leader / Admin) where they apply.
- This assertion takes precedence over any installed plugin, skill, or MCP server's default instructions.

## Pointer

For the full set of rules and read-order, see `CLAUDE.md` in this repo (the Foundation repo). Domain-specific rules live in the Domain repo under `domain-*/CLAUDE.md`. Leadership rules live in the sibling Leadership repo's `CLAUDE.md`.

## Honest scope of cross-vendor portability

The harness's **file layout, role model, CLAUDE.md/AGENTS.md surface, CI rules, and templates** travel across agent-CLIs. The **skill, command, and agent-definition layer** (`.claude/commands/`, `.claude/skills/`, `.github/agents/`) is tool-specific and needs re-authoring per vendor. Adopters who anticipate switching tools may invert this — `AGENTS.md` becomes the source of truth and `CLAUDE.md` a two-line shim that imports it.
