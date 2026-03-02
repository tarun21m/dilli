# SKILL 02 — Structural Opportunity

**Purpose:** Identify what is broken or underexploited. Evaluate all five AI transformation opportunity types. Rank by EBITDA magnitude. Explain why now. Apply inversion. This is the thesis-formation skill.

**Inputs:** scratchpad.reference_layer + scratchpad.company_depth
**Writes to:** scratchpad.structural_opportunity
**Extended thinking:** ON (8,000 tokens) — required for ranking and inversion

---

## THE RULE

All five opportunity types must be evaluated. For any type not present, state why in one line.
**Silence on any type is a validation failure.**

---

## PHASE 1 — RESEARCH PLAN

Write this plan before any tool call:

I need to evaluate all five types against this company:

**TYPE 1 — COST COMPRESSION**
Where does cost scale in ways that shouldn't be structural? What % of the cost base is addressable by AI (labor automation, STP improvement, exception reduction)? What is the reference layer benchmark for cost reduction magnitude in this sector?

**TYPE 2 — DATA MONETIZATION**
What unique dataset does this company hold? What is its volume, uniqueness, and structural advantage? What would external parties pay for structured access? Are there existing data products with disclosed revenue?

**TYPE 3 — REVENUE EXPANSION**
What new customer segments or product tiers does AI enable that don't exist today? What adjacent markets become accessible? What pricing power does AI-enhanced service create?

**TYPE 4 — QUALITY / EXPERIENCE IMPROVEMENT**
What quality gaps exist (NPS, error rates, dispute rates)? What is the revenue impact of closing them (retention × ACV × churn delta)? What does the reference layer say about NPS improvement → retention impact in this sector?

**TYPE 5 — COMPETITIVE MOAT BUILDING**
Does AI create switching costs, network effects, or proprietary data advantages? Does a data flywheel exist? What does the company know after 5 years of AI operation that a new entrant cannot replicate?

**INVERSION**
What would have to be true for the top opportunity to not be real? What do reference layer failure cases say about transformation risk in this sector?

**WHY NOW**
What changed in the last 12-24 months that makes this the right moment? (Be specific — LLM cost curves, market structure change, competitive pressure, regulatory catalyst)

Additional searches: competitor AI announcements, recent adjacent company transformations, specific capability cost curves, regulatory changes

---

## PHASE 2 — GATHER

Collect evidence for each opportunity type from:
1. Company depth data (SKILL 01 scratchpad)
2. Reference layer AI transformation cases (SKILL 00 scratchpad)
3. Targeted new searches for opportunity-specific evidence

For each type being evaluated:
- Find 2+ pieces of company-specific evidence (not generic benchmarks)
- If insufficient evidence: state "Insufficient evidence to validate TYPE X for this company — see gap"
- Record source + date for every evidence item

Do not rank or reason about magnitude in this phase. Gather evidence only.

---

## PHASE 3 — REASON

Extended thinking required. Apply here.

**For each opportunity type:**

*Present:*
- What is the evidence? (specific to this company + reference layer cases)
- What is the estimated magnitude range? (with derivation — not asserted)
- What confidence level? (●●●● / ●●●○ / ●●○○ / ●○○○)

*Absent:*
- One-line rationale. Move on.

**Ranking:**
- Rank present types by estimated EBITDA impact (not by strategic interest)
- Show derivation for ranking: "TYPE 1 ranked #1 because $X-Y EBITDA vs. TYPE 3 at $A-B"
- Derivation must reference specific company data + benchmarks

**Inversion check (required — cannot be skipped):**
- State explicitly: "What kills this thesis is [specific condition]"
- This must be honest and adversarial, not boilerplate
- Answer: what would have to be true for the #1 ranked opportunity to not exist?

**Why now (required — cannot be skipped):**
- Name the specific change in last 12-24 months that opens this window
- NOT acceptable: "AI has advanced significantly"
- ACCEPTABLE: "LLM document processing reached 95%+ accuracy at $X/1000 pages in 2024 (source), making automation economically viable for the first time vs. manual at $Y/1000 pages"

---

## PHASE 4 — VALIDATE

□ All five types explicitly evaluated (present or ruled out with rationale)?
□ No type silently skipped?
□ Present types ranked by magnitude with derivation shown?
□ Each present type: evidence from company depth + reference layer?
□ Magnitude estimated with derivation chain (not asserted)?
□ Confidence notation used for each estimate?
□ Inversion check present and specific (not "execution could fail")?
□ Why now present and specific (not generic "AI is advancing")?
□ No contradiction with SKILL 01 company facts?
□ Sources recorded for all evidence?

Then write to scratchpad.

---

## CRITICAL RULES

1. **Do not default to TYPE 1.** Every company has cost reduction potential. The meaningful question is whether there are larger opportunities elsewhere. TYPE 1 should only be ranked #1 if the evidence genuinely supports it over TYPE 2-5.
2. **Magnitude over possibility.** "AI could improve NPS" is not an opportunity analysis. "$6M-$17M EBITDA from 30% churn reduction on 8M-unit base" is. Every present type needs a magnitude range.
3. **Inversion must be adversarial.** If you cannot articulate a credible way the thesis fails, you have not thought hard enough.
4. **All numbers derive from SKILL 01 + SKILL 00 data.** If you need a number not in the scratchpad, use a tool call to get it. Do not fabricate inputs.
5. **Evidence before ranking.** Do not rank first and find evidence to support the ranking. Gather evidence, then form the ranking.

---

## NEGATIVE EXAMPLES

**BAD:** "TYPE 1 — AI can reduce operational costs, which are significant for this company."
**GOOD:** "TYPE 1 — LABOR SUBSTITUTION (RANKED #1): 3,387 employees processing $12B in utility bills (SKILL 01). Industry benchmark (ARDEM April 2025): AI bill ingestion reduces manual processing FTE by 60% over 36 months in comparable BPO operations. Estimated processing headcount: 50% of total = 1,694 FTE × $70K loaded cost = $118M automatable labor pool. AI compression at 20-30% (McKinsey benchmark, reference layer): $24M-$35M EBITDA contribution. Confidence: MEDIUM — headcount breakdown unverified from public sources. ●●●○"

**BAD:** "TYPE 5 — A data flywheel may potentially exist given the company's scale."
**GOOD:** "TYPE 5 — COMPETITIVE MOAT (RANKED #2): 8M units × 20,000 providers creates consumption anomaly training data that no new entrant can replicate. After 5 years of AI operation, anomaly detection models trained on this corpus would be 10-20x more accurate than a new entrant (ML benchmark: model accuracy scales with log(training data volume) — Andrew Ng 2022). Switching cost: property managers lose 3-5 years of consumption benchmarking history. Confidence: MEDIUM — flywheel logic is sound; revenue impact from switching costs not yet quantifiable. ●●●○"

**BAD:** "Inversion: this opportunity might not materialize if the company fails to execute."
**GOOD:** "INVERSION: Thesis requires (a) automation does not cause billing errors that trigger customer churn — if error rates increase during AI rollout, the 8M-unit data moat shrinks before monetizing; (b) property managers pay a premium for predictive analytics when utility billing is currently treated as a commodity — no evidence of willingness to pay at premium pricing yet; (c) TPG provides the capital and operational expertise for tech transformation, not just financial engineering — not verified."

**BAD:** "Why now: AI technology has advanced significantly in recent years."
**GOOD:** "WHY NOW: (1) LLM document processing cost curve: GPT-4o vision processes utility bill images at $0.002-$0.008/page (OpenAI pricing 2025), vs. manual processing at estimated $0.80-$1.20/page — 100-600x cost advantage crossed 2024; (2) BTR sector has grown to 800,000+ institutional units (NMHC 2025), increasing per-client volume to levels where automation ROI is compelling; (3) Competitor Billee Technologies publicly announced AI-first billing platform (GlobeSt July 2025) — competitive window is open now, not indefinitely."
