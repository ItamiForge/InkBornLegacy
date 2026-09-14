# Data model

Status: Stub (table names from architecture discussion only)

Exact columns, keys, RLS, and enums: TBD. Do not add extra tables for undecided features.

## Named in discussion

- `profiles`
- `loadouts` (snapshots)
- `replays`
- `ladder`
- `seasons`

## Implied by architecture (placeholder)

- `sim_version` / `content_version` on replays
- Steam id or auth uid on profiles

## RLS

TBD. Ranked writes must not be client-updatable for `winner`.

## ER

Not drawn until columns are decided.
