# Non-Functional Requirements (NFRs)

This folder holds organisation-wide non-functional requirements that all domains must adhere to.

NFRs originate either:

- Directly authored at Foundation (e.g. a Chief Product Owner declares a standard)
- Promoted from a domain context where the contributor recognised the cross-domain applicability

## Reviewer rules

Foundation reviewer rules apply: 1 Leader + Domain Lead of each affected domain. The "no single human satisfies two required-reviewer slots" rule holds.

## File naming

`YYYY-MM-DD-short-slug.md` — date-first, kebab-case slug.

## Frontmatter

Every NFR uses this minimal frontmatter:

```yaml
---
title: <short statement of the requirement>
authored-by: <handle>
authored-at: YYYY-MM-DD
affected-domains: [domain-1, domain-2, ...]   # use 'all' for organisation-wide
status: active | superseded | retired
supersedes: <slug>  # optional
superseded-by: <slug>  # optional
---
```

## Body sections

1. Statement (what is required)
2. Rationale (why)
3. Acceptance evidence (how a domain demonstrates compliance)
4. Exceptions (named, time-bounded)
5. Review cadence (when is this NFR revisited)
