# A&H Refactor: National Core + State Overlay Separation Map

Goal: make A&H scale like Life. Today the 10 MA A&H modules bake MA statutes inline. Split each into a **national core** (universal/federal content, reused by every state) and a **MA overlay** (MA-specific statutes). New states then add only an overlay, exactly like Life.

Structure (mirrors `modules/life/`):
- `modules/ah/national/ah-section-N-*.md` — universal core
- `modules/ah/MA/ah-MA-section-N-*.md` — MA statute overlay

## Separation by module (grounded in MA-statute density + content review)

| § | Module | MA-ref density | National core (universal/federal) | MA overlay (state statute) |
|---|--------|:---:|---|---|
| 1.0 | Insurance Regulation | high (19) | Licensing concepts, marketing/ethics concepts, federal (FCRA, 1033) | **Most of it**: licensing values, CE hours, appointment/termination days, 14 grounds, fines, privacy 175I |
| 2.0 | General Insurance | minimal (2) | **~all of it** (risk, insurers, agency, contracts) — same as Life §2 | 211 CMR 95 variable-products touch only |
| 3.0 | A&H Basics | mixed (13) | Perils, policy classes, limited policies, HSA/MSA, underwriting sources (MIB/APS), replacement concept | Limited-policy notices, marketing 211 CMR 40, outline-of-coverage 211 CMR 42.09, HIV 211 CMR 36.05, genetic 175:108H/I, replacement 211 CMR 42.08, **MA mandate/MCC c.111M** |
| 4.0 | Policy Provisions | low (6) | The 12 NAIC **Uniform Individual Policy Provisions** (universal) | MA adoption specifics, prompt-pay, any MA day-count deviations |
| 5.0 | Disability Income | low (5) | **~all of it** (own/any-occ, elimination/benefit periods, residual, business DI, SSDI) | MA minimum benefit standards 211 CMR 42.05(1)(g) |
| 6.0 | Health Insurance Plans | high (23) | Plan mechanics (HMO/PPO/indemnity), HIPAA, utilization review, **ACA/PHS Act**, federal MHPAEA | Dependent/newborn/adopted cluster (47C, 108, 110, 176A/B/G), **176O appeals + OPP**, cost transparency 176O:23, open enrollment 176J:4, MA parity 47B |
| 7.0 | Large Group Health | high (17) | Group concepts, COB, **COBRA/ERISA/ADEA**, Medicare secondary, funding | MA mini-COBRA/continuation 175:110D/G/I, small-employer 176J/211 CMR 66, MA nondiscrimination |
| 8.0 | Dental | none (0) | **100% of it** (100/80/50, predetermination, integrated deductible) | none |
| 9.0 | Seniors / LTC | high (19) | **Federal Medicare** (Parts A-D, enrollment, cost-sharing), LTC concepts/ADLs | **MA standardized Medigap (Core, Supplement 1)** c.176K/211 CMR 71, LTC regs 211 CMR 65 |
| 10.0 | Federal Tax | none (0) | **100% of it** (federal/IRS) | none |

## Execution order (cleanest first)
1. **Pure national, move as-is** (header reframe only): §2, §8, §10, and §5 (tiny overlay). Fast.
2. **Light split**: §4 (uniform provisions national, small MA overlay), §3 (core + MA layer).
3. **Surgical split** (heavy MA layer in clean blocks): §6, §7, §9, §1.

## Shared-with-Life note
§1 Regulation and §2 General are **line-agnostic** (Life and A&H both use them). After this split, the §2 national core and the per-state §1 regulation overlay are shared across BOTH lines, so a new state writes its regulation overlay once and both exams use it. (Life currently reuses the MA A&H §1/§2; post-refactor it points at the shared national core + MA overlay.)

## Status (national cores in `ah/national/`)
- [x] §2 General — national (100% universal; NO overlay needed — variable-products regulation sits with the Life track, not A&H; header/footer corrected 2026-06-18 to drop the dangling overlay reference)
- [x] §4 Policy Provisions — national (NAIC uniform 12 provisions; MA prompt-pay/mandates → overlay)
- [x] §5 Disability — national (~95% universal; MA definition standards → overlay)
- [x] §6 Health Plans — national + MA overlay file (the worked example)
- [x] §8 Dental — national (100% universal)
- [x] §10 Federal Tax — national (100% federal)
- [x] §3 A&H Basics — national (perils/classes/limited policies/HSA/underwriting kept; MA mandate, replacement forms, HIV/genetic cites, gag-rule cite → overlay)
- [x] §1 Regulation — national (NAIC Producer Licensing/UTPA/UCSPA model concepts + federal FCRA & 1033/1034; MA licensing values, CE hours, appointment/termination clocks, fines → overlay). Overlay built: `ah/MA/ah-MA-section-1-regulation.md`. Note: §1/§2 are line-agnostic — this MA overlay also serves the MA Life exam.
- [x] §7 Large Group — national (group mechanics + federal COBRA/ERISA/ADEA/PDA/COB/MSP; MA 110D/110G/110I continuation cluster, mini-COBRA 176J:9, merged-market rating → overlay). Overlay built: `ah/MA/ah-MA-section-7-large-group.md`.
- [x] §9 Seniors/LTC — national (federal Medicare A–D, NAIC lettered Medigap, MACRA, federal tax-qualified LTC triggers; MA waiver Medigap Core/Suppl 1/1A, 211 CMR 71/65, LTC free look c.176U, MassHealth → overlay). Overlay built: `ah/MA/ah-MA-section-9-seniors-ltc.md`.

**10 of 10 national cores complete + all MA overlays consolidated.** The A&H refactor is fully done — every module splits into a reusable national core + a MA overlay, so a new state adds only an overlay (like Life).

MA overlay files built: **§1, §3, §4, §5, §6, §7, §9** (`ah/MA/`). **§2, §8, §10 need no overlay** (100% universal). With the §3/§4/§5 consolidation (2026-06-18), every MA delta now lives in its own overlay file rather than inside the old source modules; the national cores were also scrubbed of residual MA references (§3 MassHealth/CMSP/"Massachusetts requires"; §4 the MA grace-period nonrenewal note and § 108 cite leaks). The intact `MA-16-52-section-*.md` modules remain the detailed MA source of truth and the question-bank source, but are no longer the *only* home for the MA statute layer.

**Clean-slate state for the next state:** national cores (`ah/national/`) are MA-free and reusable; MA overlays (`ah/MA/`) hold every MA statute value. A new state = copy the overlay structure, swap in that state's verified values.
