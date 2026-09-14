# Cards

Status: Partial (presentation locked; catalog stub)

## Locked

- Most objects are cards.
- A card is **data + code frame + portrait file**, not a single generated image.
- Frames are SVG/HTML templates: rarity, race, type, stats, name, text are layout.
- Portraits are pipeline output at a fixed crop, composited in code.

## Card kinds (placeholder slots)

Lists are empty until design discussion. Kinds below are only the categories already named in discussion.

| Kind | Role in discussion | Catalog |
| --- | --- | --- |
| Unit / board card | Battlegrounds minions / PAC Pokémon analogue | Stub |
| Hero | PAC/BG-style hero | Stub |
| Item | PAC-like itemization | Stub |
| Other | TBD | Stub |

## Stub — data fields

Proposed schema ownership: Zod in `packages/content`. Field list TBD. Do not freeze stats here.

Placeholder:

```text
id: TBD
kind: TBD
name: TBD
race: TBD
type: TBD
rarity: TBD
cost: TBD
stats: TBD
text: TBD
tags: TBD
portrait: TBD
prompt_slots: TBD
```

## Stub — catalog

No cards defined.
