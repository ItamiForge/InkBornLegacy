# Core loop

Status: Partial (structure locked; numbers and fiction stub)

## Locked loop

1. **Prepare** — shop phase in the Battlegrounds family: buy, sell, roll, freeze, upgrade.
2. **Save loadout** — the board/team is a snapshot (async; no live lobby of 8).
3. **Match** — system picks another player’s snapshot (rules TBD).
4. **Combat** — `packages/sim` runs; neither player acts during combat.
5. **Watch** — client plays the event log (cards and shared VFX).
6. **Results** — outcome stored; ladder/season handling TBD.
7. **Collection** — PAC-like depth (unlocks, synergies, items, heroes). Exact systems TBD.

## Out of the primary loop

- Live 8-player simultaneous matches
- Real-time action during combat

## Unresolved

- Whether prepare+fight is one continuous “run” with HP like Battlegrounds, or discrete one-off matches like a snapshot duelist
- Streaks, interest, shared shop vs private shop
- When the snapshot is published (after each round vs when the player queues)
