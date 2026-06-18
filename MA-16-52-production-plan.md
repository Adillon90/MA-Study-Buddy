# MA Series 16-52 — Full Curriculum Production Plan
**The flight plan for getting the Massachusetts A&H course launch-ready. 10 modules = 100 exam questions of coverage. Two are done; this maps the other eight to their sources so each one is a fill-in-the-template job, not a research project.**

---

## Status Board

| # | Section | Weight | Status | Content type |
|---|---|---|---|---|
| 1.0 | Insurance Regulation | 9% | ✅ DONE (4 items pending verification) | Mostly MA statute |
| 2.0 | General Insurance | 8% | ✅ DONE | ~100% universal |
| 3.0 | A&H Insurance Basics | 11% | ✅ DONE (pending items flagged) | ~70% universal + MA layer |
| 4.0 | Policy General Rights | 8% | ✅ DONE | MA statute (NAIC uniform law) |
| 5.0 | Disability Income | 8% | ✅ DONE | ~85% universal |
| 6.0 | Health Insurance Plans | 20% | ✅ DONE (176O day-counts pending) | ~60% universal + big MA layer |
| 7.0 | Large Group Health | 15% | ✅ DONE (176J:9 durations pending) | ~70% universal/federal + MA layer |
| 8.0 | Dental Insurance | 2% | ✅ DONE | ~100% universal |
| 9.0 | Senior Citizens / LTC | 15% | ✅ DONE (Medigap OE mechanics pending) | Federal (Medicare) + MA regs |
| 10.0 | Federal Tax Considerations | 4% | ✅ DONE | 100% federal/universal |

**Coverage: 100/100 exam questions — ALL TEN MODULES DRAFTED (June 2026). Question bank: 25 questions (target: 400+).**

## Remaining to launch-ready
1. **Verification sweep** — close every "Pending Verification" flag across all modules (one focused session of statute/reg pulls)
2. **Anthony review pass** — read-through of all ten modules for accuracy and tone
3. **Question bank expansion** — 25 → 400+ (≈40 per module, weighted by exam %)
4. **Annual-refresh items** — Medicare dollar amounts, IRS LTC limits, MA mandate penalties (tie to fall CMS/IRS/Connector announcements)

---

## Module-by-Module Source Map

### 2.0 General Insurance (8%) — universal
Risk concepts, insurer types, agency law, contract elements. Source: your existing general content + NAIC consumer materials. MA touch: regulation of variable products (211 CMR 95) — one paragraph.

### 3.0 A&H Basics (11%) — universal core + MA layer
Universal: perils, loss/benefit types, policy classes, limited policies, MSAs/HSAs, underwriting sources (MIB, APS), replacement concepts.
MA layer to pull: limited-policy notice rules; marketing requirements (211 CMR 40.00); outline of coverage (211 CMR 42.09); HIV consent (211 CMR 36.05); genetic information (175:108H, 108I); replacement rules (175:110(N)(3)(a); 211 CMR 42.08, 42.11); **MA individual mandate** — minimum creditable coverage (c. 111M; 956 CMR 5.00) — an MA-only concept ETS/national prep books underweight.

### 5.0 Disability Income (8%) — mostly universal
Own-occ vs any-occ, elimination/benefit periods, partial/residual, AMB/SIS riders, group STD/LTD, business DI, Social Security disability (SSA source), workers comp basics. MA touch: minimum benefit standards and definition-of-disability regs (211 CMR 42.05(1)(g)).

### 6.0 Health Insurance Plans (20%) — THE BIG ONE
Universal: plan concepts, HMO/PPO/indemnity mechanics, HIPAA, utilization management, cost containment.
MA layer to pull (citations straight from the outline):
- Dependent eligibility cluster: child to 26 (175:108(2)(a)(3); 175:110(P); 176A:8BB; 176B:4BB; 176G:4T); disabled adult children; **newborn coverage** (175:47C; 176A:8B; 176G:4); adopted children
- Open enrollment / eligibility (176J(4))
- **Internal & external appeal rights** (176O:12–14; Bulletins 2016-02) — managed care patient protections
- Cost transparency tools (176O:23; Bulletin 2013-10)
- ACA layer (federal, public domain): guaranteed issue/renewability, preventive care, EHBs, premium tax credits
- **Mental Health Parity**: federal MHPAEA + MA parity statutes (175:47B; 176A:8A; 176B:4A; 176G:4M; Bulletin 2013-02)

### 7.0 Large Group Health (15%) — federal/universal + MA layer
Universal/federal: group characteristics, COB, COBRA, ERISA, ADEA, Civil Rights/Pregnancy Discrimination, Medicare secondary rules, funding types (DOL/IRS sources, public domain).
MA layer: eligibility (175:110); **MA mini-COBRA / continuation** (175:110D, 110G, 110I); small employer definition and rating rules (176J:1; 211 CMR 66.04–66.08); nondiscrimination statutes (175:108C etc.).

### 8.0 Dental (2%) — universal
Two exam questions. Indemnity plans, benefit categories, predetermination. An afternoon.

### 9.0 Senior Citizens & LTC (15%) — federal + MA regs
Federal (public domain, CMS "Medicare & You"): Parts A/B/C/D eligibility, enrollment, cost-sharing.
MA layer: **Medicare supplement is where MA is weird** — MA uses its own standardized Medigap plans (Core, Supplement 1) instead of the national A–N lettered plans (c. 176K; 211 CMR 71). National prep content gets this WRONG for MA; ours won't.
LTC: 211 CMR 65.00 — benefit triggers, inflation protection offer, nonforfeiture offer, 'Your Options for Financing Long-Term Care' disclosure, unintentional lapse protection, MassHealth interaction.

### 10.0 Federal Tax (4%) — federal/universal
IRS publications: personally-owned DI (premiums not deductible, benefits tax-free), employer-paid (deductible to employer, benefits taxable), sole prop/partner/LLC medical deduction, key person rules.

---

## Build Order (recommended)
1. **6.0** — biggest weight, biggest MA layer, anchors the course
2. **9.0** — second-biggest MA divergence (Medigap Core/Supplement 1; LTC regs)
3. **7.0** — mini-COBRA + small group rules
4. **3.0** — marketing/replacement regs + individual mandate
5. **5.0, 2.0, 10.0, 8.0** — fast universal fills
6. Verification pass: close the four pending items in 1.0; spot-check every bolded number against current statute
7. Question bank expansion to 400+ (≈40 per module, weighted by exam %)

## Production Notes
- **Workflow per module:** outline section → pull cited statutes/regs (malegislature.gov, 211 CMR via mass.gov, federal pubs) → draft module in template → original questions → Anthony review pass.
- **Template (locked):** weights header → plain-language provisions with bolded testable numbers → MA-specific rules → drill card → practice questions → sources + review date.
- **Question bank format (locked):** ID | module | difficulty | 4 options | answer | explanation | citation — parseable to JSON for the app.
- **Annual review:** every module footer carries a next-review date (June 2027). Statute changes get caught on outline re-pulls.
- **Reuse:** when MA is done, the universal modules (2, 5, 8, 10, and the cores of 3, 6, 7, 9) port to the next state at ~70% complete. State #2 should take a third of the time.
