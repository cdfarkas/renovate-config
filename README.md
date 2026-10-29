# renovate-config

Shared [Renovate](https://docs.renovatebot.com/) config presets for `cdfarkas/*` repositories.

## Usage

Add a `renovate.json` to the target repository:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>cdfarkas/renovate-config"]
}
```

`github>cdfarkas/renovate-config` resolves to [`default.json`](default.json).

## What `default.json` does

- Weekly run (Monday night, Europe/Paris) to keep the noise down.
- Groups updates and caps open PRs (5 concurrent, 2/hour).
- Automerges patch, pin, digest and GitHub Actions updates.
- Minor updates are grouped into one PR you merge by hand; major updates stay individual.
- A dependency dashboard issue tracks everything pending.

## Per-language presets

Today a single `default.json` covers every consumer. When more repos appear, split
per language the way `stonal-tech/renovate-config` does (e.g. a `ts.json` extended
via `github>cdfarkas/renovate-config:ts`).
