# Watchtower

Watchtower is a hosted observability platform: errors, traces, logs, profiles, session replay, releases
and LLM calls in one store, so an error links straight to the trace, log lines, profile, replay and deploy
behind it. Every SDK is a thin layer over the official OpenTelemetry SDK for its language and speaks
OTLP, so your instrumentation stays portable.

## Quick start

1. Create a project and copy an ingest key (server SDKs) or a publishable key (browser, mobile).
2. Install the package for your stack from the table below.
3. Set the environment and run your app:

```sh
export WT_INGEST_KEY=...                        # secret; server SDKs only
export WT_OTLP_ENDPOINT=https://<your-endpoint> # default http://localhost:4318
export WT_SERVICE=checkout WT_ENVIRONMENT=production WT_RELEASE=1.4.2
```

Keys are sent as `Authorization: Bearer <key>` and are never logged. Client SDKs take a publishable key
option instead and must never receive a secret key.

## SDKs

| Stack | Repository | CI |
|---|---|---|
| Browser (TypeScript) | [watchtower-browser](https://github.com/watchtowerobservability/watchtower-browser) | [![CI](https://github.com/watchtowerobservability/watchtower-browser/actions/workflows/ci.yml/badge.svg)](https://github.com/watchtowerobservability/watchtower-browser/actions/workflows/ci.yml) |
| Node.js | [watchtower-node](https://github.com/watchtowerobservability/watchtower-node) | [![CI](https://github.com/watchtowerobservability/watchtower-node/actions/workflows/ci.yml/badge.svg)](https://github.com/watchtowerobservability/watchtower-node/actions/workflows/ci.yml) |
| Python | [watchtower-python](https://github.com/watchtowerobservability/watchtower-python) | [![CI](https://github.com/watchtowerobservability/watchtower-python/actions/workflows/ci.yml/badge.svg)](https://github.com/watchtowerobservability/watchtower-python/actions/workflows/ci.yml) |
| Java | [watchtower-java](https://github.com/watchtowerobservability/watchtower-java) | [![CI](https://github.com/watchtowerobservability/watchtower-java/actions/workflows/ci.yml/badge.svg)](https://github.com/watchtowerobservability/watchtower-java/actions/workflows/ci.yml) |
| Ruby | [watchtower-ruby](https://github.com/watchtowerobservability/watchtower-ruby) | [![CI](https://github.com/watchtowerobservability/watchtower-ruby/actions/workflows/ci.yml/badge.svg)](https://github.com/watchtowerobservability/watchtower-ruby/actions/workflows/ci.yml) |
| PHP | [watchtower-php](https://github.com/watchtowerobservability/watchtower-php) | [![CI](https://github.com/watchtowerobservability/watchtower-php/actions/workflows/ci.yml/badge.svg)](https://github.com/watchtowerobservability/watchtower-php/actions/workflows/ci.yml) |
| .NET | [watchtower-dotnet](https://github.com/watchtowerobservability/watchtower-dotnet) | [![CI](https://github.com/watchtowerobservability/watchtower-dotnet/actions/workflows/ci.yml/badge.svg)](https://github.com/watchtowerobservability/watchtower-dotnet/actions/workflows/ci.yml) |
| Rust | [watchtower-rust](https://github.com/watchtowerobservability/watchtower-rust) | [![CI](https://github.com/watchtowerobservability/watchtower-rust/actions/workflows/ci.yml/badge.svg)](https://github.com/watchtowerobservability/watchtower-rust/actions/workflows/ci.yml) |
| iOS (Swift) | [watchtower-ios](https://github.com/watchtowerobservability/watchtower-ios) | [![CI](https://github.com/watchtowerobservability/watchtower-ios/actions/workflows/ci.yml/badge.svg)](https://github.com/watchtowerobservability/watchtower-ios/actions/workflows/ci.yml) |
| Android (Kotlin) | [watchtower-android](https://github.com/watchtowerobservability/watchtower-android) | [![CI](https://github.com/watchtowerobservability/watchtower-android/actions/workflows/ci.yml/badge.svg)](https://github.com/watchtowerobservability/watchtower-android/actions/workflows/ci.yml) |
| Go | [watchtower-go](https://github.com/watchtowerobservability/watchtower-go) | [![CI](https://github.com/watchtowerobservability/watchtower-go/actions/workflows/ci.yml/badge.svg)](https://github.com/watchtowerobservability/watchtower-go/actions/workflows/ci.yml) |

More packages (framework add-ons, build plugins, the setup wizard and the release GitHub Action) are
published as `watchtower-<name>` repositories in this organization as they ship.

## Verify what you install

Every release artifact carries a GitHub build attestation:

```sh
gh attestation verify <file> --repo watchtowerobservability/watchtower-<name>
```

## Contributing and security

See [CONTRIBUTING](https://github.com/watchtowerobservability/.github/blob/main/CONTRIBUTING.md) and
[SECURITY](https://github.com/watchtowerobservability/.github/blob/main/SECURITY.md). All repositories are
Apache-2.0 and are mirrors of the Watchtower monorepo.
