# Client

Status: Default

## App: `apps/game`

- Vite + React + TypeScript
- Tailwind v4 + shadcn
- Zustand + TanStack Query
- Motion for card motion
- Canvas or Pixi **only** for combat VFX
- Howler or native audio for the SFX/ambient palette

## Desktop: `apps/desktop`

- Tauri 2 loads the game SPA
- Steamworks via `tauri-plugin-steamworks`

## Rendering rules

- Cards are DOM/SVG (frame + text) plus an `<img>` (or equivalent) for the portrait.
- Combat is not a second game engine. It is the card UI driven by the event log.

## Routing / screens

Stub. Implement after [player experience](../product/player-experience.md) is filled.

## Config

- API URL, Supabase keys, Steam app id: env files. No secrets in git.
