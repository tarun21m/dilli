# SKILL 03 — Value Architecture

**Purpose:** Define what the transformed company looks like with enough specificity that a financial bridge can be built from it. Translate SKILL 02 opportunity types into target operating model metrics, horizon structure, and re-rating thesis.

**Inputs:** scratchpad.company_depth + scratchpad.structural_opportunity + scratchpad.reference_layer
**Writes to:** scratchpad.value_architecture
**Extended thinking:** ON (8,000 tokens)

---

## PHASE 1 — RESEARCH PLAN

For each confirmed opportunity type from SKILL 02, I need to establish:

1. **What does the transformed state look like concretely?**
   - Specific KPIs: EBITDA margin, FTE count, STP rate, revenue mix, revenue/employee
   - Reference: what do comparable companies look like after completing a similar transformation?

2. **For TYPE 1 (cost compression) if confirmed:**
   - Post-automation FTE count and STP rate
   - New revenue/employee ratio vs. current
   - What functions automate in H1 (Year 1-2) vs. H2 (Year 3-5)?

3. **For TYPE 2 (data monetization) if confirmed:**
   - Specific data product: what does it do, who buys it, at what price?
   - Comparable product pricing from reference layer or new search
   - Addressable customer base count × estimated attach rate → revenue range

4. **For TYPE 3 (revenue expansion) if confirmed:**
   - New segment, tier, or geography — bounded and specific
   - What did comparable peers achieve adding this capability? Timeline and magnitude?

5. **For TYPE 4 (quality/experience) if confirmed:**
   - Target NPS or error rate — what do best-in-class peers achieve?
   - NPS improvement → churn reduction → retained revenue calculation

6. **For TYPE 5 (competitive moat) if confirmed:**
   - Year 1, Year 3, Year 5 moat depth — measurable indicators
   - What switching cost is created and how is it quantified?

7. **Re-rating thesis:**
   - What multiple does the transformed business deserve?
   - What do comparable post-transformation transactions show?

Search: post-transformation operating metrics for comparable companies, data product pricing in this sector, NPS → churn benchmarks, re-rating transaction comps

---

## PHASE 2 — GATHER

Collect transformation benchmarks. No analysis yet.

For each confirmed opportunity type:
- Find 1-2 companies that completed a similar transformation (from reference layer first, then new search)
- Record: pre-transformation state, post-transformation state, timeline, magnitude achieved
- Source and date every data point

For data products and new revenue streams:
- Find comparable product pricing in this sector or directly adjacent
- Find comparable attach rates or penetration rates
- Source and date

For re-rating:
- Find 3+ comparable post-transformation transaction multiples
- Source (deal announcements, PE firm announcements, market reports) and date

---

## PHASE 3 — REASON

Extended thinking required.

**HORIZON STRUCTURE (required):**

H1 (Year 1-2): Foundation and deployable wins
- What is achievable on existing systems with Wave 1 investment only?
- What metrics move in 24 months? (be specific — STP rate, error rate, early cost savings)
- Risk profile: lower (foundation-building), but demonstrates transformation feasibility

H2 (Year 3-5): Full transformation
- What requires the infrastructure built in H1?
- What are the exit-state metrics?
- Risk profile: higher execution dependency, but thesis-defining
- **Confidence ceiling on H2 impact numbers: MEDIUM ●●●○ maximum**, unless benchmark evidence specifically supports the 5-year time horizon. H2 estimates carry inherently higher execution uncertainty than H1 and cannot be labeled HIGH regardless of H1 evidence quality.

**FOR EACH INITIATIVE, require this chain:**

```
Capability: [what AI capability is being deployed]
Lever: [what operational change this drives]
EBITDA Impact: [specific calculation]
```

Example:
```
Capability: AI bill ingestion and anomaly detection engine
Lever: Replaces manual review step in billing workflow, reducing processing FTE by 40-60%
EBITDA Impact: 1,694 FTE × 50% automation rate × $70K loaded cost × 30% = $35M
```

**TRIANGULATION REQUIREMENT — for each major impact number:**
- Method A: Bottom-up (FTE × cost × reduction % from benchmark)
- Method B: Benchmark case (comparable company achieved X% improvement → applied to this cost base)
- Method C: Top-down (sector median post-transformation margin − current margin × revenue)
Show all three, state whether they converge.

**RE-RATING THESIS:**
Current entry multiple: [X]x EBITDA (from reference layer transaction comps)
Post-transformation exit multiple: [Y]x EBITDA (justified by comparable post-transformation deals)
What specifically drives the re-rating? (higher margin, software revenue mix, lower labor intensity, moat evidence)
Source each comparable transaction.

**Reference SKILL 02 explicitly:**
"As identified in SKILL 02, TYPE 1 presents $X-Y EBITDA opportunity at MEDIUM confidence..."
Do not re-derive what SKILL 02 established. Build on it.

**DO NOT introduce new opportunities here.**
If a new opportunity surfaces during research, add a gap note. New opportunities belong in SKILL 02, not here. This skill translates confirmed opportunities into target state metrics — it does not expand the opportunity set.

---

## PHASE 4 — VALIDATE

□ Every initiative references a confirmed SKILL 02 opportunity type?
□ Every initiative shows capability → lever → EBITDA chain explicitly?
□ EBITDA impact triangulated (2+ methods) for each major initiative?
□ H1 and H2 horizons defined with distinct metrics and risk profiles?
□ Target operating model specific enough to build a financial bridge from?
□ Re-rating thesis benchmarked against actual transaction comps (not assumed)?
□ No new opportunities introduced that were not in SKILL 02?
□ No contradiction with SKILL 01 or SKILL 02 findings?
□ Confidence scores consistent with SKILL 01 underlying data quality?
□ Gaps recorded for assumptions that couldn't be benchmarked?

Then write to scratchpad.

---

## CRITICAL RULES

1. **Specific enough to build from.** "Higher margins through AI" is not a value architecture. "22-30% EBITDA margin by Year 4-5, derived from three methods converging at that range" is.
2. **H1 must be achievable without H2 infrastructure.** If an H1 initiative requires data infrastructure that only gets built in Wave 2, it belongs in H2.
3. **Capability → Lever → EBITDA chain is mandatory.** Every initiative without this chain is not an architecture — it is a wish list.
4. **Do not re-derive SKILL 02.** SKILL 02 sized the opportunities. SKILL 03 defines what the transformed state looks like. These are different questions.
5. **Triangulate every major impact number.** Single-method EBITDA improvement claims are not credible in PE diligence.

---

## NEGATIVE EXAMPLES

**BAD:** "The transformed company will have significantly higher margins due to AI-driven efficiency improvements across operations."
**GOOD:** "H2 TARGET (Year 4-5): EBITDA margin 22-30% (vs. current estimated 10-14%). Method A: Post-automation BPO analog — EXL Service post-AI transformation EBITDA margin 24% vs. 16% pre-transformation (EXL 2023 annual report). Method B: Bottom-up — labor at 65% of OpEx, 30% compression = 19.5% OpEx savings on 85% margin-after-COGS basis → 10-14% + 10-12% improvement = 22-26% target. Method C: SaaS/services blended — 30% software revenue at 75% GM + 70% managed services at 35% GM = 26% blended. Convergence: 22-30% range. Confidence: MEDIUM. ●●●○"

**BAD:** "Data products could potentially generate significant new revenue streams if successfully launched."
**GOOD:** "H2 — DATA PRODUCTS (TYPE 2): $35M-$55M incremental revenue by Year 4. Method A: Addressable base: 20,000 property managers × 10% estimated attach = 2,000 customers × $1,500/month average = $36M. Method B: Comparable pricing — Urjanet/Arcadia utility intelligence product $500-$2,000/account/month (reference layer, Crunchbase 2021). Method C: Comparable revenue — Urjanet acquired at $20M+ ARR with ~500 commercial customers = $40K ARR/customer; at 2,000 customers = $80M ceiling; 50% penetration = $40M. Convergence: $35-55M range. Confidence: LOW-MEDIUM (attach rate unverified). ●●○○"
