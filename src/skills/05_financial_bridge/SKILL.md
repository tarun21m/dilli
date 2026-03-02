# SKILL 05 — Financial Bridge

**Purpose:** Quantify the transformation. Entry EBITDA to exit EBITDA. Investment required. Multiple re-rating. Do-nothing trajectory modeled. Every key number triangulated with 2+ methods. No single-source numbers in this skill.

**Inputs:** All prior skills + scratchpad.reference_layer
**Writes to:** scratchpad.financial_bridge

---

## RULE: TRIANGULATION IS NOT OPTIONAL

Every key assumption requires a triangulation table:

```
METRIC: [name]
Method 1 (top-down):    [starting point] × [rate] = [result]  Source: [X, date]
Method 2 (bottom-up):   [unit count] × [unit economics]       Source: [X, date]
Method 3 (comparable):  [comparable company value] × [adj]    Source: [X, date]
Convergence: within 15% (HIGH) / within 30% (MEDIUM) / divergent (LOW)
Confidence: ●●●● / ●●●○ / ●●○○
Selected value: [final number used in bridge]
```

A bridge number without triangulation is an assertion, not analysis.

---

## RULE: MODEL DO-NOTHING BEFORE TRANSFORMATION

The investment thesis is the delta between do-nothing and transformed. Without a do-nothing baseline, there is no thesis. Do-nothing is not optional.

---

## PHASE 1 — RESEARCH PLAN

I need to build:

1. **Do-nothing baseline:**
   - Current revenue (from SKILL 01, with confidence)
   - Current EBITDA and margin (from SKILL 01, with confidence)
   - Do-nothing Y5 trajectory: what does EBITDA look like in Year 5 without transformation?
     — Cost growth: labor inflation × headcount growth from volume
     — Volume growth: market growth rate from reference layer × current unit count
     — Competitive pressure: revenue at risk from do-nothing, per failure cases
   - Current enterprise value estimate: EBITDA × entry multiple from transaction comps

2. **Bridge levers (from SKILL 03 value architecture):**
   - For each lever: Year 1 contribution, Year 3, Year 5 (full maturity)
   - For each lever: investment required and year it deploys
   - Triangulation data needed for each lever magnitude

3. **Transformed state:**
   - Revenue, EBITDA, EBITDA margin at Year 5
   - Exit multiple: what should this trade at post-transformation?
   - Exit enterprise value

4. **Investment bridge:**
   - Total investment by year (from SKILL 04)
   - When does investment turn EBITDA-positive (payback)?
   - Net value creation calculation

Search: transaction multiples for transformed comparable companies, post-transformation margin benchmarks, SaaS/software EV/EBITDA multiples for re-rating thesis, PE-backed tech transformation case financial outcomes

---

## PHASE 2 — GATHER

Collect triangulation data for every key assumption. Do not calculate the bridge in this phase — gather inputs only.

For each assumption needing triangulation:
- Collect 2-3 benchmark data points from different source types
- For multiples: actual transaction data preferred over theoretical ranges
- For margin benchmarks: post-transformation company data, not generic sector ranges
- Flag any benchmark >24 months old

---

## PHASE 3 — REASON

**STEP 1 — DO-NOTHING TRAJECTORY (model first):**

```
Do-nothing revenue (Y5): $___M
  Derivation: Current $___M × [market growth rate %/year] × [volume growth] - [competitive attrition]
  Source: [market growth from reference layer]

Do-nothing EBITDA (Y5): $___M (___% margin)
  Derivation: Current EBITDA + [volume growth impact] - [labor inflation: ___% × ___FTE × $___]
              - [competitive pricing pressure: ___% revenue erosion]
  This is the baseline the transformation must beat.
  Confidence: ●●○○ LOW (built from estimated EBITDA base)
```

**STEP 2 — BRIDGE LEVERS:**

For each lever from SKILL 03:
```
LEVER [N] — [Name from SKILL 02/03 opportunity type]:
  Year 1 contribution: $___M
  Year 3 contribution: $___M
  Year 5 contribution (full maturity): $___M
  Investment to achieve: $___M (from SKILL 04 phasing)
  Triangulation table: [3 methods + convergence + confidence]
```

**STEP 3 — BRIDGE TABLE (additive):**
```
Do-nothing EBITDA (Y5):     $___M - $___M
+ Lever 1 ([type]):          +$___M - $___M  (●●●○ confidence)
+ Lever 2 ([type]):          +$___M - $___M  (●●○○ confidence)
+ Lever 3 ([type]):          +$___M - $___M  (●●○○ confidence)
- AI Investment (annualized): -$___M - $___M
= Transformed EBITDA (Y5):   $___M - $___M
= Transformed Margin:         ___% - ___%  (vs. current ___%)
```

**STEP 4 — ENTRY AND EXIT EV:**
```
Entry EV: $___M × ___x = $___M - $___M
  Multiple source: [transaction comp + date]
  Confidence: ●●●○

Exit EV: $___M × ___x = $___M - $___M
  Multiple source: [post-transformation transaction comp + date]
  Multiple rationale: [why this multiple is justified — what changed]
  Confidence: ●●●○

EV creation: $___M - $___M
```

**STEP 5 — ASSUMPTION TABLE (every input listed):**
```
| Assumption | Value | Method | Source | Confidence |
|------------|-------|--------|--------|------------|
| [every input — no hidden assumptions] |
```

---

## PHASE 4 — VALIDATE

□ Do-nothing trajectory modeled explicitly (not skipped)?
□ Every key assumption has triangulation table with 2+ methods and sources?
□ Bridge confidence consistent with SKILL 01 data quality (LOW EBITDA base → LOW bridge)?
□ Transformed EBITDA derivable from value architecture + execution plan numbers?
□ Exit multiple benchmarked against actual post-transformation transaction comps?
□ Investment consistent with SKILL 04 phasing (not independently invented)?
□ Assumption table complete — no hidden inputs?
□ Confidence never inflated above SKILL 01 underlying data quality?
□ Payback period calculated?
□ Gaps recorded for assumptions that couldn't be benchmarked?

Then write to scratchpad.

---

## CRITICAL RULES

1. **Do-nothing first.** The thesis is the delta. A transformed EBITDA of $130M means nothing without knowing whether do-nothing EBITDA is $60M or $110M. Model do-nothing before transformation.
2. **Triangulate everything.** If you cannot find 2 triangulation methods for a key assumption, the confidence is LOW and that must be labeled clearly. A single-method number is an assertion.
3. **Confidence propagates.** If SKILL 01 EBITDA is LOW confidence, bridge numbers built on that EBITDA are at most LOW-MEDIUM. You cannot inflate confidence by performing arithmetic on uncertain inputs.
4. **Investment is a cost in the bridge.** The returns must justify the investment on net. Show this calculation explicitly.
5. **Exit multiple must be earned.** State specifically what changed that justifies a higher multiple — not "AI companies trade at higher multiples."

---

## NEGATIVE EXAMPLES

**BAD:** "Entry EBITDA is estimated at approximately $57M. With transformation, EBITDA could reach $130M by Year 5, representing significant value creation."
**GOOD:** "DO-NOTHING Y5: $48M-$65M. Derivation: current $42M-$72M base (LOW confidence, SKILL 01), +2% annual volume growth (BTR CAGR — NMHC 2025), +4% labor inflation offset by volume, -3% competitive pricing erosion annually (utility billing commoditization trend, reference layer failure case). Do-nothing EBITDA at Year 5: $48M-$65M. This is the floor we must exceed."

**BAD:** "The transformation will generate significant value creation through multiple operational levers."
**GOOD:**
```
Do-nothing EBITDA (Y5):      $48M - $65M   (●●○○ LOW)
+ Lever 1 labor automation:  +$30M - $64M  (●●●○ MEDIUM — headcount unverified)
+ Lever 2 data products:     +$20M - $35M  (●●○○ LOW-MED — attach rate unverified)
+ Lever 3 NPS/churn repair:  +$6M  - $17M  (●●○○ LOW — churn rate estimated)
- AI investment annualized:  -$11M - $16M
= Transformed EBITDA (Y5):   $93M - $165M
= Transformed Margin:         22% - 30%    (vs. current 10-14%)
Overall confidence: ●●○○ LOW-MEDIUM — EBITDA base is estimated from benchmarks
```

**BAD:** "An exit multiple of 15-20x is reasonable for a transformed software-enabled business."
**GOOD:** "EXIT MULTIPLE: 14-18x. Method A: IT/managed services post-transformation median 11.4x (Aventis Advisors Oct 2025) + 3-6x premium for >20% EBITDA margin (Viaductus 2025 premium data) = 14-17x. Method B: Revenue mix blended — 70% services at 11x + 30% software at 22x (ClearlyAcquired 2025) = 14.3x blended. Method C: Comparable exit — EXL Service transformative acquisition premium 14-16x post-margin expansion (EXL M&A history). Convergence: 14-18x range. Confidence: MEDIUM. ●●●○"
