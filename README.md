<p align="center">
  <img src="assets/elixir_ecosystem_registry.svg" width="200" alt="Elixir Ecosystem Registry logo" />
</p>

<p align="center">
  <a href="https://github.com/nshkrdotcom/elixir_ecosystem_registry">
    <img alt="GitHub: nshkrdotcom/elixir_ecosystem_registry" src="https://img.shields.io/badge/GitHub-nshkrdotcom%2Felixir__ecosystem__registry-0b0f14?logo=github" />
  </a>
  <a href="https://github.com/nshkrdotcom/elixir_ecosystem_registry/blob/main/LICENSE">
    <img alt="License: MIT" src="https://img.shields.io/badge/license-MIT-0b0f14.svg" />
  </a>
</p>

# Elixir Ecosystem Registry

Canonical machine-readable identities, classifications, views, and operational
profiles for the complete `nshkrdotcom` Elixir ecosystem.

This repository is data, not build machinery. It has no `mix.exs`, executable,
runtime dependency, dependency-edge policy, package-version policy, or Hex
release. Generic consumers such as Mix Workspace Ops load it explicitly and bind
its portable GitHub identities to operator-owned checkouts.

The 2026-08-11 canonical pass resolved 161 repositories and 578 unique Mix
applications. It also retained 56 ambiguous or non-application observations in
the dated snapshot instead of guessing identities. The NSHKR view selects 368
projects from 43 classified repositories; the global view selects all 578.

## Authority

The registry owns only:

- stable repository and Mix-project identities;
- GitHub coordinates and relative project paths;
- application identity used to map current Mix dependencies;
- project classification tags and operational-profile references;
- named views over the one global inventory;
- dated drift and migration evidence.

Each project's `mix.exs` remains authoritative for dependencies, requirements,
version, and package contents. Projected poncho packages keep their projection
metadata in their owning repository. The registry never duplicates either.

## Layout

- `registry.json` — one canonical row per repository and Mix project.
- `views/all.json` — the entire resolved registry.
- `views/nshkr.json` — a tag-selected NSHKR platform subset, not a copied list.
- `profiles/operator_profiles.json` — shared operational classifications.
- `snapshots/` — dated observations and unresolved identities; evidence only.
- `guides/` — protocol, view, and drift rules.

## Validate and bind

Build Mix Workspace Ops from its independent source repository, then run:

```bash
mix_workspace_ops registry validate \
  --registry /path/to/elixir_ecosystem_registry/registry.json

mix_workspace_ops registry select \
  --registry /path/to/elixir_ecosystem_registry/registry.json \
  --view /path/to/elixir_ecosystem_registry/views/nshkr.json

mix_workspace_ops doctor \
  --registry /path/to/elixir_ecosystem_registry/registry.json \
  --checkout-root /path/to/operator/checkouts
```

Bindings are machine-local and untracked. A normal checkout uses the repository
basename under the supplied checkout root. Exceptional layouts require an
explicit operator-owned binding file; they are never encoded in this registry.

The initial snapshot also records the portable migration surface for 51 copied
dependency-source helpers and 50 adjacent configs across 41 canonical
repositories. It stores repository identities, relative paths, commits, status,
and content digests—never checkout paths, credentials, or dependency policy.

See [Registry contract](guides/registry_contract.md),
[Views](guides/views.md), and
[Registration and drift](guides/registration_and_drift.md).
