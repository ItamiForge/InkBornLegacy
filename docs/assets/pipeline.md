# Asset pipeline

Status: Default

Offline (or CI) generation. Runtime game only **reads** finished files referenced by content ids.

```text
packages/content (card JSON, prompt slots)
        │
        ▼
packages/pipeline
        │  fills locked prompt templates from race/type presets
        ▼
ComfyUI workflow JSON (git) ──▶ Fal / RunComfy / local Comfy
        │
        ▼
portrait PNG (fixed size/crop)
        │
        ▼
sharp composite onto SVG frame (optional bake for export; game may composite live)
        │
        ▼
named by card id → Storage or repo assets
```

Audio is a separate path in the same package: locked SFX list → ElevenLabs; ambient beds → Stable Audio and/or Tone.js (runtime generative pads vs baked files: TBD).

## Review

Reject crop/identity failures before a portrait is attached to a card id. Human or vision check: TBD which.

## Runtime

Game never calls ComfyUI, Fal, or ElevenLabs in a player match.
