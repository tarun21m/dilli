# SKILL 04 — Execution Plan

**Purpose:** How to get from current state to transformed state. Sequencing, dependency logic, early wins, investment phasing. Grounded in reference layer implementation benchmarks — not invented timelines.

**Inputs:** scratchpad.value_architecture + scratchpad.structural_opportunity + scratchpad.reference_layer
**Writes to:** scratchpad.execution_plan

---

## PHASE 1 — RESEARCH PLAN

I need to define:

1. **Early wins (M0-M6):**
   - What is deployable on existing systems without Wave 2 infrastructure?
   - Must produce measurable output signal within 6 months
   - Must build organizational confidence without requiring major data migration

2. **Wave structure (W1/W2/W3):**
   - Which initiatives belong in each wave?
   - What gates each wave transition (specific milestone criteria)?
   - What are the dependencies between waves?

3. **Critical dependency chain:**
   - What single sequence cannot be broken?
   - If step X delays by 6 months, what cascades?

4. **Investment phasing:**
   - When does money deploy? (year by year)
   - When do returns emerge? (payback period)
   - Benchmarked against reference layer transformation cases

5. **Team requirements per wave:**
   - What roles are needed in W1 that don't exist today?
   - What cannot start without those hires?

Search: implementation timelines for comparable transformations in this sector, wave structure case studies, AI deployment benchmarks, data migration complexity estimates

---

## PHASE 2 — GATHER

Collect implementation benchmarks from reference layer and targeted new searches.

For each comparable transformation case in reference layer:
- Timeline from decision to first production system
- Wave/phase structure used and rationale
- Investment deployed by phase
- Common delay causes and their timeline impact

For sector-specific technology implementations:
- Typical integration timelines for the stack type identified in SKILL 01
- Data migration complexity and realistic timeline for this data volume
- Change management timeline for workforce transformation at this org scale

Record every benchmark with source + date.
Flag gap when comparable implementation data is not findable.

---

## PHASE 3 — REASON

**EARLY WINS (M0-M6):**

List 2-4 specific initiatives that:
- Require only existing data and existing systems
- Produce measurable output within 6 months
- Build organizational proof that transformation is real
- Are not blocked by any Wave 2 dependency

For each early win: describe initiative, expected metric improvement, and why it is deployable now.

**WAVE STRUCTURE:**

```
Wave 1 ([start]-[end], e.g., M0-M18):
  Initiatives: [list specific initiatives]
  Dependencies: [what must be in place before W1 can start]
  Gate criteria: [specific measurable outcome that triggers W2 go-ahead]
    — NOT "when leadership is satisfied" — a number: e.g., "STP rate >55%" or "pilot error rate <2%"
  Investment: $X-Y million
  Key hires required: [roles needed before or during W1]

Wave 2 ([start]-[end]):
  Initiatives: [builds on W1 foundation]
  Dependencies: [specific W1 outputs required]
  Gate criteria: [what triggers W3]
  Investment: $X-Y million

Wave 3 ([start]-[end]):
  Initiatives: [full transformation capability]
  Dependencies: [W1 + W2 outputs required]
  Investment: $X-Y million
```

**CRITICAL DEPENDENCY CHAIN:**

The sequence that cannot be broken:
```
[Step 1] must precede [Step 2] because [specific reason]
[Step 2] must precede [Step 3] because [specific reason]
If [Step 1] delays by 6 months: [downstream impact with timeline specificity]
```

**INVESTMENT PHASING TABLE:**
```
Year 1: $___M  (what this funds specifically)
Year 2: $___M  (what this funds specifically)
Year 3: $___M  (what this funds specifically)
Year 4: $___M  (what this funds specifically)
Total:  $___M
Payback: ___ months from [Wave 1 gate / full deployment]
```

**TEAM READINESS CHECK (before finalizing each wave):**

Before locking each wave plan, confirm:
- Every critical hire from SKILL 07 that is a dependency for this wave is calendared before the wave start date
- If a key role (e.g., Chief AI Officer) has a 4-6 month time-to-hire, work backwards from Wave 1 start — the hire process must begin at close, not after
- A wave cannot be finalized if a mandatory leadership hire is unscheduled

```
Role gating Wave [N]: [Role]
Hire window: [time-to-hire months]
Must begin: [date relative to close]
If delayed by 3 months: [cascade consequence to wave start date]
```

Triangulate investment with:
- Method A: % of revenue benchmark for tech transformation in this sector
- Method B: comparable company transformation total cost (from reference layer)
- Method C: bottom-up sum of specific initiative costs from tech estimates

---

## PHASE 4 — VALIDATE

□ Early wins deployable on existing systems without W2 dependencies?
□ Wave structure covers all initiatives from SKILL 03 value architecture?
□ Dependencies explicit and logically sound?
□ Gate criteria specific and measurable (not "when ready")?
□ Investment by year, not just total?
□ Investment triangulated with 2+ benchmark sources?
□ Timeline benchmarked against reference layer implementation cases?
□ Critical dependency chain identified with cascade consequences?
□ Payback period calculated?
□ Gaps recorded for assumptions without benchmarks?

Then write to scratchpad.

---

## CRITICAL RULES

1. **Gate criteria must be specific.** "We'll start Wave 2 when Wave 1 is done" is not a plan. State the measurable outcome that triggers each wave transition.
2. **Early wins must be real.** "Develop AI strategy" is not an early win. A deployed system with measurable output in M0-M6 is.
3. **Dependency logic must be explicit.** If data infrastructure must exist before AI models can train, say so — and state what happens to the overall timeline if data infrastructure slips 6 months.
4. **Investment must be year-by-year, not total.** PE partners allocate capital annually. A total figure without phasing is not actionable.
5. **Benchmark timelines.** "18-month Wave 1" requires a comparable: "benchmarked against similar BPO AI transformation pilots that averaged 14-22 months from decision to gate (reference layer)."

---

## NEGATIVE EXAMPLES

**BAD:** "Wave 1 will focus on establishing the AI foundation, building capabilities, and preparing the organization for future waves."
**GOOD:** "Wave 1 (M0-M18): (1) AI bill ingestion pilot — 500K units, existing data, no new infrastructure, target: 60% error auto-resolution rate; (2) Anomaly detection model — trained on 24 months historical billing data, target: flag >80% of billing anomalies before manual review; (3) Customer portal NLP upgrade — dispute auto-triage, target: 50% of disputes auto-triaged without human touch. Gate criteria: STP rate improvement from baseline to >55%, measured at M12. Investment: $8.5M-$12M. Benchmark: comparable BPO AI pilots at $5-15M for similar scale (ARDEM 2025). Key hires before Wave 1 start: Chief AI Officer + VP Data Science."

**BAD:** "The total transformation will require approximately $50-60M in investment over the hold period."
**GOOD:** "Investment phasing: Year 1: $10M-$14M (data infrastructure + Wave 1 AI pilots); Year 2: $15M-$20M (Wave 2 expansion, MLOps infrastructure, data product development); Year 3: $12M-$18M (Wave 3 customer-facing AI, data product launch); Year 4: $8M-$13M (optimization, moat deepening). Total: $45M-$65M. Payback: 24-36 months from Wave 1 gate. Triangulation: (A) 3-5% of revenue benchmark for focused BPO-to-tech transformation = $12.7-$25.8M/year (consistent); (B) Comparable BPO transformation — EXL Service ~10% of revenue total investment, our case lighter at 3-5% given more focused scope (EXL 2021 annual report); (C) Bottom-up itemized: Wave 1 $11M + Wave 2 $17.5M + Wave 3 $15M + Wave 4 $10.5M = $54M midpoint. Convergence within 15%. Confidence: MEDIUM. ●●●○"
