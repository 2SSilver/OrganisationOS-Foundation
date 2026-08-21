# Interface: <name>

## Providing domain

<domain name> (owner of the artefact this interface describes)

## Consuming domain(s)

<one or more domains that depend on the artefact>

## Scope

The joint output, the responsibility boundary between the domains, the artefacts each side produces.

## Inputs the consuming domain expects

- <input 1 — what it is, who produces it>
- <input 2>

## Outputs the providing domain commits to

- <output 1 — what it is, who consumes it>
- <output 2>

## Owners

- Providing-domain Product Owner: @<handle>
- Consuming-domain Product Owner: @<handle>
- Required reviewers: both Domain Leads + the Leader

## Versioning

Semver-style. Breaking changes increment major version and require a CDR + a migration window agreed in the CDR (default: 4 weeks) for any active work using the previous version. A migration-completion checkpoint gates window end: the consuming Domain Lead confirms in the propagation-log that consumption of the previous version has stopped.

## Active references

[List of current work in either domain that depends on this interface. Updated on-CDR by the Admin — refreshed whenever a CDR touches this interface, not on a fixed quarterly cadence.]
