# Security policy

## Reporting a vulnerability

Do not open a public issue. Report privately with GitHub's "Report a vulnerability" button on the
repository's Security tab (private vulnerability reporting). Include the affected package and version,
reproduction steps and impact.

We acknowledge reports within 3 business days, share a fix timeline after triage, and credit reporters
who want it once a fix is released.

## Scope

All repositories in the `watchtowerobservability` organization: the SDKs, plugins, wizard, GitHub Action
and tooling. Problems in the hosted Watchtower service go through the same channel.

## Handling keys

If you find an ingest key, API token or publishable key committed anywhere, report it the same way and
revoke it in Watchtower. Secret keys are shown once and stored only as hashes; we cannot recover them.

## Supported versions

The latest released minor version of each package (0.x: the latest release only).

## Verifying releases

Every release artifact carries a GitHub build attestation:
`gh attestation verify <file> --repo watchtowerobservability/<repo>`.
