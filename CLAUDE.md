# CLAUDE.md — MA Question Bank Generator

You are generating original practice questions for a Massachusetts insurance licensing exam-prep product (Prometric Series 16-52, Accident & Health producer exam). Work module by module through the study files in this folder.

## Setup expected in this folder
- `modules/` — the ten verified study modules (MA-16-52-section-*.md). These are your ONLY source of facts.
- `banks/` — output folder. One bank file per module.
- `MA-16-52-question-bank-v1.md` and `MA-16-52-question-bank-module-6.md` — existing banks (Q001–Q065). Match their format exactly and continue their ID sequence.

## The one unbreakable rule
**Every factual claim in every question, answer, and explanation must come from the module file you are working from.** If a fact isn't in the module, the question doesn't get written — no outside knowledge, no guessing, no "improving" statutes from memory. The modules are statute-verified; your job is transformation, not research. Never use or imitate content from ExamFX, Kaplan, Prometric, or any other vendor.

## Question format (locked — match existing banks exactly)
```
### Q### | [module #] | [Easy/Medium/Hard]
[Question stem]
- A) [option]
- B) [option]
- C) [option]
- D) [option]
**Answer: X** — [One-sentence explanation of why, and why it matters.]
*Citation: [statute/regulation/outline cite, copied from the module]*
```

## Per-module targets (weighted to exam percentages, 400-question total)
| Module file | New questions | ID range | Notes |
|---|---|---|---|
| section-7-large-group | 30 | Q066–Q095 | Lean on the continuation cluster (110D/110G/110I/Mini-COBRA/COBRA) |
| section-9-seniors-ltc | 30 | Q096–Q125 | Medigap Core/1/1A + MACRA trap; LTC 65.10 mechanics; NO Medicare dollar amounts |
| section-3-ah-basics | 22 | Q126–Q147 | Mandate/MCC, guaranty gag rule, MIB, HIV/genetic limits, replacement |
| section-1-insurance-regulation | 23 (tops up to 36) | Q148–Q170 | Don't duplicate Q018–Q025; mine the 14 grounds, 162T/162V/162Q, fines |
| section-4-policy-provisions | 20 (tops up to 32) | Q171–Q190 | Don't duplicate Q001–Q017; mine optional provisions, renewability, prompt-pay |
| section-2-general-insurance | 26 (tops up to 32) | Q191–Q216 | Don't duplicate the 6 in-module questions; vocabulary-pair traps |
| section-5-disability-income | 26 | Q217–Q242 | Own/any-occ scenarios, residual math, business DI matching, SSDI |
| section-10-federal-tax | 12 (tops up to 16) | Q243–Q254 | The rule of thumb + BOE inversion from every angle |
| section-8-dental | 4 (tops up to 8) | Q255–Q258 | 100/80/50, predetermination, adverse selection, integrated deductible |

## Quality rules
1. **Difficulty mix per module:** ~30% Easy (direct recall), ~45% Medium (applied scenario), ~25% Hard (trap distinctions, EXCEPT questions, multi-fact).
2. **Use all three Prometric formats:** direct question, incomplete sentence, and "all of the following EXCEPT."
3. **Hard questions live on the traps.** Each module's drill card and italicized *exam trap* notes are your hard-question seed list. Examples: weeks-vs-months (110G), petition-vs-finalization (47C), Supplement 1 vs 1A (MACRA), BOE's inverted tax treatment, earlier-birthday-not-older-parent (COB).
4. **Scenario questions use varied, realistic names and MA flavor** (Worcester, Springfield, Lowell — not always Boston). Never reuse a name within a module's bank.
5. **Wrong answers must be plausible** — preferably true statements about a DIFFERENT provision (that's how the real exam builds distractors). Never make joke options.
6. **Numbers are sacred.** Copy every day-count, percentage, and dollar figure character-for-character from the module. If you're tempted to write a number you can't see in the module file, stop and skip that question.
7. **No yearly-indexed dollar amounts** (Medicare deductibles, IRS LTC limits, mandate penalties) — test the structure instead, per the modules' own approach.
8. **One question = one testable fact.** Don't stack unrelated facts in a stem.
9. **Explanations are one sentence**, stating the rule and (when useful) the contrast that makes the wrong answers wrong.

## Workflow per module
1. Read the module file fully.
2. List the testable facts (the drill card is the skeleton; the prose adds the scenarios).
3. Check the existing banks for that module's already-written questions — do not duplicate a fact already tested unless approaching from a genuinely different angle.
4. Write the questions to `banks/MA-16-52-question-bank-module-N.md` with a header matching the Module 6 bank file.
5. End each file with the running bank total.
6. After all modules: write `banks/BANK-INDEX.md` summarizing question counts by module and difficulty, flagging any module that came up short of target and why.

## Self-check before finishing each module (do this, seriously)
- [ ] Every citation string appears verbatim somewhere in the module file
- [ ] Every number in every stem/answer appears in the module file
- [ ] No duplicate facts vs. existing banks
- [ ] Difficulty mix within ±10% of target
- [ ] All three question formats used
- [ ] IDs sequential, no gaps or repeats
