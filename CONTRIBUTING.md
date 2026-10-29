# Contributing

Thanks for helping. Each `watchtower-<name>` repository is a published mirror of a directory in the
Watchtower monorepo, so pull requests are welcome here and are applied upstream by maintainers; the
mirror is then re-synced. A PR may therefore be closed with a note once its change lands upstream.

## Before you start

* Search existing issues. For anything larger than a bug fix, open a feature request first.
* Read the [Code of Conduct](CODE_OF_CONDUCT.md). Report vulnerabilities privately ([SECURITY.md](SECURITY.md)).

## Pull requests

1. Fork, branch from `main`, keep the change focused.
2. Add or update tests; CI in the repository must pass (`ci.yml`).
3. Update `CHANGELOG.md` for user-visible changes.
4. Use conventional commit messages: `feat:`, `fix:`, `docs:`, `test:`, `chore:`.
5. No sign-off needed; by submitting you license your change under the repository's Apache-2.0 license.

## Rules every SDK follows

* Thin over the official OpenTelemetry SDK for the language; add only Watchtower value.
* Configuration names are identical everywhere: `WT_INGEST_KEY`, `WT_OTLP_ENDPOINT` (default
  `http://localhost:4318`), `WT_SERVICE`, `WT_ENVIRONMENT`, `WT_RELEASE`. Client SDKs take a publishable key option.
* Keys are sent as `Authorization: Bearer <key>`, masked in debug or string output and never logged.
* Caller-supplied `wt.*` attributes are dropped: tenant identity comes only from the key.
* No product analytics, feature flags or experiments inside SDKs.
* Source files stay at or under 650 lines.
