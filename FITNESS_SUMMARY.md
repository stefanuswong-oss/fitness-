# Fitness Summary — Stefanus Wong
**Last updated:** 2026-08-09

---

## Current Status

- **Phase 4, Week 2 complete** (Aug 3–8, all 6 sessions logged). **Week 3 begins Mon 2026-08-10** — first week of the cut, and he is in Bali 11–20/21 Aug for most of Wk 3–4.
- Historical note: sessions 07-24 → 07-29 were once mislabeled "Phase 3 Week 4" by a tracker bug (Log Workout Phase/Week never auto-updated). Fixed 2026-07-30 — inputs now default to the last logged session's phase/week, and a data correction relabels the affected sessions. No data was lost.
- Body scan 2026-07-30: 69.2kg, 14.2% fat, 81.2% muscle, BCM 6318 (down from 68.6kg/15% fat/80.5% muscle/BCM 6402 on 2026-07-04). Fat down, muscle up, weight roughly flat — still recomping in the right direction. BCM drop and WHR uptick (0.93, into "bad" band) are most likely bioimpedance/hydration noise rather than real muscle loss, since they moved opposite to the muscle%/fat% trend in the same reading — watch the next scan before reacting. Raw scan images in `Body Scan Log/`.
- Injury: thumb pain from a pull-up fall (noted 2026-07-03), last logged as still healing 2026-07-28. Lat Pulldown has since jumped to 70kg and Wk4 prescribes 75 — check before assuming resolved.

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
| **Bali** | 11–20/21 Aug | Phase 4 Wk 3–4 | **cut — NOT a break** |
| **Singapore** (real birthday) | 17–21 Sep | Phase 4 Wk 8 | break |
| **Hong Kong** (yacht 17 Oct) | 12–19 Oct | Phase 4 Wk 12 | break |
| **Bangkok** (Tomorrowland) | ~10 Dec | Phase 5 Wk 7 | peak |

- **Bali = same FTL gym brand**, identical machines, so prescribed loads transfer exactly.
  No alcohol there. It is a normal cut block that happens to be abroad.
- **SG and HK are planned diet breaks at MAINTENANCE (~2,400), not surplus.** Breaks every
  ~5–6 weeks on a 15-week cut are good practice, not a concession. He doesn't normally drink;
  may in SG and HK — that's budgeted.
- **Three birthday celebrations**: Sep (SG, the real one), Oct (HK), Dec (BKK).
- **Scans: Sat 22 Aug · Tue 16 Sep · Sat 11 Oct · Mon 1 Dec.** The Sep scan was moved off
  19 Sep because he is in Singapore — scan pre-flight for a clean read. Same FTL branch each
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

- `SUGGESTED_WORKOUTS` = the Phase 4 plan, with per-week `wk: { 3: {reps, weight}, 4: {…} }` prescriptions. Add a `5:` key to each exercise when Week 5 is prescribed; until then Week 5+ carries Week 4 forward and shows a double-progression prompt.
- `PHASE_PLAN` = block checkpoints, macros, protein schedule, scan-day protocol. Rendered by `renderPhasePlanCard()` into the collapsible "Phase 4 Plan" card on the Log page.
- `reps`/`weight` must use the log parser's format: `"1 x 8, 1 x 8, 1 x 7"` and `"26-26-24"` (dash = per set, comma = drop stage). `compactReps()`/`compactWeight()` render these as `8 · 8 · 7` / `26 · 26 · 24` for the phone-width table — display only, the stored strings stay parseable.

---

## Notes for Agents

- Read this file first before any session
- Workout programs are reference PDFs — read only the one relevant to the session, never all 6 on startup
- Check the Hosting/Git section before saying anything about repo visibility
- Update this summary (concisely) if the program, goal, or hosting setup changes
