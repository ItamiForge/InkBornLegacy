# Backend

Status: Default

## v1: Supabase

| Concern | Service |
| --- | --- |
| Accounts | Auth |
| Loadouts, replays, ladder, seasons | Postgres |
| Portraits / built card assets if hosted | Storage |
| Live notify (optional) | Realtime |

## Responsibilities

- Validate Steam (or web) identity
- Store and serve loadout snapshots
- Select an opponent snapshot (SQL; rules TBD)
- Run `sim` (Edge Function or other hosted TS — exact host TBD, same package)
- Persist replay + result
- Serve collection/content if not shipped entirely in the client bundle (choice TBD)

## Not in v1

- Dedicated game server
- Colyseus rooms
- Authoritative tick loop

## Later

- Cloudflare Worker for `sim`
- R2 for heavy assets
