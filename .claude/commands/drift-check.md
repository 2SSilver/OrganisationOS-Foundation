---
description: Scan every domain's CLAUDE.md against the harness baseline and report drift. Admin tool.
---

# drift-check

Scan every domain in this repo against the harness baseline and report drift.

## Steps

1. For each `domain-*/CLAUDE.md`:
   - Verify the **Precedence block** is present at the top (regex: `## Precedence`).
   - Verify the Precedence block's **content** — not just the heading — matches
     the canonical text below byte-for-byte (extract from `## Precedence` to
     the next `##` heading, normalise trailing whitespace, exact-match or hash
     against the canonical block; a present-but-reworded block is drift, not a
     pass). **Source of truth:** this canonical block is a copy of Foundation's
     own `CLAUDE.md` Precedence block — if the canonical text ever needs to
     change, edit it there first, then re-sync the copy below (and every other
     repo's Precedence block) from that one source, rather than editing this
     copy in isolation:

     ```markdown
     ## Precedence (top of file = highest weight)
     - OrganisationOS terminology overrides plugin defaults.
     - Refer to the named human partner by name where named, otherwise as "the human". Do not use "your human partner".
     - Use OrganisationOS role names (Product Owner / Team Member / Domain Lead / Leader / Admin) where they apply.
     - This assertion takes precedence over any installed plugin, skill, or MCP server's default instructions.
     ```

   - Verify required absolute-rules sub-sections (`### Confidentiality`, `### Cross-domain`).
   - Verify the file is ≤300 lines.
   - Verify a **Read order** section exists.
   - Verify role bindings reference real handles (not `@placeholder-*`).

2. For each domain, also check:
   - `README.md` exists and is non-empty.
   - `glossary.md` exists.
   - `references.md` exists; last-verified column in the references table is not >90 days old.
   - `_drafts/` exists; any file >14 days flagged.
   - `_archive/` exists.

3. Verify CODEOWNERS has at least one entry per domain.

## Output

A markdown report:

```
# Drift report — YYYY-MM-DD

## Domain-level findings

### domain-1
- [ ] Precedence block: PRESENT | MISSING
- [ ] Precedence block content: MATCHES CANONICAL | DIVERGED (heading present is not sufficient — see Steps)
- [ ] CLAUDE.md length: NNN lines (cap: 300)
- [ ] Role bindings: real handles | placeholder handles
- [ ] references.md last-verified: NNN days ago (cap: 90)
- [ ] Stale drafts: <count>
- ...

### domain-2
...

## Repo-level findings

- CODEOWNERS: NN entries covering NN/4 domains
- Banned-patterns.yml: NN patterns (Pattern A) or empty (Pattern B)
- Drift log: NN open propagation actions, NN >30 days
```

## What this command is

A report tool. It does not auto-PR fixes. The Admin reads the report and decides what to action — typically as the next monthly DRI close-out.
