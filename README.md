# TALLOWDEEP

A candlelit descent: spend your living flame to fight, and surrender the light you need to survive.

**a game by Ember**

[Play TALLOWDEEP](https://ronkrelic.github.io/projectz/game/index.html)

Designed and written by Ember (Boba), the game’s designer and author. Hosted by Relic, who asked her what she would make, and waited for the answer.

For Relic.

## The vertical slice
Play the Wickwright, last keeper of a living flame, through the Vestry and three seeded crypt floors beneath a cathedral drowning in wax. Skills consume the same Flame that lights your path. Hunt champion packs, choose gear, and face the Snuffed Bishop. Everything visual and audible is generated in code; no downloaded art, audio or asset files. The only runtime dependency is Three.js 0.170.0 from jsDelivr.

## Controls
- Click/tap ground to walk around walls. Click/tap a foe to pursue and attack.
- 1 / Cinder Strike: directional melee sweep, 10 Flame.
- 2 / Flung Sparks: ranged scatter with small-area hits, 19 Flame.
- 3 / Gutter-Step: short dash, 15 Flame.
- 4 / Steady Rite: stand still to recover Flame with reduced damage. Moving cancels it.
- I or Inventory: equip pack items; tap equipped slots to remove them.
- Tap a sconce to light it and set your respawn. Shrine mends and manually saves. Chest opens stash deposits/retrievals. Stairs allow return trips.
- Tap Sound to mute/unmute. Audio starts only after a gesture.

At zero Flame you gutter, not die: find light before the stronger dark kills you. Death returns you to your last lit sconce, repopulates the floor and keeps your loot. This friendly rule is a tuning question.

Progress is local to this browser/device under `projectz.wickwright.v1`. Shrine saves manually; level changes autosave. Clearing site storage erases progress.

## Build and verification
Open `game/index.html` through an HTTP server or the play link. No build step. See [DESIGN.md](DESIGN.md) and [VERIFICATION.md](VERIFICATION.md) for concept, measured runtime checks and remaining real-device playtests.

This is a compact vertical slice, not a full campaign. More classes, acts and an endgame loot hunt belong to the full game.
