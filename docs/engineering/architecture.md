# Technical architecture

Status: Default

## Summary

One TypeScript monorepo. A Vite SPA is the game. Tauri wraps it for Steam. Combat is a pure function. Supabase holds accounts, snapshots, and replays. No realtime match server.

```text
                    ┌──────────────┐
                    │  Steam / OS  │
                    │  Tauri 2     │
                    └──────┬───────┘
                           │ webview
┌─────────────┐     ┌──────▼───────┐     ┌─────────────────┐
│ Browser     │────▶│ apps/game    │────▶│ packages/sim    │
│ (playtest)  │     │ React SPA    │     │ (optional local │
└─────────────┘     └──────┬───────┘     │  preview)       │
                           │             └────────┬────────┘
                           │ HTTPS                │ same fn
                    ┌──────▼───────┐     ┌────────▼────────┐
                    │  Supabase    │────▶│  sim (server)   │
                    │  Auth        │     │  same package   │
                    │  Postgres    │     └─────────────────┘
                    │  Storage     │
                    └──────────────┘

packages/content   card JSON + Zod
packages/pipeline  ComfyUI / Fal / audio APIs → portraits & SFX
```

## Trust boundary

- Shop and collection UI: client.
- Ranked outcome: server runs `sim(boardA, boardB, seed)` and writes the replay.
- Clients may run sim for sandbox / animation preview; they must not submit their own winner.

## Runtime

- No Colyseus, no websocket tick, no dedicated simulation host in v1.
- A match is request/response: enqueue or accept match → server sim → read replay.
- Optional Realtime (Supabase) only if a live “replay ready” ping is wanted later. Not required.

## Scale path (not v1)

- Move `sim` invocation to a Cloudflare Worker if CPU on Supabase becomes the bottleneck.
- Serve portraits and audio from R2/CDN.

## Shared types

Zod schemas in `packages/content` and `packages/sim` are the contract: cards, boards, events, match results.

## Auth

- Steam build: Steam session ticket validated on the backend (exact Supabase hook TBD).
- Web: TBD (see open questions).
