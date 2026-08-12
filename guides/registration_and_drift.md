# Registration and drift

Registration begins with a canonical Git root whose directory basename matches
its GitHub repository name and whose Git common directory is its own `.git`.
Worktrees, alternate clones, backups, generated packages, private unrelated
trees, and fixture Mix projects are not canonical rows.

Discovery evaluates `mix.exs` in an isolated Elixir process without loading
`config/runtime.exs`, starting the application, compiling project code, or
checking dependencies. A project is registered only when its application
identity is available and globally unambiguous. Failures enter the dated
unresolved ledger; they are never guessed from a filename.

Generated dependency trees, `_legacy` archives, fixtures, backups, worktrees,
and vendored source are pruned before metadata evaluation. If one exact
standalone repository owns an application identity, shadow copies are recorded
as unresolved evidence and the exact standalone identity remains canonical.

Validation compares the recorded application identity to current Mix metadata.
Binding additionally verifies Git root, common directory, origin, branch, and
the explicit checkout root. Machine-local paths and exceptional bindings remain
untracked operator state.

Snapshots preserve observations and migration receipts. They are not consulted
as dependency or compatibility policy.
