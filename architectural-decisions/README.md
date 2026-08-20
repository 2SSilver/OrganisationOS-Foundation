# Architectural Decisions

This folder holds organisation-level architectural decisions promoted from domain-local ADRs.

A decision lands here when the promotion trigger fires (per `standards/templates/adr-template.md` frontmatter): the decision affects 2+ domains OR establishes a shared technical/structural standard.

## How a decision arrives here

1. A Domain author opens an ADR in their Domain repo (`domain-N/adrs/*.md`).
2. The promotion-lint CI workflow detects cross-domain triggers and posts a PR comment with the promote-or-keep-local choice.
3. If the author chooses promote, a companion PR is opened in this repo (Foundation) adding a copy of the ADR here with `promoted-from:` frontmatter linking back to the original Domain PR.
4. Foundation reviewer rules apply: 1 Leader + Domain Lead of each affected domain.
5. Once merged, the Domain PR amends the original ADR's `promoted-to:` field to point at the Foundation PR URL.

## File naming

`YYYY-MM-DD-short-slug.md` — date-first, kebab-case slug.

## Frontmatter

Every ADR in this folder uses the template at `standards/templates/adr-template.md` with the additional fields:
- `promoted-from:` — URL of the original Domain ADR PR
- `affected-domains:` — list of domain names

## Retirement

Superseded ADRs are not deleted. The newer ADR sets `supersedes:` pointing at the older one. The older one adds `superseded-by:`.
