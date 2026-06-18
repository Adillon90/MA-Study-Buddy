# Multi-State Rollout Tracker

The 19 states the product covers. Architecture (locked): **national core built once + a small per-state regulatory overlay**. Each new state is overlay-only, reusing the national core, question-bank structure, and flashcard structure. See `LIFE-production-plan.md` and `project-multistate-architecture` memory.

## Status

| # | State | Life (16-51 equiv) | A&H | Notes |
|---|-------|:---:|:---:|-------|
| 1 | Massachusetts | ✅ done | ✅ done | Reference build: tutor + bank (98 Q) + decks, all verified |
| 2 | California | ✅ live | ✅ live | TWO separate PSI exams: Life-Only (75q) + A&H (75q); combined 150q also offered. Tutor + decks live in both app files. Verified vs CIC/CDI/CLHIGA: elected commissioner since 1991 (12900), free look 10d general / 30d seniors 60+ (10127.9/10127.10), replacement 30d refund (10509), nonforfeiture cash/RPU/ET, divorced-spouse auto-revocation, A&S provisions §§10350.2-.7 (grace 7/10/31, incontest 2yr, reinstate 45/10/60, notice 20, forms 15, proof 90), Cal-COBRA 2-19 emp/36mo/110% (10128.50), CLHIGA 80% haircut $300k death/$100k cash/$250k annuity/$300k aggregate, health $200k indexed, CE 24h/3 ethics + annuity 8+4 + LTC 8. CA uses standard NAIC lettered Medigap. Source docs in `modules/states/CA/`. Pending (optional): detailed A&H exam weights, CA mandated-benefits list, nonforfeiture day-counts. |
| 3 | Colorado | ⬜ | ⬜ | |
| 4 | Connecticut | ✅ live | ✅ live | Combined Life+Health (18-03), Pearson VUE. Tutor + 4 decks live. Verified: free look 10d (38a-436), health grace 7/10/31 + incontestability 2yr + reinstatement (38a-483), nonforfeiture 60-day/3-yr/6-mo defer (38a-439), replacement reg 38a-480, continuation-until-eligible (38a-512a), guaranty $500k (38a-858), CE 24h. Only mandated-benefits list left (optional). |
| 5 | Georgia | ⬜ | ⬜ | |
| 6 | Indiana | ⬜ | ⬜ | |
| 7 | Maine | ⬜ | ⬜ | |
| 8 | Michigan | ⬜ | ⬜ | |
| 9 | New Hampshire | ⬜ | ⬜ | |
| 10 | New Jersey | ⬜ | ⬜ | |
| 11 | New York | ⬜ | ⬜ | |
| 12 | North Carolina | ⬜ | ⬜ | |
| 13 | Pennsylvania | ⬜ | ⬜ | |
| 14 | Rhode Island | ⬜ | ⬜ | |
| 15 | South Carolina | ⬜ | ⬜ | |
| 16 | Tennessee | ⬜ | ⬜ | |
| 17 | Vermont | ⬜ | ⬜ | |
| 18 | Virginia | ⬜ | ⬜ | |
| 19 | West Virginia | ⬜ | ⬜ | |

## What each new state needs
1. **Exam content outline** for the state's Life and/or A&H exam (most use NAIC-based outlines; pull from the state's testing vendor — Prometric/PSI/Pearson VUE — the same way the MA 16-51 outline was pulled).
2. **State statute overlay** — the state-specific values (free look, replacement, nonforfeiture, guaranty limits, licensing rules) pulled and verified from that state's legislature/insurance-dept site. NOT guessed.
3. **App wiring** — a STATE picker (the current selector is line-only, state fixed to MA), and per-state overlay constants composed with the national core.
4. Optional per state: question bank + flashcard decks (national questions reuse; only the state-overlay questions are new).

## Decisions
- **Lines:** both Life and A&H per state.
- **Approach:** pilot one state end-to-end first (Connecticut), then scale.

## Pilot: Connecticut (in progress)
- **Testing vendor:** Pearson VUE (not Prometric). Outline cites CT statutes inline as `Ref: 38a-...` (Title 38a = CT insurance code), same model as the MA Prometric outline.
- **Exam structure:** ONE combined **Life + Accident & Health exam, Series 18-03**, 150 questions. Sections 1-8 are Life (map almost 1:1 onto our MA Life modules), sections 9-16 are Health. Source saved: `modules/states/CT/CT-18-03-content-outline.pdf` + `.txt`.
- **Key overlay statute refs found:** free look/right to return 38a-495a-13(d), 38a-483(a)(3), 38a-476; grace period 38a-495a(m); replacement 38a-480-1 to 480-5. Values to be pulled from the CT General Statutes (cga.ct.gov) and verified before use.

### Structural wrinkle (affects the app's selector)
MA has **two separate** exams (Life 16-51, A&H 16-52) → two tabs. CT has **one combined** Life+Health exam (18-03). So the state picker can't assume a fixed Life/A&H pair per state; the available exam(s) vary by state. The selector needs to be data-driven per state (some states = 2 exams, some = 1 combined).

## Pilot remaining steps
1. Pull + verify the CT overlay statutes (Life + Health) from cga.ct.gov
2. Refactor the A&H modules into national core + state overlay (one-time, needed for A&H scaling)
3. Build CT overlay modules (Life + Health)
4. Add a STATE picker to the app; make the exam/line selector data-driven per state
5. Build CT SYSTEM_PROMPT(s), starters, decks; verify
6. Then replicate to the other 17 states
