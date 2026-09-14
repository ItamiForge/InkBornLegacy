# Steam

Status: Default / partial

## Ship form

Tauri 2 app wrapping `apps/game`.

## Plugin

`tauri-plugin-steamworks` for achievements, cloud saves, overlay, identity. Which of those ship in v1: TBD.

## Overlay

WebView2 overlay is a known issue. Implementation task: follow the plugin’s overlay-surface path on Windows. Not a reason to change stack unless it fails QA.

## Partner tasks (not code)

- [ ] Steamworks partner account
- [ ] App ID
- [ ] Depot / build upload
- [ ] Store page
- [ ] AI asset disclosure
- [ ] Achievements list (depends on design)

## Web vs Steam

Same SPA. Steam ticket auth on desktop. Web auth TBD.
