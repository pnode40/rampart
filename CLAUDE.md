# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Working with the owner

- The owner is non-technical and works on a Windows PC in PowerShell (Windows PowerShell 5.1). The local clone is at `C:\Users\epatn\rampart`.
- Explain things in plain language and say what each command does before asking them to run it.
- Give commands in PowerShell syntax, not bash. Example: `$env:USERPROFILE`, not `~`.
- End each session by updating `docs/checkpoint.md`, then committing and pushing, so nothing exists only on the laptop.

## Start here

Read `docs/checkpoint.md` first. It records the current intent, decisions made, the open question and the next action. `docs/rampart-research.md` holds rules research on the 1990 arcade game and a comparison with the existing prototype.

Current state (see the checkpoint for the latest): brainstorming a fresh, modern versus game in the Rampart style, probably with three.js. Nothing new is built yet. `rampartversus.html` is reference only and is not the base for the new version.

## Running the prototype

There is no build step, package manager, linter or test suite. `rampartversus.html` is one self-contained file (HTML, CSS and JavaScript inline, no external libraries). To run it, open it in a browser:

```powershell
start rampartversus.html
```

## Prototype architecture (`rampartversus.html`)

One `<script>` block split into sections marked by `/* ===== NAME ===== */` banner comments. Search for the banner to find a section.

- **State:** a single global `G` built by `freshG()`. `G.screen` selects the active screen (title, join, menus, game). `G.round.phase` drives play: `CASTLESELECT` then a repeating `ARM` (place cannons), `COMBAT`, `BUILD` cycle. `enterPhase()` in the PHASES MODULE handles transitions. Phase lengths are `PHASE_BASE_MS` scaled by `G.settings.timerPreset`.
- **Board:** a 48x30 grid of 20px tiles. Tile types are the constants `LAND, WATER, ROCK, WALL, CASTLE, CANNON`. Maps in `MAPS` define water, rocks, each player's column range and castle positions.
- **Enclosure:** `computeEnclosure()` flood-fills from the board edges through non-solid tiles. Anything the fill cannot reach is enclosed. It sets `c.enclosedBy` on castles, and `cannonEnclosed()` reuses `board.outside`. The code labels it "fragile algorithm #1"; scoring, cannon allotment and the loss condition all depend on it.
- **Loop:** fixed 60 Hz update with an accumulator in `frame()`, separate from rendering. Rendering draws to a 960x664 canvas plus an offscreen `glowCanvas` that is blurred and composited for bloom.
- **Input:** two players on gamepads (remappable per player) with a keyboard fallback. Input handling is split between the INPUT MODULE and INPUT HANDLING PER SCREEN.
- **Audio:** generated with Web Audio (`AUDIO`), with no sound files.

Known issue, unverified as intentional: cannons that are not enclosed keep firing during `COMBAT` and survive through `BUILD`, because `activeCannons` only checks `c.active` and removal happens in `evalRoundEnd`.
