# Registration and drift

Registration begins with a canonical Git root whose directory basename matches
its GitHub repository name and whose Git common directory is its own `.git`.
Worktrees, alternate clones, backups, generated packages, private unrelated
trees, and fixture Mix projects are not canonical rows.

Discovery queries actual Mix metadata without starting or compiling the
application. A project is registered only when its application identity is
available and globally unambiguous. Failures enter the dated unresolved ledger;
they are never guessed from a filename.

Validation compares the recorded application identity to current Mix metadata.
Binding additionally verifies Git root, common directory, origin, branch, and
the explicit checkout root. Machine-local paths and exceptional bindings remain
untracked operator state.

Snapshots preserve observations and migration receipts. They are not consulted
as dependency or compatibility policy.
