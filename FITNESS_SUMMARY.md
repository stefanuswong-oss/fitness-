# Fitness Summary — Stefanus Wong
**Last updated:** 2026-08-22

---

## Current Status

- **Phase 4, Week 4 complete as run: 5 of 6 sessions logged** (Aug 17–21). **Sat session skipped entirely — no time** (confirmed 08-22), not deferred. **Wk5 prescriptions are now in the tracker**, recomputed from real Wk4 data — see `SUGGESTED_WORKOUTS` in `index.html`. Sat's Wk5 carries the Wk4 targets forward unchanged (no Wk4 Sat data exists to progress from) until he next runs a Saturday session.
- **2026-08-22 data corrections** (from the phone export, applied via `applyDataCorrections()` in the tracker, not by editing localStorage directly):
  - Mon 2026-08-17 (Push Strength) and Tue 2026-08-18 (Pull Strength) were saved as **Phase 4 Week 3** — should've been **Week 4** (he forgot to bump the Log page's week selector for the first 2 sessions of the week). Relabeled by session ID.
  - **Three sessions each had one exercise logged twice** — Pull Strength (08-18, Machine Lat Pulldown), Push Hypertrophy (08-20, Cable Overhead Extension), Pull Hypertrophy (08-21, Machine Lat Pulldown). Deduped, keeping the better-performing of the two logged entries in each case. **Root cause not yet found** — Log Workout has no delete button once a session is saved, so this can only be patched in `applyDataCorrections()`, not fixed at the source. Worth a look at the Log Workout add-exercise flow since it happened 3x in one week (all on pull days + one push-hypertrophy day) — possible double-submit or a stale "add" bound to the wrong exercise.
- **Hammer Curl (Tue) still painful as of 08-22; Bayesian Curl (Tue + Fri) is now pain-free.** Skipped entirely in Wk4 rather than guessing at a weight. Since the neutral hammer grip loads the forearm more than the supinated Bayesian curl, this reads as forearm-specific, not general elbow/bicep pain — consistent with the open forearm/thumb flag below. Keep it skipped; if still painful after another week or two, worth a physio look rather than continuing to test it in the gym. Don't resume prescribing a weight for it until pain-free.
- **Bali extended, resolved 2026-08-16.** He's now in Bali through **27 Aug** (was 20/21 Aug) — a friend visits **21–27 Aug** for a wellness-focused trip (yoga/breathwork). Confirmed posture: **21–27 Aug is a planned diet break at maintenance**, same treatment as SG/HK — budget it as ~2 flexible days, not all 7, same "halves the cost" rule already used for SG. 11–20 Aug (solo) stays cut, run as written. **Scan moved Sat 22 Aug → Sat 29 Aug** (was blocked — he's still in Bali with a guest through the 27th). The Wk4 checkpoint numbers below (13.5% bf / 68.8 kg) haven't been re-modeled for the extra maintenance days; expect them to land a touch softer at the delayed scan, on the same order as the ~0.2–0.3 pt cost the SG break added — ask if a full re-projection is wanted.
- Historical note: sessions 07-24 → 07-29 were once mislabeled "Phase 3 Week 4" by a tracker bug (Log Workout Phase/Week never auto-updated). Fixed 2026-07-30 — inputs now default to the last logged session's phase/week, and a data correction relabels the affected sessions. No data was lost.
- Body scan 2026-07-30: 69.2kg, 14.2% fat, 81.2% muscle, BCM 6318 (down from 68.6kg/15% fat/80.5% muscle/BCM 6402 on 2026-07-04). Fat down, muscle up, weight roughly flat — still recomping in the right direction. BCM drop and WHR uptick (0.93, into "bad" band) are most likely bioimpedance/hydration noise rather than real muscle loss, since they moved opposite to the muscle%/fat% trend in the same reading — watch the next scan before reacting. Raw scan images in `Body Scan Log/`.
- Injury: thumb pain from a pull-up fall (noted 2026-07-03). **2026-08-11: left forearm pain, self-reported as overcompensating for the thumb**, logged on the same Pull Strength session where Lat Pulldown sits at 70kg. Neither is confirmed healed — Wk4 and Wk5 both hold Lat Pulldown at 70kg rather than progressing further, and most other Tuesday pulling numbers plateaued through Wk4 too (Straight-Arm Pulldown skipped a prescribed load add, Rear Delt and Bayesian Curl both repeated Wk3 exactly). **Hammer Curl is the one exercise still causing pain as of 08-22** (see above) — everything else on Tuesday is holding steady, not actively regressing. Don't progress pulling loads until pain-free.
- Wk3 also surfaced: a Leg Press load jump that failed badly (110→115→115kg, reps collapsed to 6 vs a 120kg/9-rep target) — pulled back for Wk4 rather than pushed through; and Thursday's Cable Lateral Raise ran a 7-stage drop-set ladder instead of one single drop. That was **the plan's instruction being unclear, not drift** — "one drop set" means one weight change at the end, not a chain. Clarified explicitly in the tracker's Wk4 note.

### Goal (final as of 2026-08-09) — read this before advising

- **The target is DECEMBER, not October.** 10 Dec (Tomorrowland, Bangkok) and 31 Dec
  (White Party) are his "album unveiling". **17 Oct (HK birthday, yacht) is a nice-to-have
  waypoint** that arrives free on the way — do not treat it as the goal.
- **Live plan: cut straight through, peak 10 Dec at ~9.7% / 66.9 kg.** ~300 kcal/day deficit
  (2,100 training days), protein 170 g, across ~14 cut weeks from 10 Aug to 30 Nov.
- **He is in HK 12–19 Oct** — a planned **diet break at maintenance**, not a lapse.
  Yacht condition (~11.3%) is banked by Sat 11 Oct.
  *(Adding the Singapore break cost ~0.3 pts vs the pre-SG model: 9.4% → 9.7%, 11.0% → 11.3%.)*
- **10–31 Dec: HOLD at maintenance.** Do not diet between the two events — arriving flat on
  the 31st is the bigger risk.
- **Block naming (his rule):** Phase 4 keeps counting **Wk 3 → Wk 11** through the cut.
  Phase increments **after HK** — **Phase 5 Wk 1 = Mon 20 Oct**, and Phase 5 is a
  **continued cut**, not a build block.
- **Muscle stays roughly flat (+0.5 kg over 17 weeks). This was an explicit, informed trade**
  — he chose cut-through over build-then-cut after seeing both sets of numbers. The
  +1 kg/4-week build target is deferred to **January**, from a ~9.7% base. Don't re-litigate.

### Travel & scans (confirmed 2026-08-09)

| Trip | Dates | Block | Posture |
|---|---|---|---|
| **Bali** | 11–20 Aug | Phase 4 Wk 3–4 | **cut — NOT a break** |
| **Bali — friend visiting** | 21–27 Aug | Phase 4 Wk 4–5 | **break (maintenance)** |
| **Singapore** (real birthday) | 17–21 Sep | Phase 4 Wk 8 | break |
| **Hong Kong** (yacht 17 Oct) | 12–19 Oct | Phase 4 Wk 12 | break |
| **Bangkok** (Tomorrowland) | ~10 Dec | Phase 5 Wk 7 | peak |

- **Bali = same FTL gym brand**, identical machines, so prescribed loads transfer exactly.
  No alcohol there. 11–20 Aug is a normal cut block that happens to be abroad.
- **21–27 Aug (friend visiting) is now a planned diet break at maintenance**, added
  2026-08-16 — same treatment as SG/HK. Budget ~2 flexible days out of the visit, not all 7,
  same halving rule used for SG. Yoga/breathwork stacks fine alongside the lifting split;
  keep training sessions in place where the schedule allows rather than swapping them out.
- **SG and HK are planned diet breaks at MAINTENANCE (~2,400), not surplus.** Breaks every
  ~5–6 weeks on a 15-week cut are good practice, not a concession. He doesn't normally drink;
  may in SG and HK — that's budgeted.
- **Three birthday celebrations**: Sep (SG, the real one), Oct (HK), Dec (BKK).
- **Scans: Sat 29 Aug · Tue 16 Sep · Sat 11 Oct · Mon 1 Dec.** The Aug scan moved from
  22→29 Aug (he's in Bali with a guest through the 27th); the Sep scan was moved off 19 Sep
  because he is in Singapore — scan pre-flight for a clean read. Same FTL branch each
  time where possible; different units calibrate differently.
- Tracker's "Suggested Workout" card carries per-week weight + rep prescriptions
  (`wk: {3:…, 4:…}`); the "Phase 4 Plan" card holds checkpoints, cut macros, protein
  schedule, scan protocol and the event protocol for 17 Oct / 10 Dec / 31 Dec. Weeks 5+
  carry Week 4 forward and prompt for double progression rather than inventing numbers.

### Peptides — factual notes only, never advise on protocol

- Ipamorelin: finishing 2nd pen ~week of 2026-08-10; buying a 3rd pen (~40 doses, ~1 month),
  which takes him to roughly mid/late September.
- **He is considering switching to retatrutide ("Reta") after ~3 months of Ipamorelin.**
  Flagged 2026-08-09: a GLP-1/GIP/glucagon triple agonist works *against* a build block, and
  starting it in the weeks before HK would be poorly timed (titration nausea). Natural window
  if he wants it is January, after December is banked.
- **Tesamorelin also asked about 2026-08-09.** Answered: wrong depot and wrong timeline for
  his goal. Its evidence base is *visceral* fat (approved for HIV-associated lipodystrophy);
  abs are hidden by *subcutaneous* fat. His visceral fat is already 5 — top of the healthy
  1–5 zone, not a problem. The trial effect is measured over 26 weeks; he has 9 to 11 Oct.
  Different receptor from Ipamorelin (GHRH analog vs ghrelin agonist) — complementary, not
  a substitute.
- **Standing position: none of these three is his limiting factor.** Week 2 showed the real
  constraints were under-fuelling and program drift, both fixed 2026-08-09. Don't recommend
  adding a compound to solve a programming problem. Revisit at the 11 Oct scan with three
  readings of trend data (30 Jul / 22 Aug / 16 Sep), not before.
- **Never advise on dosing, protocol, or whether to start/stop any of these.** Physician's
  call. Agents here may only address how a compound interacts with the training plan.

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

- `SUGGESTED_WORKOUTS` = the Phase 4 plan, with per-week `wk: { 3: {reps, weight}, 4: {…}, 5: {…} }` prescriptions. Weekday categories (Mon–Fri) have Wk5 filled in as of 2026-08-22; `sat` doesn't yet (Wk4 Sat hadn't been logged at the time). Add a `6:` key to each exercise when Week 6 is prescribed; until then Week 6+ carries Week 5 forward and shows a double-progression prompt.
- `PHASE_PLAN` = block checkpoints, macros, protein schedule, scan-day protocol. Rendered by `renderPhasePlanCard()` into the collapsible "Phase 4 Plan" card on the Log page.
- `reps`/`weight` must use the log parser's format: `"1 x 8, 1 x 8, 1 x 7"` and `"26-26-24"` (dash = per set, comma = drop stage). `compactReps()`/`compactWeight()` render these as `8 · 8 · 7` / `26 · 26 · 24` for the phone-width table — display only, the stored strings stay parseable.
- **Notes moved from per-day to per-exercise (2026-08-15).** The Log page no longer has a day-level Notes textarea; each exercise row in "Current Exercise" has its own optional note input, saved as `exercises[i].note`. Old sessions logged before this change still carry a day-level `session.note` — both are still read (History, Today's Session, "Last Time" reference, and the Session Notes card all display exercise-level notes now, falling back to the legacy day-level note where present).

---

## Notes for Agents

- Read this file first before any session
- Workout programs are reference PDFs — read only the one relevant to the session, never all 6 on startup
- Check the Hosting/Git section before saying anything about repo visibility
- Update this summary (concisely) if the program, goal, or hosting setup changes
