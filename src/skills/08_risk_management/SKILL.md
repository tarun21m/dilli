# SKILL 08 — Risk Management

**Purpose:** What kills the thesis. Build this skill adversarially. You are the skeptical IC partner. Find the 3 most damaging questions before writing anything. Bear case. Compounding failure scenarios. Every risk traces to a specific prior skill finding.

**Inputs:** All prior skills + scratchpad.reference_layer
**Writes to:** scratchpad.risk_management
**Extended thinking:** ON (12,000 tokens) — required for compounding scenario logic

---

## REQUIRED SETUP: ANSWER THESE THREE QUESTIONS FIRST

Before writing the risk register, answer these honestly:

1. What is the single assumption in this thesis that, if wrong, renders everything else irrelevant?
2. What did the reference layer failure cases say that most directly applies to this company's situation?
3. What are the 3 most damaging questions a skeptical IC partner would ask — and what are the honest answers?

Write the answers. Then write the risk register.

---

## PHASE 1 — RESEARCH PLAN

I need to stress-test every prior skill finding:

**From SKILL 01 (Company Depth):**
- What assumptions about the business model or financials are LOW confidence and could be wrong?
- What data did we not find that downstream skills assumed?

**From SKILL 02 (Structural Opportunity):**
- What would have to be true for the #1 ranked opportunity to not be real?
- Where did we infer things we couldn't verify?

**From SKILL 03 (Value Architecture):**
- Which transformation magnitude estimate is most likely to be wrong?
- Which lever is most execution-dependent?

**From SKILL 04 (Execution Plan):**
- Where is the critical dependency chain most fragile?
- What causes delays in comparable implementations?

**From SKILL 05 (Financial Bridge):**
- What single assumption, if wrong by 30%, breaks the investment thesis?
- If do-nothing degrades faster than modeled, what does the floor look like?

**From SKILL 00 (Reference Layer):**
- What do failure cases say about this specific type of company and transformation?
- What warning signs appeared in those cases that we already see here?

Additional searches: recent negative news, litigation or regulatory action, key person departures, competitive moves, customer contract structures that could limit transformation speed

---

## PHASE 2 — GATHER

Collect:
- Negative signals not yet captured: BBB/Trustpilot patterns, litigation filings, regulatory actions, key executive departures
- Reference layer failure case specifics — map each to this company's situation explicitly
- Competitive threat data: new entrants, incumbent platform moves, pricing pressure
- Any new signals since SKILL 01 was completed

Do not sanitize. Look for what's wrong, not what confirms the thesis.

---

## PHASE 3 — REASON

Extended thinking required for compounding scenario.

**RISK REGISTER (minimum 5 risks):**

For each risk:
```
[R__] Risk name: [specific description — not "execution risk"]
Traces to: SKILL __ finding: "[specific quote or number from prior skill]"
Likelihood: HIGH / MEDIUM / LOW — [one-line rationale with evidence basis]
Impact: HIGH / MEDIUM / LOW — [quantified if possible: "$X-Y bridge impact if this materializes"]
Mitigation: [specific and actionable — not "monitor closely" or "manage carefully"]
```

**COMPOUNDING SCENARIO (required):**

Build a causal chain of 3+ risks triggering each other:
```
[R__] occurs because [specific condition]:
  → [specific consequence]
  → which triggers [R__] because [specific logic]
  → [specific consequence]
  → which triggers [R__] because [specific logic]
  → Outcome: [thesis failure statement with financial specificity]

Timeline to irreversibility: [at what point has the investment thesis definitively failed?]
Correction window: [how long does the investor have to intervene before irreversibility?]
```

The "because" logic is mandatory. A list of risks is not a compounding scenario.

**FLOOR CASE (required — must be a number, not a narrative):**
```
Bear case assumptions:
  [Assumption 1]: [stressed value] vs. [base case value] — [reason for stress]
  [Assumption 2]: [stressed value] vs. [base case value] — [reason for stress]
  [Assumption 3]: [stressed value] vs. [base case value] — [reason for stress]

Floor Y5 EBITDA: $___M
  Derivation: [do-nothing EBITDA] + [stressed lever 1] + [stressed lever 2] - [investment]

Floor exit multiple: ___x
  Rationale: [underperforming comparable multiple — source + date]

Floor EV: $___M

Still investable at floor?
  Entry EV estimated: $___M - $___M (from SKILL 05)
  Floor EV: $___M
  Assessment: [YES if floor EV > entry / NO if floor EV < entry / MARGINALLY if within 10%]
  At what entry price is the floor case investable? $___M
```

**MOST LIKELY FAILURE MODE:**

Single sentence. The most probable way this thesis underperforms rather than fails. Name it explicitly. Not generic — specific to what this analysis found.

---

## PHASE 4 — VALIDATE

□ Three IC partner questions answered honestly before risk register written?
□ Every risk traces to a specific prior skill finding (not generic)?
□ Risk register has 5+ risks with likelihood + impact + mitigation?
□ No generic risks — each is specific to this company's situation?
□ Compounding scenario builds logically sound causal chain of 3+ risks?
□ "Because" logic present at each step of compounding scenario?
□ Floor case is a number, not a narrative?
□ Floor case built from stressed version of SKILL 05 bridge (not independently invented)?
□ Reference layer failure cases explicitly referenced and mapped?
□ Most likely failure mode named explicitly?
□ Sources for new data gathered in Phase 2?

Then write to scratchpad.

---

## CRITICAL RULES

1. **Every risk must trace to a prior skill finding.** "Competition is always a risk" is not acceptable. "SKILL 02 identified Billee Technologies (GlobeSt July 2025) building the exact NLP billing transparency product that addresses Conservice's primary NPS complaint vector — this is the competitive risk" is.
2. **Compounding scenario requires causation, not correlation.** R1 causes R2 because [specific logic]. R2 causes R3 because [specific logic]. Without the causal logic, it is not a scenario — it is a list.
3. **Floor case is a financial statement.** "$64M Y5 EBITDA at 8x = $512M EV vs. $564M estimated entry EV — marginally impaired at midpoint entry price" is a floor case. "Results could be worse than expected" is not.
4. **Reference layer failure cases are not optional.** If the reference layer has failure cases for this sector, they must appear in SKILL 08. They exist precisely to inform this risk analysis.
5. **Mitigation must be actionable.** "Monitor execution closely" is not a mitigation. "Pre-Wave 1 data quality audit with 85% data quality threshold as Wave 1 go/no-go gate" is.

---

## NEGATIVE EXAMPLES

**BAD:** "Execution risk is significant, as with all large-scale transformation programs."
**GOOD:** "[R1] EXECUTION SEQUENCING FAILURE: SKILL 04 identified data infrastructure build as the critical Wave 1 dependency — anomaly detection models cannot train until data pipeline is built, which cannot be done until data quality baseline is established. Reference layer failure case: RPA rollout delayed 8 months at comparable BPO operator due to unstructured legacy data quality issues (reference layer, EXL 2021 case). At Conservice's estimated $422.7M-$515.6M revenue, 6-month Wave 1 delay shifts Wave 2 ROI emergence from Year 2-3 to Year 3-4. NPV impact at 7% cost of capital: $15-25M. Likelihood: MEDIUM (legacy billing systems historically have data quality issues). Impact: HIGH ($15-25M NPV, plus deferred moat-building). Mitigation: pre-Wave 1 data quality audit; set 85% data quality score as explicit gate criterion before Wave 1 capital deployment."

**BAD:** "If execution underperforms, the investment returns may be lower than expected."
**GOOD:** "FLOOR CASE: Bear assumptions: (A) Wave 1 delayed 6 months — data quality issues (Likelihood: MEDIUM, precedented in sector); (B) Lever 1 delivers 50% of base case ($15M-$32M vs. $30M-$64M) — automation slower than benchmarks due to billing system complexity; (C) Lever 2 (data products) pushed entirely past the hold period — no Year 4 contribution; (D) NPS repair stalls at 0 (litigation overhang unresolved). Floor Y5 EBITDA: $48M (do-nothing) + $22M (Lever 1 at 50%) + $0 (Lever 2) + $5M (Lever 3 partial) - $11M (investment) = $64M. Floor exit at 8x (underperforming managed services, Aventis Oct 2025): $512M EV. Entry EV estimated midpoint: $564M. Floor EV $512M < midpoint entry EV $564M — marginally impaired. Investable if entry price <$450M. Not investable above $600M entry. Entry price is the primary risk management lever."

**BAD:** "COMPOUNDING SCENARIO: If execution fails, data quality issues emerge, and key talent leaves, the transformation could take longer and deliver less value."
**GOOD:** "COMPOUNDING SCENARIO: [R1] Data quality delays Wave 1 by 6 months → [R3] Chief AI Officer departure (SKILL 07 identified this as unfilled role; 6-month delay with no early wins creates recruitment stigma) because experienced AI leaders avoid transformations showing no traction → [R4] Competitor Billee Technologies launches NLP billing product (SKILL 02 WHY NOW section) and captures the customer transparency narrative before Conservice's Wave 1 completes because Billee can move faster without a legacy stack → Outcome: Conservice loses the opportunity to be first-mover on TYPE 4, meaning NPS repair lever ($6-17M) is permanently impaired, reducing bridge by $6-17M and removing the TYPE 5 moat-building narrative. Timeline to irreversibility: 18 months from now if Wave 1 does not show measurable progress."
