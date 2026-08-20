# Cross-domain decisions

CDRs (Cross-Domain Decision Records) live here. Each CDR is a single markdown file using `../standards/templates/cdr-template.md`.

## Naming

`CDR-NNN-short-title.md` — sequential numbering, kebab-case title.

## Lifecycle

1. **Proposed** — drafted by any role using `raise-cdr` command or the issue template.
2. **Accepted** — approved by the Leadership Forum (Domain Leads of affected domains + Leader; Admin co-signs propagation).
3. **Deprecated** — replaced by a newer CDR; reason recorded; superseding CDR linked.
4. **Superseded** — explicitly replaced (Status field: `Superseded by CDR-YYY`).

## Below ~20 people

The CDR/ADR split collapses. Every decision is an ADR in the relevant domain with an `affected-domains: [list]` frontmatter field. Use `../standards/templates/cdr-light-template.md`. This folder may stay near-empty.

## Audit trail

Every PR that closes a propagation action carries `Closes CDR-XXX` in its description. The Admin records the merged PR's SHA in the Leadership repo's `cadence/propagation-log.md`. The `propagation-sla.yml` workflow opens an issue for any propagation action open >30 days.
