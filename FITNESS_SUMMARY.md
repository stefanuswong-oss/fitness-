# Fitness Summary — Stefanus Wong
**Last updated:** 2026-07-24

---

## Current Status

- Phase 3, Week 4 (self-designed program). Logged sessions through 2026-07-23 are baked into the tracker's embedded history (no longer only in browser localStorage). Added 2026-07-22 (Legs Strength) and 2026-07-23 (Push Hypertrophy) from a manual JSON export — Stefanus had been logging to an older, unpushed copy of the tracker.
- Latest body scan: 2026-07-04 — 68.6kg, 15% body fat, 80.5% muscle mass, BCM 6402. Up from Phase 3 Start (2026-06-03: 66.7kg, 13.6% fat). Reads as a lean bulk/recomp (torso muscle +0.4kg, torso fat +0.6kg) rather than pure fat gain — see Insights tab in the app for the full breakdown.
- **Active injury note:** Thumb pain from a pull-up fall (as of the 2026-07-03 note). Thumb status not confirmed since — check with Stefanus before assuming it's resolved.
- 4 weeks into an Ipamorelin cycle as of early July 2026 (Week 6 as of 2026-07-24).
- **2026-07-24: New goal set — abs-ready by 2026-10-17.** Reviewed all 6 Phase 3 PDFs against actual logged sessions: found Saturday's "Legs + Core/Full Body/Hyrox" day had drifted into a 3rd weekly chest/shoulder session (on top of Mon Push Strength + Thu Push Hypertrophy), plus heavy redundant-exercise stacking and long drop-set ladders on Push/Pull days — root cause of ~2-hour sessions. Wrote `PHASE_4_TRAINING_PLAN.md` — a trimmed 6-day split (same weekdays) that cuts push frequency back to 2x/week, caps exercises per session at 5-6, and turns Saturday back into legs/core/conditioning only. Stefanus is following this new plan going forward — read it (not the old PDFs) for anything about his current program until he says otherwise.
- **2026-07-24: Added "Suggested Workout" card back to the tracker's Log Workout page** (between Today's Session and Current Exercise), this time sourced from `SUGGESTED_WORKOUTS` in the tracker JS (the Phase 4 plan above) instead of the old weekday auto-detect logic that was removed. It's read-only guidance, not auto-filled — updates when the Session Type dropdown changes, each exercise has a "↑ use" click to prefill it into Current Exercise, and there's a "Load All Into Current Exercise" button to prefill the whole session at once (reps only, weight left blank for Stefanus to fill in with actual load). Applied identically to `fitness_tracker.html` and `index.html`.
- **2026-07-24 (same day, revised):** Stefanus pushed back on cutting Saturday push work entirely — he wants chest/shoulders trained 3x/week for growth. Correct framing: frequency wasn't the actual problem, Saturday duplicating Monday/Thursday at *full volume* was. Saturday's `sat` plan (both in `SUGGESTED_WORKOUTS` and `PHASE_4_TRAINING_PLAN.md`) now keeps a short, light, not-to-failure push finisher (2 exercises, 2 sets each) after legs/core instead of cutting push work or restoring a full duplicate session. Weekly total lands ~15 chest sets / ~14 shoulder-press+lateral sets. Also: the Fitness folder has no `.git` — GitHub push was never going to work until it's initialized/connected to a remote; flagged to Stefanus, not yet resolved as of this note.
- **App changes (2026-07-22):** Removed the "Suggested Workout" card from Log Workout (it auto-detected a session type from the date's weekday and would silently override the Session Type dropdown whenever you tried to pick a different one — e.g. picking "Full Body" on a Wednesday got reset back to "Legs Strength"). The Session Type dropdown no longer shows "(usually Mon)"-style day hints and can be freely set regardless of the date. The pull-up/wide-grip-pulldown injury substitution logic (`EXERCISE_PAUSES`) was removed along with it since it only fed that feature — reintroduce if needed.

---

## Current Programs

| File | Program | Type |
|------|---------|------|
| `PUSH HYPERTROPHY.pdf` | Push Hypertrophy | Chest / Shoulders / Triceps |
| `PUSH STRENGTH.pdf` | Push Strength | Chest / Shoulders / Triceps |
| `PULL HYPERTROPHY.pdf` | Pull Hypertrophy | Back / Biceps |
| `Pull STRENGTH.pdf` | Pull Strength | Back / Biceps |
| `LEGS STRENGTH.pdf` | Legs Strength | Quads / Hamstrings / Glutes |
| `LEGS + CORE : FULL BODY : HYROX.pdf` | Legs + Core / Full Body / HYROX | Conditioning |

---

## Tracker

Live tracker: `fitness_tracker.html` (open in browser)
Dashboard: `index.html`

---

## Notes for Agents

- Read `FITNESS_SUMMARY.md` (this file) first before any session
- Workout programs are reference PDFs — read only the one relevant to the session
- Do NOT read all 6 PDFs on startup
- Update this summary if any program changes or new goals are set
