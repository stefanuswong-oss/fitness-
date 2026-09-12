# Fitness Summary — Stefanus Wong
**Last updated:** 2026-09-12

---

## Current Status

- **Added: per-exercise delete on saved sessions (2026-09-12), plus a significant bug fix it exposed.** The History page already had a "Delete this session" button for whole days; there was no way to remove a single wrong or duplicate exercise row without a code-level `applyDataCorrections()` patch — the exact gap behind every duplicate-logging fix above. Each exercise row in an expanded History card now has its own ✕ that deletes just that row from `custom_sessions` in localStorage (matches by name+reps+weight, not raw array position, so it's safe even for sessions `applyDataCorrections()` has already touched) and re-renders. Tested end-to-end in a local preview before shipping. **While testing, found that the History page literally could not show any Phase 4 session** — `PHASE_NAMES` and the render loop only knew about Phases 1–3, so every Phase 4 session (all of Week 1 onward) was silently invisible in History even though the total count at the top included them. Fixed: added Phase 4 to both, moved the "(Current)" tag off Phase 3 onto Phase 4. This means the History tab has been unusable for anything from the current training block until now — worth keeping in mind if anything else "current-phase" seemed to be missing from a view.
- **Phase 4 Week 7 (Sep 7–12) ran clean, with two data-entry issues caught and fixed 2026-09-12.** (1) Mon 09-07 Push Strength was saved as Week 6 — should've been Week 7 (he forgot to bump the Log page's week selector, caught it mid-session or the next day). (2) **Duplicate-logging bug hit that same session again**: Incline Press, Chest Press, and Cable Lateral Raise each saved an identical row twice; Machine Shoulder Press saved twice with a 1-rep difference (10,10,8 vs 10,10,9). Both fixed via `applyDataCorrections()` in the tracker (session id `custom_1788769003099`), not by editing localStorage — same pattern as the 2026-08-22 corrections. **This is now the 5th+ week this bug has recurred** (previously: three Wk4 sessions 08-22, Rope Pushdown + Abductor in Wk6) — general root cause for whole-row duplicates (vs. the specific Cable Lateral Raise drop-stage bug below) still not found. *(Mitigated 2026-09-12 — see the History-page fix below: any wrong or duplicate exercise row can now be deleted directly, no code patch needed.)*
  - **Real Wk7 results, by day:** Mon (Push Strength) — most lifts one rep short of a clean sweep for the 2nd-3rd week running (Incline Press, Chest Press, Shoulder Press); Rope Pushdown reps matched but the set-1 weight bump to 49.9 wasn't taken (stayed 45.4, likely just missed the app update); Cable Abs Crunch hit its first-ever clean 15×3 sweep. Tue (Pull Strength) — best pulling session in weeks: Lat Pulldown clean 4×8 @ 70 for the 3rd week running, Straight-Arm Pulldown's contingent bump landed clean (though form broke down on the 34kg top set — holding there, not adding), Rear Delt/Bayesian on target. **Hammer Curl was finally tested after ~4 weeks parked** — switched from DB to cable, pain-free, 15,15,12 @ 9.1-13.4-18.1; real progress, watch it over the next couple of weeks. Wed (Legs Strength) — gym was packed/chaotic (arrived earlier than usual); V-Squat never reached its top set at all (only 3 of 4 sets done); Leg Curl and Standing Cable Crunch were skipped entirely; everything else that WAS run (Leg Press, Hip Thrust, Abductor, Leg Extension) hit or cleared target — Leg Press's clean sweep is the first in a while. Thu (Push Hypertrophy) — Shoulder Press and OH Ext both landed their top-set adds clean; Incline Press missed its top-set bump (didn't see the update, stayed at 24 not 26); the stretch-focused Cable Fly found a way past the 5kg-step ceiling by adding a 2.5kg plate (10-10-12.5). **Cable Lateral Raise drop-set bug — root cause found 2026-09-12, not user error.** He flagged the same issue on the Wk6 data too and was right both times: he only ever did ONE drop after set 3, but `initSuggestedWorkoutClicks()` called `prefillExercise()` without `stripDrops:false`, so tapping this exercise from the Suggested Workout card (rather than "Load all") silently dropped the prescribed drop-set structure — leaving no on-screen reference for what the drop should look like, so he rebuilt it from scratch each time and ended up with extra rows. **Fixed at the source in `index.html`** (2026-09-12) — `prefillExercise()` now takes a `stripDrops` param, defaulting `true` for the Log Reference "Use" case (past performance shouldn't auto-carry) but `false` for the Suggested Workout tap (a prescribed drop must survive the load). Wk6 (`custom_1788406212673`) and Wk7 (`custom_1789013979049`) saved data corrected via `applyDataCorrections()` to the single real drop stage each. The pattern likely traces back further — Wk2's Cable Lateral Raise shows the same shape with even more duplicate stages — but only the two most recent weeks were corrected; earlier weeks weren't worth the retroactive cleanup. Also swapped the weight target from an unachievable 17.4 notch to the 18.1 he actually hit. Fri (Pull Hypertrophy) — Lat Pulldown and Low Row held/landed their contingent bumps clean, Rear Delt and Bayesian both cleared; Cross-Body Lat Pulldown's numbers were too messy to read as a clean beat (he misread set 1, compensated with extra reps elsewhere) — held its target rather than progressing off noisy data. Sat (Legs+Core) — **Hip Thrust cleared a full clean 4×12 @ 85 for the first time**; Glute Kickback and the core crunch both hit/beat target; Leg Curl slipped slightly (12,12,10). **Added Shrug** (12,12,12 @ 18-20-20) for the first time in a while — logged but not yet part of the formal program; not added to `SUGGESTED_WORKOUTS` without reading the relevant PDF first, per the hard rule — worth folding in properly once back from Singapore if it's meant to stick.
- **Phase 4 Week 8 prescribed 2026-09-12** (`wk.8` on every exercise). Wk8 splits in two: **Mon–Wed (14–16 Sep) are still home days** — real double progression off Wk7 data (Lat Pulldown top → 72.5, Cable Abs Crunch top → 59, Abductor top → 70; V-Squat and Leg Press get careful retries of adds that were interrupted/collapsed before; Leg Curl and Standing Cable Crunch carry forward untested). **Wed 16 Sep is also the pre-flight scan** — Legs Strength runs first, scan after (post-workout/post-lunch state, same as always — note the summary previously mislabeled this "Tue 16 Sep"; 16 Sep is actually a Wednesday). **Thu–Sat (17–19 Sep) fall inside the Singapore trip** (fly out Thu 17 Sep) — Push Hypertrophy, Pull Hypertrophy, and Sat all just hold Wk7's numbers flat, no new adds, same no-pressure treatment Wk5's Bali-resort days got. Earned bumps from clean Wk7 hypertrophy/Sat performance (Shoulder Press, OH Ext, Lat Pulldown, Low Row, Rear Delt, Bayesian, Glute Kickback, core, and the newly-earned Hip Thrust top-set add) are all **parked for Wk9**, not added mid-trip.
- **Phase 4 Week 6 (Aug 31–Sep 6) ran clean and complete — first full home week since the travel block, and every session logged.** Mon–Fri all hit their numbers, most one rep short of a clean sweep, nothing regressed. **Legs fully recovered:** Wed was the first complete leg day in weeks (V-Squat clean 8,8,8,8 @ 115, Hip Thrust 10,10,10 @ 95) and Abductor + Standing Cable Crunch were finally run. **Saturday finally ran in full** (first since Wk3) — Hip Thrust 85, hams, Glute Kickback, core (cable crunch + leg raise), light push finisher kept capped, 25-min walk done. Fri Machine Lat Pulldown took the contingent +2.5 to 62.5 top set and hit 12,12,12,10 → forearm tested clean under load. **Hammer Curl was NOT tested** (~4 weeks parked now). **Duplicate-logging bug recurred:** Rope Pushdown (Mon) + Abductor (Wed) each saved twice; Thu Cable Lateral Raise drop saved 3 identical stages again (4th week — Stefanus flagged it, believes he did one).
- *(Superseded by the Wk7-results/Wk8-prescription bullets above, 2026-09-12 — kept for history.)* **Phase 4 Week 7 prescribed 2026-09-06** (`wk.7` on every exercise in `SUGGESTED_WORKOUTS`, from real Wk6 data). Wk7 is the last hard week before Singapore (Wk8 = diet break, scan Tue 16 Sep pre-flight). **Earned load adds:** V-Squat top → 117.5, Machine Hip Thrust top → 100, Standing Cable Crunch top → 54.4, Thu Incline top → 26, Thu Shoulder Press top → 45, Thu OH Ext top → 31.8, Fri Rear Delt top → 31.8, Fri Bayesian top → 27.2, Sat Glute Kickback top → 29.5, Mon Rope Pushdown set 1 → 49.9. **Forearm-contingent bumps** (take only if set 1 is 100% clean, else repeat): Tue Straight-Arm Pulldown set 1 → 31.8, Fri Low Row top → 62.5. Everything else holds load, chases the last reps. **Tue Lat Pulldown still held flat at 70.**
- **Thursday 2nd-press slot: the stretch-focused Cable Chest Fly is KEPT for Wk7** (decision was deferred to when Wk7 got prescribed). Still a swap not an add — Monday keeps both presses; the Iso-leverage Decline restore belongs in the deferred January build block. Wk6 cleared it 3×15 @ 5-10-10 (home gym has 5 kg steps only); Wk7 holds load and progresses rep quality (1-count stretch pause, slow negative).
- **Phase 4 Week 5 ran as a travel week (Aug 24–29) — all sessions logged, none to plan on the strength side.** Mon–Wed were at the Bali resort with the visiting friend (diet break, per plan): improvised DB/cable work, *none* of the Push/Pull/Legs **strength** asks attempted. Thu was a flight day (lost). Fri = Push Hypertrophy, Sat = Pull Hypertrophy — both run properly at the Surabaya home gym after the flight, both progressed cleanly off Wk4 (Shoulder Press held its +5 kg, Low Row +5 kg, +1 rep in several places). **Sat Legs + Core skipped** — 2nd running (Wk4 also skipped). No duplicate-logging bug this week.
- **Wk6 prescriptions now in the tracker** (added 2026-08-30, `SUGGESTED_WORKOUTS` in `index.html`). **Mon–Tue–Wed strength days repeat the Wk5 asks unchanged** — those progress off *Wk4 real data*, NOT the light resort logs, so the "carried forward" baseline is the un-attempted Wk5 target. Thu/Fri hypertrophy = double progression off the real Wk5 Fri/Sat sessions. Pulling loads still held flat per the forearm flag — except Machine Lat Pulldown (Fri), which cleared 12×4 at 60 kg: Wk6 offers 62.5 kg on the top set *only if* the forearm tests 100% clean on set 1, else stay 60. Sat still carries Wk3-derived targets (no real Saturday since Wk3).
- **Legs are light: one full session in ~3 weeks** (Wk4 Wed). Wk5 Wed was token resort work (DB lunges + sumo squat only); Sat skipped twice. Not a muscle-loss risk yet on a cut, but a 3rd light week would be. Plan: resume the normal split, **no makeup volume**, expect V-Squat/Leg Press to feel rusty and rebuild reps before adding load.
- **Scan done Mon 31 Aug** (gym ~2 PM, post-workout / post-lunch per protocol — Push Strength = upper day, leg readings comparable). **Result: 69.1 kg · 15.2% fat (10.5 kg fat mass) · 80.2% muscle (~55.4 kg) · BCM 6385 · visceral fat 5 · WHR 0.98 · BMR 1579 · body age 46.** Softer than the 13.5% bf / 68.8 kg checkpoint row, as expected — captures the full 21–27 Aug diet break + the maintenance days after. **Fat is UP ~1 pt vs 30 Jul (14.2% → 15.2%); WHR 0.93 → 0.98.** This is the Wk4/Wk5 checkpoint. **Full re-projection to December still owed — offered to Stefanus 2026-08-31, not yet run.** Raw scan image was pasted in chat 2026-08-31; not yet saved to `Body Scan Log/`.
- **Thursday (Push Hypertrophy) Wk6: 2nd press swapped → deep stretch-focused Cable Chest Fly** (3×15 @ ~6–8 kg/side), made 2026-08-31 in `SUGGESTED_WORKOUTS`. Stefanus flagged pecs as his priority/lagging muscle and asked to add a fly to **both** Mon + Thu. Declined the straight addition — it re-adds the 3rd chest movement Phase 4 deliberately cut, and mid-cut is the worst slot to add volume (the Week 2 load-regression pattern). Did a **same-slot swap** on the hypertrophy day instead: same set count, no added fatigue, supplies the lengthened-position stimulus the two presses miss. **Monday untouched** (both presses stay — heavy overload day). Wk7 decision (keep the fly vs restore the press) to be made when Wk7 is prescribed — in-app it carries the fly forward until then. Real chest-emphasis window = the deferred **January** build block, from a lean base. Reasoning logged in `PHASE_4_TRAINING_PLAN.md` §"Phase 4 Week 3–4 — prescribed loads".
- **Wk6 (Aug 31–Sep 6) is a clean home week** — back in Surabaya, home gym, no travel until Singapore (17–21 Sep).
- **2026-08-22 data corrections** (from the phone export, applied via `applyDataCorrections()` in the tracker, not by editing localStorage directly):
  - Mon 2026-08-17 (Push Strength) and Tue 2026-08-18 (Pull Strength) were saved as **Phase 4 Week 3** — should've been **Week 4** (he forgot to bump the Log page's week selector for the first 2 sessions of the week). Relabeled by session ID.
  - **Three sessions each had one exercise logged twice** — Pull Strength (08-18, Machine Lat Pulldown), Push Hypertrophy (08-20, Cable Overhead Extension), Pull Hypertrophy (08-21, Machine Lat Pulldown). Deduped, keeping the better-performing of the two logged entries in each case. At the time, root cause wasn't found and there was no way to fix a saved session's data except patching `applyDataCorrections()`. *(Superseded 2026-09-12 — see below: per-exercise delete now exists, and the Cable Lateral Raise instance of this pattern got its root cause fixed.)*
- **Hammer Curl (Tue) still painful as of 08-22; Bayesian Curl (Tue + Fri) is now pain-free.** Skipped entirely in Wk4 rather than guessing at a weight. Since the neutral hammer grip loads the forearm more than the supinated Bayesian curl, this reads as forearm-specific, not general elbow/bicep pain — consistent with the open forearm/thumb flag below. Keep it skipped; if still painful after another week or two, worth a physio look rather than continuing to test it in the gym. Don't resume prescribing a weight for it until pain-free.
  - **Update 2026-08-30:** now skipped Wk4 + Wk5 (Wk5 Tue was the resort week, not tested at all) — effectively ~3 weeks untested. Wk6 note in the tracker says: try one light set on the neutral grip; any pain → book the physio rather than re-testing again next week.
  - **Update 2026-09-06:** NOT tested in Wk6 either — ~4 weeks parked. Wk7 tracker note escalated: one light neutral-grip set this week or book the physio. No more open-ended deferral, no working weight prescribed until pain-free.
- **Bali extended, resolved 2026-08-16 — now over.** He was in Bali through **27 Aug** (was 20/21 Aug) — a friend visited **21–27 Aug** for a wellness-focused trip (yoga/breathwork); **21–27 Aug was a planned diet break at maintenance**, same treatment as SG/HK — ~2 flexible days, not all 7. 11–20 Aug (solo) ran as a cut. **He flew back Thu 27 Aug and is in Surabaya (home gym) as of Wk6.** **Scan moved Sat 22 Aug → Sat 29 Aug → Mon 31 Aug** (each move because he was still travelling that weekend). The Wk4/Wk5 checkpoint numbers below (13.5% bf / 68.8 kg) haven't been re-modeled for the extra maintenance days; expect the 31 Aug scan to land a touch softer, on the order of the ~0.2–0.3 pt cost the SG break added — offer a full re-projection once the numbers are in.
- Historical note: sessions 07-24 → 07-29 were once mislabeled "Phase 3 Week 4" by a tracker bug (Log Workout Phase/Week never auto-updated). Fixed 2026-07-30 — inputs now default to the last logged session's phase/week, and a data correction relabels the affected sessions. No data was lost.
- Body scan 2026-07-30: 69.2kg, 14.2% fat, 81.2% muscle, BCM 6318 (down from 68.6kg/15% fat/80.5% muscle/BCM 6402 on 2026-07-04). Fat down, muscle up, weight roughly flat — still recomping in the right direction. BCM drop and WHR uptick (0.93, into "bad" band) are most likely bioimpedance/hydration noise rather than real muscle loss, since they moved opposite to the muscle%/fat% trend in the same reading — watch the next scan before reacting. Raw scan images in `Body Scan Log/`.
- Injury: thumb pain from a pull-up fall (noted 2026-07-03). **2026-08-11: left forearm pain, self-reported as overcompensating for the thumb**, logged on the same Pull Strength session where Lat Pulldown sits at 70kg. Neither is confirmed healed — Wk4/Wk5/Wk6 all hold Tuesday's Lat Pulldown at 70kg, and most other Tuesday pulling numbers plateaued through Wk4 too (Straight-Arm Pulldown skipped a prescribed load add, Rear Delt and Bayesian Curl both repeated Wk3 exactly). **Hammer Curl is the one exercise still causing pain as of 08-22** (see above) — everything else on Tuesday is holding steady, not actively regressing. Don't progress pulling loads until pain-free — **one deliberate exception (2026-08-30):** Friday's *hypertrophy* Machine Lat Pulldown cleared 12×4 at 60kg twice, so Wk6 offers a single 2.5kg bump on the top set only, contingent on the forearm feeling 100% clean on the first set. If he takes it and the forearm complains, drop straight back to 60.
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
- **Scans: Mon 31 Aug · Wed 16 Sep · Sat 11 Oct · Mon 1 Dec.** (Corrected 2026-09-12 —
  16 Sep is actually a Wednesday, not the "Tue 16 Sep" this used to say; the date itself was
  always right.) The Aug scan moved 22→29→31 Aug (still travelling each weekend) — scan at
  the gym after that day's session (his usual post-workout / post-lunch state; do NOT switch
  to fasted/AM). The Sep scan lands on a Legs Strength day, not Push Strength — same
  post-workout rule applies regardless of which session precedes it.
  The Sep scan was moved off 19 Sep because he is in Singapore — scan pre-flight for a
  clean read. Same FTL branch each time where possible; different units calibrate differently.
- Tracker's "Suggested Workout" card carries per-week weight + rep prescriptions
  (`wk: {3:…, 4:…, 5:…, 6:…}`); the "Phase 4 Plan" card holds checkpoints, cut macros, protein
  schedule, scan protocol and the event protocol for 17 Oct / 10 Dec / 31 Dec. Weeks 7+
  carry Week 6 forward and prompt for double progression rather than inventing numbers.

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

- `SUGGESTED_WORKOUTS` = the Phase 4 plan, with per-week `wk: { 3: {reps, weight}, 4: {…}, … }` prescriptions. **All six categories (Mon–Fri + `sat`) have Wk3–Wk7 filled in as of 2026-09-06.** Add an `N:` key to each exercise when Week N is prescribed (from that week's real logged data); until then Week N carries the last defined week forward via `resolveRx()` and shows a double-progression prompt banner.
- `PHASE_PLAN` = block checkpoints, macros, protein schedule, scan-day protocol. Rendered by `renderPhasePlanCard()` into the collapsible "Phase 4 Plan" card on the Log page.
- `reps`/`weight` must use the log parser's format: `"1 x 8, 1 x 8, 1 x 7"` and `"26-26-24"` (dash = per set, comma = drop stage). `compactReps()`/`compactWeight()` render these as `8 · 8 · 7` / `26 · 26 · 24` for the phone-width table — display only, the stored strings stay parseable.
- **Notes moved from per-day to per-exercise (2026-08-15).** The Log page no longer has a day-level Notes textarea; each exercise row in "Current Exercise" has its own optional note input, saved as `exercises[i].note`. Old sessions logged before this change still carry a day-level `session.note` — both are still read (History, Today's Session, "Last Time" reference, and the Session Notes card all display exercise-level notes now, falling back to the legacy day-level note where present).

---

## Notes for Agents

- Read this file first before any session
- Workout programs are reference PDFs — read only the one relevant to the session, never all 6 on startup
- Check the Hosting/Git section before saying anything about repo visibility
- Update this summary (concisely) if the program, goal, or hosting setup changes
