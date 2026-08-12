# Registry contract

`registry.json` implements `mix_workspace_ops.registry/v1`.

Each repository has a stable lowercase ID, `owner/repository` GitHub identity,
default branch, and projects. Each project has a stable ID, unique Mix
application identity, repository-relative path, kind, tags, and profile
reference.

Allowed kinds are `standalone`, `workspace_root`, `package`, and `tooling`.
Paths must be relative, may not escape the repository, and may not enter `.git`,
`deps`, `_build`, or operator state. Every application identity is globally
unique so a declared Mix dependency maps to one project without a hidden
precedence rule.

The registry deliberately omits dependency edges, version requirements,
package versions, source overrides, absolute checkout paths, credentials, CI
commands, and release ordering. Those values belong to current Mix/Weld metadata
or machine-local operator state.
