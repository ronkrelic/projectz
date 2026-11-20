# TALLOWDEEP — vertical-slice verification

Checked 19 November 2026 (America/New_York), against game commit `ec8b9b73880459d32c2d8a13e2c058dc16f63107`, served by GitHub Pages. These are automated browser runtime assertions, not claims of human play quality.

## Passed headlessly
- Module executed, simulated steps advanced, WebGL2 context created (1920×831 drawing buffer in the desktop test). Instrumented drawElements exceeded 51,000 calls across the observation window. In the final controlled hub runtime window: zero captured error events, unhandled rejections or console.error calls.
- A synthetic wall blocked the direct route from (4,4) to (12,4); BFS routed via z=10, every waypoint walkable, and 250 simulated 0.05s steps reached the destination.
- Each of three seeded floors generated seven mutually reachable room centers, with 18/18/19 enemies and two champions per floor; floor three had one Bishop.
- Cinder Strike: 10 Flame, 0.7s cooldown, 19.2 damage in the test. Flung Sparks: 19 Flame, 2.8s cooldown, three projectiles; direct and nearby AoE targets damaged. Gutter-Step: 15 Flame, 3.4s cooldown, 3.3-unit open-ground dash. Steady Rite: no cost, 8s cooldown, 4s channel; a 10-damage hit reduced to 3.5. Moving canceled Rite. Cooldown reuse rejected and countdown advanced.
- Gnawer entered chase, closed distance and attacked. Hollow received 4.5 versus 10 damage in darkness/light. Smoldering created a patch dealing 0.7 damage over 0.1s. Swollen death burst dealt 20.
- Floor-one dark net Flame drain: 4 over 10s. Zero Flame guttered without killing. Lit sconce restored 12.4 in 1s; Rite restored 10.4 in 1s.
- Generated 100 items each of common, magic and rare: correct tiers and finite positive rolled stats under 55. Equipping a rare changed computed stats. Inventory/stash deposit and retrieve controls worked.
- Bishop displayed slam then sweep telegraphs; slam dealt 26 after its delay. Half-health phase change produced adds (four: three on phase change and one periodic). Death produced one unique and a homeward flame. The Bishop’s Last Match equipped at radius 11; floor-three dark net burn was 3.2 Flame/s including its 2.5/s tradeoff.
- Death returned to the selected last sconce, restored the enemy population and retained inventory. Save/load roundtrip restored level, health, inventory, computed stats and last sconce using projectz.wickwright.v1. Shrine fully mended Blood/Flame; down and up stairs returned between Vestry and crypt.
- Actual game in a same-origin 390×844 iframe viewport: no document overflow; all five bottom buttons inside viewport, 52px high; pack panel had no horizontal overflow; canvas 585×1266 (DPR 1.5). Synthetic touch pointer routed movement around tiles, selected an enemy, fired Sparks through its button and opened inventory. This is phone-sized layout/input verification, not a real mobile-device test.
- AudioContext observed running after an actual browser gesture. The sound synthesis graph and rarity-scaled chord scheduling executed. No assertion about how satisfying the result sounds.

## Limits and corrections
An early editor workflow appended documents rather than replacing them. A dedicated repair commit restored one exact complete HTML/module; source equality was checked afterward. A malformed test-only fake sconce caused errors during an early harness attempt; real props were restored, then the final controlled runtime/error window was clean. Negative automation clock deltas were clamped to zero.

Browser screenshots came back black (and an iframe preview white), despite DOM geometry, gameplay state and WebGL draw calls advancing. Therefore painted appearance/pixel output is not independently certified here. Real GPU output, iOS audio unlock/resume, audible mix and actual phone framerate require a device playtest. No automated test establishes boss fairness, combat feel or frame stability.

## Relic’s playtest
1. Does click/tap routing feel obedient near corners, stairs and crowded enemies?
2. Do hits have weight without feeling sluggish? Is dash distance right?
3. Is spending sight for damage tense or merely inconvenient? Try guttering deliberately.
4. Does the rare pickup chime make you want another drop? Compare tiers with headphones.
5. Can you read and evade both Bishop tells? Does phase two feel earned rather than unfair?
6. On a phone: check HUD readability, thumb targets, framerate, heat, audio after app switching and resume.

## Open design questions — Ember
Is keeping all loot on death too kind, or exactly what invites another descent? Should the unique lantern burn harder for its enormous view? Do you want scarce safe light or more frequent little islands of relief? Inventory currently leaves the world running: does that pressure serve the game? I would tune these from your gut before adding more content.

For Relic. Tell me which moment made you lean closer.
