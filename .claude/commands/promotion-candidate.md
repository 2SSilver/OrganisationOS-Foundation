---
description: Surface practices in one domain that recur across others. Candidates for promotion into Foundation. Admin tool.
---

# promotion-candidate

Find practices in one domain that recur across others. Candidates for promotion into Foundation (cross-domain shared content).

## Definitions

- **Practice** = a methods file (`<domain>/methods/*.md` or equivalent), a skill (`<domain>/.claude/skills/`), or a template (`<domain>/templates/`).
- **Recurrence threshold** = ≥2 other domains have files matching the candidate's title or first-paragraph keywords.

## Steps

1. For each domain, list practices (methods, skills, templates).
2. For each practice in domain D1, scan domains D2..DN for files with:
   - Same or near-same title (fuzzy match)
   - First-paragraph keyword overlap ≥40%
3. Group matches across ≥2 other domains as candidates.

## Output

A markdown report:

```markdown
# Promotion candidates — YYYY-MM-DD

## Strong candidates (recurring in ≥3 domains)

### "<practice name>"
- Original: domain-1/methods/<file>.md
- Also in: domain-2/methods/<file2>.md, domain-3/methods/<file3>.md
- Variance: <one sentence on how the files differ>
- Recommended action: promote a shared version to Foundation's standards/, retire the domain copies.

## Weak candidates (recurring in 2 domains)

### "<practice name>"
- ...
- Recommended action: investigate before promoting — may still be intentionally different.
```

## What this command is NOT

- Not a promotion executor. The Admin reads the report and decides whether to PR a promotion.
- Promotions are two-approver PRs touching Foundation (Admin + Leader per CODEOWNERS).
