# Decisions log

Status: Locked  
Source: project discussion (stack and product), 2026-09-14

Only items that were discussed and accepted. No additions.

## Product

1. The game is an auto-battler in the lineage of Hearthstone Battlegrounds and Pokémon Auto Chess.
2. Mechanics are similar to those games, but the game is **async**.
3. Content should be **wider and richer**, more like Pokémon Auto Chess in that regard.
4. Matches are snapshot PvP: fight another player’s saved board, not a live 8-player lobby.
5. Async is also a production choice: reduce server-side load.
6. Ideal distribution: Steam.
7. Presentation: JavaScript / shadcn-style polished website look.
8. Most objects are cards.
9. High-quality AI art cards, with portraits generated under controlled workflows.
10. Reference games discussed: Pokémon Auto Chess (browser, GitHub), Oaken Tower, Hearthstone Battlegrounds, Batomon Showdown.

## Stack

11. Game client: Vite + React + TypeScript + Tailwind v4 + shadcn.
12. Motion: Motion (Framer) + a small Canvas/Pixi layer for VFX only.
13. Card frames: SVG/HTML templates in code. Stats, rarity, race, type, and typography are layout, not part of the generated image.
14. Client state: Zustand + TanStack Query.
15. Schemas: Zod.
16. Combat: shared TypeScript package `packages/sim`. Deterministic. Integer math. No wall-clock. Input is two boards + seed. Output is an event log. Client plays the log. Server runs the same function.
17. Backend: Supabase (Auth, Postgres, Storage, optional Realtime).
18. Later scale option: combat sim on a Cloudflare Worker; assets on R2. Not required to start.
19. Desktop: Tauri 2 wrapping the Vite app.
20. Steam: `tauri-plugin-steamworks`.
21. Same SPA runs in the browser and in the Steam wrapper. Next.js is not the game client.
22. Monorepo (pnpm): `apps/game`, `apps/desktop`, `packages/sim`, `packages/content`, `packages/pipeline`.

## Explicitly rejected

23. Not Bevy, Unity, Godot, Phaser, or Colyseus.
24. Not Next.js as the game.
25. Not live 8-player rooms as the primary match type.
26. The previous Bevy template in this repo is removed (v0 fresh start).

## Assets

27. Never generate a finished card as one image. Generate a portrait only; composite onto the frame in code.
28. Art orchestration: ComfyUI workflows checked into git, called by a TypeScript pipeline.
29. Model default: FLUX.2 Klein 9B (or current FLUX.2) + consistency LoRA + per-race LoRA.
30. Identity: approved reference per race/type, then reference-image conditioning. Not a new random prompt per card.
31. Pose lock: ControlNet or a fixed bust-portrait template so units share a camera/crop.
32. Batch generation: Fal or RunComfy, same workflow JSON.
33. Do not train a LoRA per unit. Train one style LoRA for the game and one LoRA per race.
34. Do not AI-video every unit.
35. Combat animation: the card moves; shared VFX are tagged by damage type, not unique per card.
36. Audio is a palette mapped by type tags, not a unique sound per card.
37. Raw SFX: ElevenLabs SFX v2 API from a locked list.
38. Synth ambients: Stable Audio 2.5 and/or Tone.js.

## Match flow (architecture default)

39. Player submits / saves a loadout.
40. Matchmaking picks a snapshot from other players (nearby MMR, recent window — exact rules TBD).
41. Server runs `packages/sim` and stores the replay.
42. Client requests the replay and animates the event log.
43. No dedicated tick server.
