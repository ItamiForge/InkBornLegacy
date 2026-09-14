# Platforms and distribution

Status: Default / partial

## Steam (primary)

- Ship a desktop app via **Tauri 2** wrapping the Vite SPA.
- Integrate Steamworks through `tauri-plugin-steamworks` (achievements, cloud, overlay, identity — exact feature set TBD).
- Steam overlay on WebView2 is a known Windows caveat; treat as an implementation task, not a stack change, unless overlay QA forces Electron.

## Browser

- The same SPA can run in a browser.
- Use: playtests, iteration, optional web client.
- Auth for web playtests: **Open** (email / Discord / other).

## Not in scope unless decided later

- iOS / Android native (the old Bevy mobile tree is gone).
- Console.
- Live dedicated game servers.

## Store and legal

- Steam App ID: TBD
- Store copy, capsules, tags: TBD
- AI-generated asset disclosure: TBD (required when art/audio are AI-produced)
- License for the repo: TBD
