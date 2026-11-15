# Checkpoint

Read this first when resuming work on this repo.

```
=== CHECKPOINT ===
project: rampart-versus-remake
timestamp: 2026-11-15 20:51 UTC
Intent: Design a fresh, modern take on Rampart (likely three.js) that keeps the 2D original's simplicity. Still in brainstorming. Nothing is built.
Decisions made: Start fresh; existing rampartversus.html is reference only. Core = (1) tension of rebuilding walls before the timer ends, (2) strategy of choosing which enemy walls to destroy. Versus, couch play on one shared screen for starters (online or AI may come later). Proposed by Claude, not yet confirmed: browser on PC-to-TV, two gamepads plus keyboard fallback, mostly top-down camera for readability, rules kept separate from visuals and input so online or AI can be added later.
Current step: Brainstorming. Last question asked was about the "modern spin": which games' look or feel to borrow, and which to avoid. It is unanswered.
Open questions: Visual and feel references (unanswered). Whether the proposed platform, controls and camera are right (unconfirmed). Possible bug in old file: unenclosed cannons keep firing until the end of BUILD (activeCannons never checks enclosure); unverified whether intentional. No design doc written yet.
Next action: Answer the "modern spin" question (games to borrow from or avoid), then confirm or correct the proposed platform, controls and camera.
=== END CHECKPOINT ===
```

Background research and the comparison with the old file: see `docs/rampart-research.md`.
