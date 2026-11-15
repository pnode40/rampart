# Rampart research notes

Collected 2026-11-15. Sources are listed at the end. Most rules detail comes from one fan-written strategy series (Arcade Mermaid, Set Side B), whose author says much of it is "self-discovered." Treat numbers as one player's findings, not official specs. The series mostly covers single-player.

## Basics
- 1990 arcade strategy game by Atari Games; Namco distributed in Japan. Designers John Salwitz and Dave Ralston. Trackball control.
- Release date conflicts: Wikipedia says limited US release October 1990, wide release February 1991; one database says 31 December 1990; Arcade Mermaid says 1989.
- Often called a precursor to tower defense.

## Core loop
- After picking a home castle (the game auto-walls it) and placing starting cannons, each round repeats Battle, Building, Cannon.
- Lose: fail to enclose at least one castle by the end of Building.
- Single-player: six levels against ships. Multiplayer: players shoot each other's walls across rivers; ends when others are out, or after a set number of battles (highest score wins). A "Final Battle" ends continues.
- Players can only join at the lobby screen, not mid-game.
- Semi-secret mode: two players, one rejoining after a finished game, unlocks a map with both players and color-coded ships that act like extra cannons.

## Battle
- Crosshair aim; each cannon has at most one shot in the air. Distant shots arc higher and take longer, so close targets mean more shots.
- Cannons fire in the order they were placed.
- Ships move in straight lines in 8 directions, stop at shore or other ships. Max 16 ships on screen.
- Level clears after most ships are sunk (exact rule unknown).

## Ships (single-player)
| Type | Hits | Notes |
|---|---|---|
| Gunship | 2 | From level 1 |
| Lander | 3 | Drops grunts on diagonal shorelines |
| Red Ship | 5 | From level 3; shots leave craters |
| Dark versions (levels 4-6) | 3 / 4 / 6 | One extra hit each |

- Grunts move and multiply during Building, block pieces, and can destroy castles in the next Battle (the only thing that can). Walling them in kills them.
- Craters block placement and fade over three rounds (two if you recently continued).

## Building
- Pieces arrive one at a time; place one to get the next. Shapes range from 1x1 to large plus and U shapes, getting larger and more complex over time.
- Rotate is clockwise. A piece can't overlap wall, shore, castle, cannon, crater, grunt or the screen edge.
- Enclosing a castle with a continuous wall captures it and anything inside.

## Cannons
- Cannon phase: 10 seconds. Cannons are 2x2.
- Start of game: 3 cannons (4 after a continue, 2 at the start of later levels). Each later phase: 2 for the home castle, 1 per other enclosed castle, only if there's room.
- Cannons can't be removed except by losing. Unowned (unenclosed) cannons sit idle during Battle.
- Five illegal placements in a row end the Cannon phase early.
- Wikipedia: losing an enclosure after combat also loses the cannons inside it.

## Levels (single-player)
- Recruit always starts on the "J" map; Veteran adds 5,000 points. Four starting maps; author's ease order: Hat, J, C, Lowercase N.
- Level 5: two peninsula maps ("slash" and "backslash") with Red Ship limits removed.
- Level 6: one island with a lake and two castles, attacked from both sides.
- Four continues allowed in single-player; continuing changes cannon strength and crater timing.

## Ports (from search snippets, not full reads)
- Many home ports. NES (North America) by Bitmasters for Jaleco; separate Konami Famicom version with seven training levels, three difficulties and an extensive two-player mode (fan translation May 2017). SNES and DOS let cannons convert into powerups; SNES drops three-player mode. Master System lacks the countdown timer.
- Not confirmed: Game Boy version details; co-publisher mentions (Midway, Domark).

## Comparison with rampartversus.html (old prototype)
Matches: Cannon then Battle then Build cycle; home castle pick with auto wall ring; 2 cannons for home plus 1 per other castle; 2x2 cannons; one shot in the air per cannon; placement-order firing; distance-based flight time; lose on zero enclosed castles; score tiebreak at cycle limit; castles immune to shots; 10 s cannon phase; river-split maps.

Differences:
- Possible bug: unenclosed cannons keep firing in COMBAT and persist through BUILD; `activeCannons` only checks `c.active`, and removal happens in `evalRoundEnd`.
- Piece weights are fixed (no progression); no U shape.
- Walls and cannons die in one hit.
- First cannon phase gives 2, not 3 (multiplayer starting count not documented).

Missing: ships, grunts, craters, levels, continues, composite mode, Final Battle, three-player, bonus squares, five-illegal-placements rule.

Added: hold slot, two-piece preview, CCW rotation, best-of-N, timer presets, 12-cannon cap, scoring numbers, three powerups (balloon, mega piece, super cannon) costing 3 cannons, gamepad remapping, color-blind palette.

## Not read
Hardcore Gaming 101 (site under maintenance), Destructoid and The Cutting Room Floor (Cloudflare block), Sega Retro comparison page (blocked).

## Sources
- https://en.wikipedia.org/wiki/Rampart_(video_game)
- https://setsideb.com/rampart-part-1-introduction/
- https://setsideb.com/?p=8131 (Part 2)
- https://setsideb.com/?p=8150 (Part 3)
- https://setsideb.com/?p=8167 (Part 4)
- https://arcade-museum.com/Videogame/rampart
- https://www.nintendolife.com/news/2017/05/famicom_version_of_rampart_translated_to_english
