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

**Locked:** sumi-ink for portraits and main game components (flowing splashes, sprays, calligraphy). One game-wide style LoRA in that language. Per-race LoRAs still apply. Card **frames** styled by race/type in code.

Counts, exact palettes: TBD.
