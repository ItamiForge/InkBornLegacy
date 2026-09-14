# [GAME_NAME]

Working title: **TBD**. This repository is a clean slate (v0).

Async PvP auto-battler for Steam. Shop, buy, roll, freeze, and upgrade like Hearthstone Battlegrounds. Collection, synergies, items, and content depth like Pokémon Auto Chess, intended to be wider and richer. Most objects are cards. Matches are snapshot PvP (fight another player’s saved board), not a live 8-player lobby.

## Status

v0 — fresh start. No game code yet. The previous Bevy template was removed.

## Locked product decisions

- Publish on Steam (desktop wrapper around the same web app).
- Async features on purpose, to keep server load low.
- Presentation: JavaScript / shadcn-style polished website look.
- Primary objects: cards. High-quality AI art **portraits** composited onto code-defined card frames (never generate a finished card as one image).
- Asset production: fully controlled custom workflows from standard templates/presets so races and card types stay visually consistent.
- Original discussion references: Battlegrounds, Pokémon Auto Chess, Oaken Tower, Batomon Showdown.

## Locked stack

If this repo is implemented end-to-end as discussed:

| Layer | Choice |
| --- | --- |
| Game client | Vite + React + TypeScript + Tailwind v4 + shadcn |
| Motion | Motion (Framer) + a small Canvas/Pixi layer for VFX only |
| Card frames | SVG/HTML templates in code |
| Client state | Zustand + TanStack Query |
| Schemas | Zod |
| Combat | Shared TypeScript package `packages/sim` — deterministic, integer math, event log |
| Backend | Supabase (Auth, Postgres, Storage). Optional later: Cloudflare Worker for sim, R2 for assets |
| Desktop / Steam | Tauri 2 + `tauri-plugin-steamworks` |
| Art pipeline | ComfyUI workflows in git + FLUX.2 (Klein 9B or current FLUX.2) + consistency / per-race LoRAs; batch via Fal or RunComfy |
| Audio | ElevenLabs SFX v2 for raw one-shots; Stable Audio 2.5 and/or Tone.js for synth ambient beds |
| Repo | pnpm monorepo: `apps/game`, `apps/desktop`, `packages/sim`, `packages/content`, `packages/pipeline` |

Explicitly not using: Bevy, Unity, Godot, Phaser, Colyseus, Next.js as the game client.

## Docs

Start at [docs/README.md](docs/README.md). Locked decisions, open questions, product, design stubs, architecture, asset pipeline, and build checklists live there.

## Not decided (do not invent here)

Game name, lore, races, types, synergies, economy numbers, modes beyond snapshot PvP, UI layout details, license, and all other design specifics. Tracked in [docs/02-open-questions.md](docs/02-open-questions.md).

## License

TBD.
