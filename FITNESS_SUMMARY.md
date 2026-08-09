# Fitness Summary — Stefanus Wong
**Last updated:** 2026-08-09

---

## Current Status

- Phase 4, Week 1 (corrected 2026-07-30 — sessions 07-24 through 07-29 had been mislabeled "Phase 3 Week 4" due to a tracker bug where the Log Workout Phase/Week fields never auto-updated; no session data was lost, only the phase/week tag. Fixed in code: inputs now default to the last logged session's phase/week, and a data correction relabels the affected sessions).
- Body scan 2026-07-30: 69.2kg, 14.2% fat, 81.2% muscle, BCM 6318 (down from 68.6kg/15% fat/80.5% muscle/BCM 6402 on 2026-07-04). Fat down, muscle up, weight roughly flat — still recomping in the right direction. BCM drop and WHR uptick (0.93, into "bad" band) are most likely bioimpedance/hydration noise rather than real muscle loss, since they moved opposite to the muscle%/fat% trend in the same reading — watch the next scan before reacting. Raw scan images in `Body Scan Log/`.
- Injury: thumb pain from a pull-up fall (noted 2026-07-03), last logged as still healing 2026-07-28. Lat Pulldown has since jumped to 70kg and Wk4 prescribes 75 — check before assuming resolved.
- Ipamorelin: Week 6 as of 2026-07-24.

### Goal (pivoted 2026-08-09) — read this before advising

- **Abs on the yacht 17 Oct (HK birthday), then 12% body fat by December.** Both are now
  achievable — see `PHASE_4_TRAINING_PLAN.md` header for the live sequence.
- **He is in HK 12–19 Oct.** Birthday + yacht on the 17th. Diet off-plan and training
  intermittent that week **by design** — that is planned for, not a lapse. Peak condition is
  banked by Sat 11 Oct.
- **Calorie posture: moderate CUT (~2,100 kcal training days, ~275/day deficit), protein UP
  to 170 g.** He chose the moderate rate over the aggressive one. Do not push harder unless
  two consecutive scans show under 0.2 kg/wk of fat loss.
- **Block naming (his rule, as updated 2026-08-09):** **Phase 4 keeps counting Wk 3 → Wk 11**
  through the cut (10 Aug – 11 Oct). The phase increments **after HK** — **Phase 5 Wk 1 starts
  Mon 20 Oct** as the post-HK build block. Do NOT increment the phase before 20 Oct, and do
  not increment it at the start of the deficit.
- Muscle is expected flat-to-+0.4 kg through the cut. The +1 kg/4-week-block target resumes
  in Phase 5 from 20 Oct. Don't promise both at once.
- Tracker's "Suggested Workout" card carries **per-week weight + rep prescriptions**
  (`wk: {3:…, 4:…}`); the "Phase 4 Plan — Targets & Nutrition" card holds the checkpoint
  table, cut macros, protein schedule, scan-day protocol and the peak/HK-week guidance.
  Weeks 5+ carry Week 4 forward and prompt for double progression instead of inventing numbers.

### Peptides — factual notes only, never advise on protocol

- Ipamorelin: finishing 2nd pen ~week of 2026-08-10; buying a 3rd pen (~40 doses, ~1 month),
  which takes him to roughly mid/late September.
- **He is considering switching to retatrutide ("Reta") after ~3 months of Ipamorelin.**
  Flagged 2026-08-09: a GLP-1/GIP/glucagon triple agonist works *against* a build block, and
  starting it in the weeks before HK would be poorly timed. Sequencing discussed; the decision
  and any dosing is for his prescribing physician, not for agents here.

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
**Keep the two files byte-identical** — edit `index.html`, then `cp index.html fitness_tracker.html`.

- `SUGGESTED_WORKOUTS` = the Phase 4 plan, with per-week `wk: { 3: {reps, weight}, 4: {…} }` prescriptions. Add a `5:` key to each exercise when Week 5 is prescribed; until then Week 5+ carries Week 4 forward and shows a double-progression prompt.
- `PHASE_PLAN` = block checkpoints, macros, protein schedule, scan-day protocol. Rendered by `renderPhasePlanCard()` into the collapsible "Phase 4 Plan" card on the Log page.
- `reps`/`weight` must use the log parser's format: `"1 x 8, 1 x 8, 1 x 7"` and `"26-26-24"` (dash = per set, comma = drop stage). `compactReps()`/`compactWeight()` render these as `8 · 8 · 7` / `26 · 26 · 24` for the phone-width table — display only, the stored strings stay parseable.

---

## Notes for Agents

- Read this file first before any session
- Workout programs are reference PDFs — read only the one relevant to the session, never all 6 on startup
- Check the Hosting/Git section before saying anything about repo visibility
- Update this summary (concisely) if the program, goal, or hosting setup changes
