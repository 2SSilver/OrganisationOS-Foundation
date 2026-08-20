# Interfaces

Cross-domain coupling. Each interface is a single markdown file describing how two or more domains co-produce something.

## Why a separate folder

Without it, cross-domain content drifts into one domain's tree and the other domain has no way to find it or contest it. With it, the joint work has a stable address and clear owners on both sides.

## How to add an interface

1. Use `../standards/templates/interface-template.md` as the starting shape.
2. File name: kebab-case, descriptive (e.g. `domain-2-intake-to-domain-3.md`).
3. CODEOWNERS routes the PR to both affected Domain Leads + the Leader.
4. Breaking changes require a CDR with a migration window.

## What does NOT go here

- Domain-internal coordination — that lives in the domain's own folder.
- One-off communications between two people — that is Slack or email, not an interface artefact.
- Aspirational future interfaces — only the interface for active or committed work.
