# Roadmap

Status: Plan (order locked by dependencies; dates not set)

No calendar dates were decided. Order is what the stack and missing design imply.

## 0. Documentation (this PR)

- v0 clean slate
- Product, design stubs, architecture, asset method, checklists

## 1. Design fill-in (discussion)

- Lore, races, types, card kinds, economy, combat rules, modes
- Until this exists, do not generate portraits or write sim rules

## 2. Scaffold

- pnpm monorepo, `apps/game` with shadcn, empty screens
- `packages/sim` identity function + Zod event stub
- `packages/content` empty catalogs
- `packages/pipeline` CLI stub
- Supabase project + placeholder tables
- Tauri shell launching the SPA

## 3. Vertical slice (engineering)

- One placeholder card kind, code frame, fake portrait
- Shop verbs as UI only (numbers TBD or temporary)
- Two canned loadouts → server sim → replay playback of cards
- No real meta, no real art pipeline required

## 4. Pipeline

- Comfy workflow + one style/race preset after races exist
- ElevenLabs locked SFX list after tags exist

## 5. Content and systems

- Collection, synergies, items, heroes as designed
- Snapshot matchmaking + ladder/seasons if designed

## 6. Steam

- Steamworks auth, depot, overlay QA, store page, AI disclosure

## 7. Launch bar

- TBD against [success criteria](../product/success-criteria.md)
