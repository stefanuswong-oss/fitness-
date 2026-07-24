# Fitness Summary — Stefanus Wong
**Last updated:** 2026-07-24

---

## Current Status

- Phase 3, Week 4. Full session history embedded in tracker (through 2026-07-23).
- Body scan 2026-07-04: 68.6kg, 15% fat, 80.5% muscle, BCM 6402 (up from 66.7kg/13.6% fat on 2026-06-03 — lean bulk/recomp, not pure fat gain — see Insights tab).
- Injury: thumb pain from a pull-up fall (noted 2026-07-03), status unconfirmed since — check before assuming resolved.
- Ipamorelin: Week 6 as of 2026-07-24.
- Goal: abs-ready by 2026-10-17. Training on **Phase 4 plan** — see `PHASE_4_TRAINING_PLAN.md` for full rationale (fixed a 3rd accidental full chest/shoulder session on Saturdays, exercise redundancy, drop-set bloat). Chest/shoulders stay 2x/week + a short light Saturday finisher (his call, kept deliberately light). One ab exercise per weekday + Saturday core rotation. Tracker's "Suggested Workout" card (Log Workout page) mirrors this plan live — read that doc, not the old Phase 3 PDFs, for anything about his current program.

---

## Hosting / Git — settled, don't relitigate

- Repo: https://github.com/stefanuswong-oss/fitness- — **must stay public.** GitHub Pages free tier only serves sites from public repos; going private takes the live app down (happened 2026-07-24, caused real downtime). Don't suggest making it private again unless he upgrades to GitHub Pro or moves hosting off Pages.
- Live app (his iPhone home-screen icon points here): https://stefanuswong-oss.github.io/fitness-/
- Local Fitness folder = source of truth, already `git init`'d and connected to the repo above.
- Normal update workflow: `cd ~/Claude/Projects/Fitness && git add . && git commit -m "..." && git push`
- If a new token is ever needed: classic PAT with full `repo` scope (not `public_repo` only). A separate, unrelated token "WONGSO Tracker Auto-Push" exists on his account for other work — never touch it.

---

## Current Programs (reference PDFs — superseded by Phase 4 plan above, keep for exercise-detail lookup only)

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

Live tracker: `fitness_tracker.html` / `index.html` (identical, both deployed via GitHub Pages — see Hosting section)
`SUGGESTED_WORKOUTS` in the tracker JS = Phase 4 plan, editable there if the plan changes again.

---

## Notes for Agents

- Read this file first before any session
- Workout programs are reference PDFs — read only the one relevant to the session, never all 6 on startup
- Check the Hosting/Git section before saying anything about repo visibility
- Update this summary (concisely) if the program, goal, or hosting setup changes
