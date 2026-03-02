# SKILL 09 — Final Validation

**Purpose:** Cross-block consistency check on the complete scratchpad. LLM-as-judge quality scoring. Final gate before memo output. Produce a clear GO / CONDITIONAL GO / NO-GO recommendation with explicit rationale.

**Inputs:** Complete scratchpad (all prior skills)
**Writes to:** scratchpad.validation_report
**Extended thinking:** ON (8,000 tokens)

---

## PHASE 1 — RESEARCH PLAN

I need to inspect the complete scratchpad for:

1. **Consistency breaks:** Does any downstream skill finding contradict an upstream skill finding?
2. **Confidence drift:** Does any skill assign higher confidence than the underlying data from prior skills supports?
3. **Source independence:** Are any conclusions built on what turns out to be a single source cited multiple times?
4. **Gap registry completeness:** Are all known gaps from all skills in the gap registry?
5. **Triangulation completeness:** Do all calculated numbers in SKILL 05 show triangulation tables?
6. **Derivation chains:** Do all estimates in all skills show explicit derivation?
7. **Generic language:** Is any generic language remaining in the output?

No tool calls required for this skill unless a specific claim needs external verification.

---

## PHASE 2 — GATHER (internal inspection)

Read every prior skill output from the scratchpad and check these cross-block relationships:

```
SKILL 02 opportunities ← traceable to SKILL 01 company facts?
SKILL 03 transformation targets ← consistent with SKILL 02 opportunity sizing?
SKILL 04 wave sequence ← covers all SKILL 03 initiatives?
SKILL 05 bridge levers ← derivable from SKILL 03 + SKILL 04 numbers?
SKILL 05 investment ← consistent with SKILL 04 phasing?
SKILL 06 tech decisions ← consistent with SKILL 04 execution sequence and timeline?
SKILL 07 workforce numbers ← consistent with SKILL 01 headcount data?
SKILL 07 hiring priorities ← consistent with SKILL 04 critical dependency chain?
SKILL 08 risks ← trace to specific prior skill findings?
SKILL 08 floor case ← consistent with stressed version of SKILL 05 bridge?
SKILL 08 mitigations ← consistent with SKILL 06 tech strategy and SKILL 07 talent plan?
```

For each relationship: confirm consistent, or flag the inconsistency.

---

## PHASE 3 — REASON

**LLM-AS-JUDGE SCORING:**

Score each skill 1-5 on three dimensions:
- **Specificity** (5 = numbers throughout, no generic language; 1 = no numbers, all adjectives)
- **Evidence** (5 = every claim cited and triangulated; 1 = assertions without sources)
- **Consistency** (5 = no contradictions with other skills; 1 = multiple contradictions)

For any skill scoring below 4: explain exactly what is missing.
For any skill scoring below 3: flag for human review and recommend revision.

**CONSISTENCY CHECK (explicit for each relationship):**

```
[SKILL X] states [claim A].
[SKILL Y] states [claim B].
Status: CONSISTENT / INCONSISTENT
If inconsistent: which is better supported? Recommended resolution.
```

Do not summarize. Check each relationship above one by one and state the result.

**CONFIDENCE DRIFT CHECK:**

The rule: confidence in a downstream skill cannot exceed confidence in the upstream data it depends on.

```
SKILL 01 established [metric] as [confidence level].
SKILL 05 uses this metric to derive [bridge output] at [confidence level].
Drift present? YES / NO
If YES: which skill's confidence must be reduced?
```

Common drift patterns to check:
- SKILL 01 EBITDA is LOW → SKILL 05 bridge cannot be MEDIUM or HIGH overall
- SKILL 02 opportunity magnitude is LOW → SKILL 03 transformation target cannot be HIGH
- SKILL 04 investment estimate is MEDIUM → SKILL 05 investment line item must be MEDIUM

**GAP REGISTRY REVIEW:**

Are all gaps from all skills in the scratchpad gap registry?
Are any gaps with HIGH impact on thesis not yet surfaced?
For each HIGH-impact gap: is it adequately flagged for the memo reader?

**FINAL FLAGS FOR HUMAN REVIEW:**

List every item requiring human attention:
```
[FLAG 1] LOW confidence claim affecting investment decision: [specific claim + skill + why it matters]
[FLAG 2] Unresolved contradiction: [specific claim A vs. claim B]
[FLAG 3] HIGH-impact gap: [what's missing + why it matters to the thesis]
```

**RECOMMENDATION:**

```
GO — All sections pass. No unresolved HIGH-impact inconsistencies.
     Confidence distribution is acceptable for preliminary investment framework.
     [State what a reader can rely on and what they should verify]

CONDITIONAL GO — Warnings present but not thesis-breaking.
     [List specific conditions that must be resolved before final investment decision]
     [Be explicit: "Condition 1: VDD access to confirm EBITDA within 20% of estimate"]
     [Not: "Further diligence required"]

NO-GO — Hard failures present.
     [State the specific failure: data quality too thin, unresolved contradiction,
      fundamental thesis inconsistency]
     [State what would need to change to reach CONDITIONAL GO]
```

---

## PHASE 4 — VALIDATE

□ All prior skills have outputs in scratchpad?
□ All cross-block relationships checked explicitly (not summarized)?
□ LLM-as-judge scoring complete for all skills with explanation for below-4 scores?
□ Consistency check confirms or flags each major cross-block relationship?
□ Confidence drift check complete — no inflated downstream confidence found (or flagged if found)?
□ Gap registry complete and all HIGH-impact gaps surfaced?
□ Final flags listed with enough specificity for human action?
□ Recommendation is GO / CONDITIONAL GO / NO-GO with explicit, actionable rationale?
□ LOW confidence items listed for human review?

Then write to scratchpad.

---

## CRITICAL RULES

1. **Check, don't summarize.** This skill cannot say "everything looks generally consistent." It must check each cross-block relationship and state the result. Summaries without checks are not validation.
2. **Confidence drift is the most common failure.** If SKILL 01 couldn't verify EBITDA (LOW confidence) and SKILL 05 calls the bridge MEDIUM confidence overall — that is a drift failure that must be caught here.
3. **Recommendation must be actionable.** "CONDITIONAL GO — conditions: (a) management interview to confirm AI roadmap; (b) VDD access to P&L within 20% of SKILL 01 estimate; (c) legal diligence on BBB/regulatory exposure" is actionable. "More diligence recommended" is not.
4. **LOW confidence items must be listed.** The memo reader needs to know what they can rely on and what requires verification before acting on this analysis.
5. **Contradictions between skills are not failures — they are information.** The validation report exists to surface them, not to adjudicate them. State which is better supported and let the reader decide.

---

## NEGATIVE EXAMPLES

**BAD:** "The analysis is generally consistent across all skills and the investment thesis appears sound with appropriate caveats."
**GOOD:**
```
CONSISTENCY CHECK — SKILL 02 × SKILL 05:
SKILL 02 TYPE 1 opportunity: $30M-$64M EBITDA at MEDIUM confidence.
SKILL 05 Lever 1: $30M-$64M — same range. CONSISTENT.

CONSISTENCY CHECK — SKILL 01 × SKILL 05:
SKILL 01 EBITDA: estimated $42M-$72M at LOW confidence (●●○○).
SKILL 05 bridge: "overall confidence LOW-MEDIUM."
Status: BORDERLINE — bridge confidence should not exceed LOW given EBITDA base.
Recommended: SKILL 05 overall confidence should be ●●○○ LOW, not LOW-MEDIUM.

CONSISTENCY CHECK — SKILL 08 × SKILL 05 (floor case):
SKILL 05 do-nothing Y5: $48M-$65M.
SKILL 08 floor case Y5: $64M EBITDA.
SKILL 08 floor ($64M) falls within SKILL 05 do-nothing range ($48M-$65M).
Status: CONSISTENT — floor case is essentially the do-nothing case with partial lever benefit.
```

**BAD:** "Recommendation: GO — the analysis supports a positive investment thesis with standard diligence caveats."
**GOOD:**
```
RECOMMENDATION: CONDITIONAL GO.

Conditions before final investment decision:
1. VDD access to confirm EBITDA within 20% of $57M midpoint estimate.
   The bridge is built on a LOW-confidence EBITDA floor — if actual EBITDA is below $35M,
   the floor case becomes impaired. This single data point changes the thesis materially.

2. Management interview to confirm AI roadmap and data infrastructure plans.
   SKILL 06 identified no evidence of ML capability in current org.
   If management has no AI roadmap, TYPE 2 and TYPE 5 opportunities are speculative.

3. Legal diligence on BBB complaints and any pending regulatory action.
   SKILL 08 R4 flags 561 BBB complaints as HIGH-impact on NPS repair lever ($6-17M).
   If there is active litigation, the litigation overhang suppresses NPS improvement
   regardless of product investment.

Without these three resolved: EBITDA bridge confidence remains ●●○○ LOW,
and the $0.9B-$2.3B EV creation range is illustrative only, not decision-grade.

With these resolved: analysis supports preliminary investment framework for further
underwriting. The structural opportunity identification (SKILL 02) and financial
bridge framework (SKILL 05) are directionally sound.
```
