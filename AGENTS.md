# Agent Context

`aatemplate` is the source Copier template project for this workspace.

All other sibling projects under `c:\prj\p2p\ongithub` are Copier-managed targets that should be synced/updated from `aatemplate` (not treated as the template source).

Never generate or keep `.cmd` or `.ps1` scripts in template outputs; use Python scripts instead.

## Template-First Change Policy

For Copier-managed projects in this workspace:

1. Do not apply template-applicable changes directly in child repos.
2. Apply template-applicable changes in `aatemplate` first.
3. Propagate those changes to child repos only through `copier update`.
4. Direct child-repo edits are allowed only for repo-specific changes that are not template-applicable.

## Standardization

All projects in `c:\prj\p2p\ongithub` should follow the same coding guidelines, high-level design approaches, configuration handling, etc. They should all be consistent among each other.

## Module Template Entrypoint Policy

`aatemplate` is module-first. Do not add `src/<package>/main.py` as a required template file.

If executable support is needed, keep it in `src/<package>/__main__.py` only, so `python -m <package>` works without a separate `main.py`.
