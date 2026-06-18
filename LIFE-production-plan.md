# Life Producer Exam Build Plan (MA Series 16-51) + Multi-State Architecture

## The decision (locked)
1. **Verified modules first.** Every fact the tutor teaches comes from a statute/source-verified module file, never from model memory. Same unbreakable rule as the A&H build (`CLAUDE.md`).
2. **National core + state overlay architecture.** ~80% of life/health content is national and identical across states. Build it once. Each state adds only a small regulatory overlay.

---

## Content layers

### Layer 1 — National Life core (build once, reused by all 17 states)
Source: the verified study notes in `modules/life/_source/` (KW + RN color-coded sets, green = must-know).
Output: `modules/life/national/life-section-N-*.md`

Module files now follow the **official outline section numbers** (from `16-51-content-outline.md`), not my earlier L1–L9 guess.

| Outline § | Weight | Module file | Primary source | Status |
|-----------|--------|-------------|----------------|--------|
| 3.0 Basics | 20% | life-section-3-basics.md | Basic Principles, Legal Concepts, Uses, Underwriting | ✅ done |
| 4.0 Policies | 15% | life-section-4-policies.md | Life Insurance Policies | ✅ done |
| 5.0 Provisions/Riders | 24% | life-section-5-provisions-riders.md | Provisions, Options and Riders | ✅ done |
| 6.0 Annuities | 14% | life-section-6-annuities.md | Annuities | ✅ done |
| 7.0 Federal Tax | 7% | life-section-7-federal-tax.md | Policies/Annuities/Retirement | ✅ done |
| 8.0 Qualified Plans | 6% | life-section-8-qualified-plans.md | Retirement Accounts | ✅ done |

**National core COMPLETE — all 6 modules (86% of exam by weight) drafted from verified green/must-know source notes.**

Reused from A&H (line-agnostic, verified against the outline): §1.0 Insurance Regulation (8%), §2.0 General Insurance (6%) → brings coverage to 100%.

MA overlay: `MA/life-MA-section-5-provisions.md` **done and verified** — provisions cluster (132/144/142/187H), guaranty (146B), replacement free-look **20 days** (211 CMR 34.06), accelerated benefits (211 CMR 55), group assignment (134C), retained-proceeds creditor protection (119A). Only minor flags left: group term **conversion timing** (175:134/134A) and net-single-vs-gross premium mechanics for §3.0.

## Remaining to launch-ready (Life)
1. ~~MA overlay reg pulls~~ ✅ done (211 CMR 34.06, 211 CMR 55, 175:134C, 119A)
2. ~~App integration~~ ✅ done — `SYSTEM_PROMPT_LIFE` built from the modules (`modules/life/life-system-prompt.txt`), added a Life/A&H selector + dynamic title, routed the chat prompt, gated Life flashcards as "coming soon." In both `study-buddy.html` and `index.html`. **Needs a live browser load to confirm (no JS runtime in the build env to auto-test).**
3. ~~Question bank for Life~~ ✅ done — 98 questions (L001–L098) across all 8 sections in `banks/life/`, weighted to the exam blueprint, every MA item verified-cited. See `banks/life/BANK-INDEX.md`.
4. ~~Flashcard decks for Life~~ ✅ done — `LIFE_DECKS`, 8 section decks (~86 term/def/cite cards) wired to the Flashcards tab when Life is selected, in both files; pushed.
5. Pending premium mechanics in §3.0 (net single vs gross) and group conversion timing (175:134/134A) — minor pulls
6. Optional: expand the bank from ~1x (98) toward the A&H bank's ~4x depth
7. The other 16 states — overlay-only per state, reusing national core + bank + deck structure
8. Anthony review pass for accuracy + tone

### Layer 2 — Shared regulatory/fundamentals core (already exists, line-agnostic)
These existing A&H modules apply to Life unchanged. Do NOT rewrite:
- `MA-16-52-section-1-insurance-regulation.md` — MA licensing, CE, appointments, 14 grounds, fines. Identical for any line.
- `MA-16-52-section-2-general-insurance.md` — risk/peril/hazard, stock vs mutual, domestic/foreign/alien, authority, contracts. National fundamentals; the Life "Basic Principles" source largely duplicates this.

The Life tutor's knowledge base = Layer 1 (life-specific) + Layer 2 (shared) + Layer 3 (MA overlay).

### Layer 3 — MA Life overlay (state-specific, NEEDS A SOURCE)
The national PDFs are not MA-specific. These MA life-law items must be sourced from MA statute/reg before they go in front of a test-taker:
- Free-look period (life) and replacement free-look
- Replacement of life insurance regulation (211 CMR)
- Standard nonforfeiture law, suicide clause limit, grace period, reinstatement, incontestability (MA day-counts)
- MA Life & Health Guaranty Association limits + gag rule
- Required policy provisions / readability

**Open item for you:** do you have MA life-statute source material (like the A&H statutory research), or should the overlay reuse the shared A&H regulation module plus a flagged "verify against MA statute" list? I will not fill these from memory.

---

## Multi-state rollout (after MA Life is solid)
For each new state, you only produce a Layer-3 overlay (small). Layers 1 and 2 are reused. App gets a **state + line-of-authority picker**; it composes the right knowledge base = national core + that state's overlay.

App work (separate from content):
- Add `STATE` and `LINE` selectors to the header.
- Split the single `SYSTEM_PROMPT` into composable parts: `NATIONAL_LIFE`, `NATIONAL_HEALTH`, `SHARED_REG`, and `OVERLAY[state][line]`.
- Flashcard `DECKS` keyed by state+line.

---

## Module format (locked — matches existing A&H modules)
Header line with exam weight + source + verification note; "How to study this module" blockquote; numbered Parts; a drill card of testable facts; italicized *exam trap* notes. See `modules/life/national/life-section-2-policies.md` for the worked template.

## Source color key (from the PDFs)
- **Green** = must know and study → goes in the module
- **Blue** = appeared on a quiz, not important → include only if it sharpens a distinction
- **Red** = don't need to know → skip
