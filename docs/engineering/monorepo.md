# Monorepo

Status: Default

Package manager: **pnpm**. Layout as decided:

```text
apps/game          Vite + React SPA (the game)
apps/desktop       Tauri 2 shell
packages/sim       deterministic combat
packages/content   card/hero/item data + Zod schemas
packages/pipeline  asset generation CLI / scripts
docs/              this documentation
```

## Rules

- Game code does not import pipeline (generation is offline / CI).
- `apps/game` and the server both import `packages/sim` and `packages/content`.
- No game logic living only in React components.

## Tooling (defaults from stack; versions TBD at scaffold)

- TypeScript
- Vite
- Tailwind v4
- shadcn
- ESLint / Prettier or the current shadcn default — TBD at scaffold
- CI: TBD (old Bevy GitHub Actions were removed)

## Scaffold status

Not created. v0 is docs-only besides README and gitignore.
