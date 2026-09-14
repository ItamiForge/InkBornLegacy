# Simulation

Status: Default

Package: `packages/sim`

## Function

```text
sim(boardA, boardB, seed) -> { result, events }
```

- Pure. No I/O, no `Date.now()`, no RNG other than a seeded PRNG inside the function.
- Integer math only.
- Identical output in browser and on server for the same inputs and package version.

## Versioning

Replays must store **sim version** + **content version**. Old replays replay on the version they were created with, or are marked not re-simulable. Exact policy TBD; the fields are required.

## Clients of the sim

1. Server match resolver (authoritative)
2. Client playback (animation; may use stored events without re-running)
3. Optional sandbox (local, not ranked)

## Implementation notes

- Event types are a Zod union.
- Content (stats, synergy hooks) is data from `packages/content`, not hardcoded unit names in the sim core.
- No combat rules written until [combat design](../design/combat.md) is filled.
