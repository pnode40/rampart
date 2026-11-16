# Checkpoint

Read this first when resuming work on this repo.

```
=== CHECKPOINT ===
project: rampart-versus-remake
timestamp: 2026-11-16 UTC
Intent: Design a fresh, modern take on Rampart (three.js, in the browser) that keeps the 2D original's simplicity. Still in brainstorming. The real game is not built.
Decisions made: Start fresh; rampartversus.html is reference only. Core = (1) tension of rebuilding walls before the timer ends, (2) strategy of choosing which enemy walls to destroy. Versus, two players at one shared screen. Screen is a PC monitor, not a TV. Rebuilding stays piece-based (block-by-block rebuilding was considered and dropped: it removes the awkward-shape pressure). Blocky 3D look is the leading direction, using our own style (no Minecraft name, textures or characters). Roblox was considered out of curiosity and set aside; browser stays the platform. Proposed by Claude, not yet confirmed: two gamepads plus keyboard fallback, angled top-down camera, rules kept separate from visuals and input.
Current step: Owner is reviewing a throwaway look test, demos/block-siege-test.html (published as a private link: https://claude.ai/artifact/JVHv6PY4cftLs3XEGaqoJJ). It shows blocky walls, cannonballs breaking wall blocks into rubble, and a piece dropping in to patch a gap. Its code does not carry over to the game.
Open questions: Does the blocky look feel right (owner's reaction to the demo)? Who is the game for: people the owner knows, or strangers? (Decides how much new gameplay is needed beyond the look.) Power-ups: how players earn them, and what they do (must add a choice, not just strength). Platform, controls and camera still unconfirmed. Possible bug in old file: unenclosed cannons keep firing until the end of BUILD; unverified whether intentional. No design doc written yet.
Next action: Owner opens the demo link and says what feels right or wrong about the look and the explosions.
=== END CHECKPOINT ===
```

Background research and the comparison with the old file: see `docs/rampart-research.md`.
