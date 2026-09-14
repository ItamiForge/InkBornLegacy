# Vision

Status: Locked (product); Stub (fiction)

## What this is

An async PvP auto-battler sold on Steam.

Players build a team through a shop loop in the same family as Hearthstone Battlegrounds (buy, sell, roll, freeze, upgrade). Content, collection, synergies, and items are in the same family as Pokémon Auto Chess, and should be wider and richer than those games in that regard.

Most objects the player owns or plays are **cards**. The chrome is a polished website UI (shadcn), not a 3D tavern and not a sprite board.

Fights are **not** live 8-player lobbies. A player fights a **snapshot** of another player’s board. Combat is simulated deterministically and watched as a replay. This matches the async pacing discussed around Oaken Tower and Batomon Showdown, while keeping Battlegrounds/PAC mechanical DNA.

## Why async

- Product: play at your own pace; no lobby timer required for the primary mode.
- Production: no tick servers, no Colyseus rooms, low server load.

## What this is not

- Not a live 8-player Battlegrounds clone.
- Not a Pokémon product (reference only).
- Not a Bevy/Unity/Godot action game.
- Not a Phaser sprite-board auto chess.

## Name, pitch, fantasy

**Name:** InkBorn Legacy. Fantasy and lore: [WORKING.md](../WORKING.md).
