# Views

Views implement `mix_workspace_ops.view/v1`. They are selectors, not manifests.
They may include projects by tag, require tags, include stable project IDs, and
exclude stable project IDs. They never copy repository or project rows.

`views/all.json` selects the common `ecosystem` tag. `views/nshkr.json` selects
`platform.nshkr`. A project may participate in several platforms without
duplicating its canonical identity.

Changing a view changes scope only. It cannot change a dependency edge, source,
version constraint, release version, or package contents.
