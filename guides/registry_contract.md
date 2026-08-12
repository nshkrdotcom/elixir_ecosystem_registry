# Registry contract

`registry.json` implements `mix_workspace_ops.registry/v1`.

Each repository has a stable lowercase ID, `owner/repository` GitHub identity,
default branch, and projects. Each project has a stable ID,
repository-relative path, kind, tags, and profile reference. Application
projects also have a globally unique Mix application identity. A genuine
non-application `workspace_root` or `tooling` project uses JSON `null` for
`app`; it remains addressable by project ID but never participates in
dependency-name resolution.

Allowed kinds are `standalone`, `workspace_root`, `package`, and `tooling`.
Paths must be relative, may not escape the repository, and may not enter `.git`,
`deps`, `_build`, or operator state. Every non-null application identity is
globally unique so a declared Mix dependency maps to one project without a
hidden precedence rule. Real Mix projects beneath `examples/` are inventory,
not generated noise; their presence does not turn an otherwise standalone root
into a workspace or change that root's stable ID.

The registry deliberately omits dependency edges, version requirements,
package versions, source overrides, absolute checkout paths, credentials, CI
commands, and release ordering. Those values belong to current Mix/Weld metadata
or machine-local operator state.
