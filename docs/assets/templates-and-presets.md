# Templates and presets

Status: Default (system); Stub (contents)

This is the consistency control. Cards do not own raw prompts. Presets do.

## Layers

1. **Style preset** (game-wide) — style LoRA, shared negative, shared camera
2. **Race preset** — palette, motifs, race LoRA, reference sheet
3. **Type preset** — additional motifs if types exist
4. **Card record** — id and prompt **slots only** (role, adjectives TBD by design)

## Compiler

`packages/pipeline` fills a locked prompt template. Changing a race preset regenerates that race; changing one card does not rewrite the race look.

## Stub — files

```text
presets/style.yaml      TBD
presets/races/*.yaml    none
presets/types/*.yaml    none
templates/portrait.json Comfy workflow — not authored yet
templates/prompt.txt    TBD
```

No presets until [races](../design/races.md) and [types](../design/types.md) are decided.
