# Combat

Status: Default (architecture); Stub (rules)

## Locked

- Fully simulated. No player input during the fight.
- Deterministic: `(boardA, boardB, seed) → event log`.
- Integer math. No wall-clock in the sim.
- Same code on server and client (`packages/sim`).
- Server result is authoritative for ranked / stored outcomes.
- Client animates the log (card motion + VFX by damage type).
- Replay is stored and can be rewatched.

## Event log (shape only)

Exact event set TBD. Architecture expects a typed list, for example (names not final):

- `spawn` / `enter`
- `hit`
- `die`
- `synergy_proc`
- `item_proc`
- `end`

Zod schemas live with the sim. Do not invent the full catalog here.

## Stub — combat rules

- Team size / positions: TBD
- Targeting: TBD
- Speed / initiative: TBD
- Damage types: TBD (VFX and SFX will key off whatever tags are chosen)
- Win condition: TBD
- Ties: TBD
- Interaction with synergies, items, heroes: TBD
