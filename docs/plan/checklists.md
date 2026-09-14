# Checklists

Status: Plan

Check items off as they are done. Do not mark design items done by inventing answers.

---

## A. Documentation (M0)

- [x] Remove Bevy template
- [x] v0 README (goal + stack)
- [x] Decisions log
- [x] Open questions
- [x] Product docs
- [x] Design docs (stubs where needed)
- [x] Technical architecture
- [x] Asset pipeline docs
- [x] Roadmap, milestones, this checklist

---

## B. Design discussion (M1) — blocked on conversation

- [x] Game name — InkBorn Legacy
- [x] Lore — accumulating in `docs/WORKING.md` (tone, motive, ink aesthetic, catalog split, synergy axes)
- [ ] Races list — draft codex in WORKING.md, not locked
- [ ] Types list — axes locked; field/class lists TBD
- [ ] Card kinds and catalog scope for v1
- [ ] Synergy rules — axes locked (race, class, emotion-or-raw, element); thresholds TBD
- [ ] Heroes
- [ ] Items
- [ ] Shop/economy rules and numbers
- [ ] Combat rules
- [ ] Snapshot matchmaking rules
- [ ] Modes (ranked/casual/sandbox/etc.)
- [ ] Collection / progression
- [ ] UI wireframes / card anatomy
- [ ] Audio tag list and bed list
- [ ] Success criteria filled

---

## C. Scaffold (M2)

- [ ] pnpm workspace
- [ ] `apps/game` Vite + React + TS + Tailwind v4 + shadcn
- [ ] Motion installed
- [ ] Zustand + TanStack Query
- [ ] Zod
- [ ] `apps/desktop` Tauri 2 shell
- [ ] `packages/sim` package stub
- [ ] `packages/content` package stub
- [ ] `packages/pipeline` package stub
- [ ] Env examples (no secrets)
- [ ] CI TBD

---

## D. Backend (M2–M3)

- [ ] Supabase project
- [ ] `profiles` `loadouts` `replays` `ladder` `seasons` (columns per data-model decision)
- [ ] RLS
- [ ] Function host for `sim`
- [ ] Steam ticket validation (when App ID exists)
- [ ] Web auth (if any)

---

## E. Vertical slice (M3)

- [ ] Placeholder card frame (SVG/HTML)
- [ ] Placeholder portrait slot
- [ ] Two loadouts in data
- [ ] `sim` returns a typed event log
- [ ] Client plays log as card motion
- [ ] Server writes replay; client reads it
- [ ] No live lobby

---

## F. Asset pipeline (M4) — after races/types exist

- [ ] Style preset file
- [ ] Race preset files
- [ ] Prompt template
- [ ] ComfyUI workflow in git
- [ ] Compiler: content → prompt → job
- [ ] Fal or RunComfy (or local) runner
- [ ] Fixed crop / pose
- [ ] Composite onto frame
- [ ] Id-based filenames
- [ ] Review step
- [ ] ElevenLabs SFX list generated
- [ ] Ambient beds (Stable Audio and/or Tone.js)

---

## G. Game systems (M5) — after design fill-in

- [ ] Shop verbs wired to economy rules
- [ ] Combat rules in sim
- [ ] Synergies
- [ ] Items
- [ ] Heroes
- [ ] Collection
- [ ] Snapshot matchmaking
- [ ] Ladder / seasons if in design

---

## H. Steam (M6)

- [ ] App ID
- [ ] Tauri + steamworks init
- [ ] Overlay QA (Windows)
- [ ] Achievements (if any)
- [ ] Cloud (if any)
- [ ] Depot upload
- [ ] Store page
- [ ] AI disclosure
- [ ] Capsules / trailer (art TBD)

---

## I. Explicitly not doing

- [x] Bevy / Unity / Godot client
- [x] Phaser board
- [x] Colyseus live rooms
- [x] Next.js as the game
- [x] Generate finished cards as single AI images
- [x] Per-unit LoRAs
- [x] Per-unit AI video
- [x] Per-card unique SFX
