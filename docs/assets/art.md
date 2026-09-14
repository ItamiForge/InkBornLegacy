# Art

Status: Default (method); Stub (style)

## Locked method

```text
portrait PNG  (AI, same crop, same light)
    +
frame SVG     (rarity / race / type — code)
    +
typography    (name, stats, text — code)
    =
card
```

- Model: FLUX.2 Klein 9B or current FLUX.2
- Consistency LoRA + **per-race** LoRA
- One **style** LoRA for the whole game
- No LoRA per unit
- Reference sheet per race/type; reference-image conditioning
- Pose/crop locked (ControlNet or fixed bust template)
- Workflows in git; TypeScript compiler from content → prompt

## Stub — look

Art direction, medium, era, faces vs creatures: TBD (lore/design discussion).

## Counts

No target count decided.
