# SKILL 07 — Talent Strategy

**Purpose:** Who runs this. What team needs building. Workforce evolution — specific, honest, and humane. Org design for the transformed company.

**Inputs:** scratchpad.execution_plan + scratchpad.tech_strategy + scratchpad.reference_layer
**Writes to:** scratchpad.talent_strategy

---

## PHASE 1 — RESEARCH PLAN

I need to establish:

1. **Current leadership:**
   - Who is the CEO and key leaders? What is their track record? (LinkedIn, press, company bio)
   - What gaps exist for the transformation mandate? (AI leadership, tech transformation experience, data expertise)
   - Any PE sponsor signals about leadership change intent?

2. **New roles required:**
   - What leadership roles does this transformation require that don't exist today?
   - Sequenced: who is needed before Wave 1, during Wave 1, by Wave 2?
   - For each role: can it be developed internally or must it be hired externally?

3. **Workforce evolution:**
   - What % of current workforce does the transformation address? (from SKILL 03 lever calculations)
   - What is the natural attrition rate for this company/industry? (attrition absorbs headcount without forced reduction)
   - Which roles evolve to higher-skilled work vs. are eliminated?
   - What retraining is realistic (not just theoretically possible)?
   - How is workforce reduction managed at this scale — timeline, severance, communication?

4. **Talent market:**
   - Supply/demand for key roles: Chief AI Officer, ML engineers, data scientists, transformation PMO
   - Comp benchmarks from reference layer talent data
   - Time-to-hire for critical roles in current market

5. **Culture and org structure:**
   - What org structure supports the transformation? How does it differ from current?
   - What change resistance is likely at this scale of automation?

Search: leadership team (LinkedIn, press), talent market data for AI roles, natural attrition rates for this industry, workforce transition case studies, comp benchmarks

---

## PHASE 2 — GATHER

Collect:
- Current leadership team from LinkedIn and press (title, tenure, prior experience)
- Job posting patterns as org structure signal — what roles are being hired?
- Natural attrition rates for this industry from reference layer or new search
- Comp benchmarks for key transformation roles (Chief AI Officer, VP Data Science, ML engineers)
- Case studies: how did comparable companies manage workforce transition during automation?

Record source + date for every data point.
Record gaps for all leadership data that cannot be found from public sources.

---

## PHASE 3 — REASON

**LEADERSHIP GAP ASSESSMENT:**
For each gap identified:
- What capability is missing?
- What is the consequence of that gap persisting through Wave 1?
- Rate urgency: must fill before Wave 1 / can fill during Wave 1 / Wave 2 timing acceptable

**NEW ROLES REQUIRED (prioritized list):**

For each role, state:
```
Role: [title]
Priority: IMMEDIATE (before Wave 1) / YEAR 1 / YEAR 2
Rationale: [why this role unblocks what — specific]
Approach: HIRE (external) / PROMOTE (internal) / DEVELOP (grow into)
Comp range: $___K-$___K total (source: reference layer talent benchmarks)
Time-to-hire: ___ months (benchmark: comparable role search timelines)
Critical dependency: [what cannot start until this role is filled]
```

**WORKFORCE EVOLUTION:**

Be specific with numbers. Not narrative.

```
Addressable headcount: ___FTE (from SKILL 03 lever calculation)
  = ___% of [total headcount from SKILL 01]

Natural attrition path:
  Annual attrition rate: ___% (source: [industry benchmark])
  FTE absorbed per year: ___
  FTE absorbed over Wave 1-3 (__ years): ___
  = ___% of addressable headcount absorbed without forced reduction

Retraining opportunity:
  ___FTE (___%) can realistically retrain to [specific higher-skilled roles]
  ___FTE (___%) cannot be retrained — role type eliminated, not evolved
  Basis: [evidence for retraining ceiling, not wishful thinking]

Managed reduction (if attrition insufficient):
  ___FTE requiring active offboarding
  Timeline: over ___months, starting [wave/date]
  Approach: [severance structure, communication timeline, support resources]
```

**KEY PERFORMER ATTRITION RISK:**

Distinguish general workforce attrition (which absorbs automatable headcount) from key performer flight (which impairs execution). Identify:
- Which roles, if vacated voluntarily during transformation, would most delay the Wave 1-2 timeline?
- Is there a retention mechanism (equity, milestone bonuses, explicit career path) in the plan?
- If no retention mechanism exists, this is a risk that must surface in SKILL 08.

Be honest: high performers often leave *first* when automation threatens their roles, not last.

**ORG STRUCTURE:**
```
Current:  [describe current model — functional, operational, geographic]
Target:   [describe target model post-transformation]
Key structural change: [what shifts and why — e.g., "technology function from cost center to product org"]
Transition path: [how you get from current to target, phased]
```

**CULTURE SHIFT:**
What changes because the operating model changes?
- From: [current operating behaviors — e.g., manual exception handling, tribal knowledge]
- To: [target operating behaviors — e.g., data-driven exception routing, systematic playbooks]
- Resistance likely: [specific resistance patterns based on workforce profile and change type]
- Management actions: [specific mitigation, not "communicate well"]

---

## PHASE 4 — VALIDATE

□ Leadership gap assessment grounded in evidence, not assumed?
□ New roles sequenced with clear priority rationale and critical dependency noted?
□ Comp ranges sourced from reference layer talent benchmarks?
□ Workforce evolution shows specific numbers (not "attrition will help manage transition")?
□ Attrition rate sourced, not assumed?
□ Retraining opportunity realistic — not wishful (not all processing staff become data scientists)?
□ Workforce reduction plan: specific FTE count, timeline, approach?
□ Org structure change described with transition path?
□ Culture shift addresses realistic resistance patterns?
□ Talent risks specific to this company situation?
□ Gaps recorded for leadership data that couldn't be verified?

Then write to scratchpad.

---

## CRITICAL RULES

1. **Workforce numbers, not narrative.** "Natural attrition will help manage the workforce transition" is not a talent strategy. "At 20% annual attrition, 1,356 FTE absorbed over 4 years — covering 80% of automatable headcount without forced reduction, leaving 338 FTE requiring managed offboarding" is.
2. **Retraining ceiling.** Not all displaced workers can retrain. A BPO processing clerk cannot realistically become a data scientist in 24 months. Be honest about what's achievable — and what isn't.
3. **Leadership gaps are execution risks.** An unfilled Chief AI Officer at Wave 1 start is not a talent planning note — it is a critical path blocker that belongs in SKILL 08 risk register too.
4. **Comp benchmarks must be sourced.** "Chief AI Officer salary" from the reference layer talent data, not assumed.
5. **Org structure must be specific.** "A more technology-focused organization" is not an org structure. "Product org structure with technology as a revenue-generating unit, reporting to CEO alongside managed services" is.

---

## NEGATIVE EXAMPLES

**BAD:** "The company will need to hire AI leadership and manage workforce changes carefully during the transformation."
**GOOD:** "NEW ROLES REQUIRED (IMMEDIATE — before Wave 1): (1) Chief AI/Technology Officer — no CAIO/CTO identifiable from public sources (LinkedIn search Feb 2026: no technology C-suite). Scope: own AI roadmap, vendor selection, data infrastructure build. Must be external hire — no internal transformation track record evident. Comp: $400K-$550K total (VP/C-suite AI in managed services — reference layer talent benchmark). Time-to-hire: 4-6 months in current market. If unfilled at Wave 1 start: Wave 1 gate criteria cannot be set or enforced — single highest-leverage hire. (2) VP Data Science — owns anomaly detection model development. Wave 1 cannot complete gate criteria without this role filled by M3. External hire only; no internal ML team exists. Comp: $280K-$380K. Time-to-hire: 3-5 months."

**BAD:** "The company has approximately 3,387 employees. Some roles will be displaced by automation, but the company will manage this sensitively."
**GOOD:** "WORKFORCE EVOLUTION: Addressable headcount: 1,694 FTE (50% estimated processing roles, SKILL 01 MEDIUM confidence). Natural attrition: managed services/BPO average turnover 18-25% annually (SHRM 2025 BPO sector). At 20% rate: 339 FTE/year, over 4 years = 1,356 FTE absorbed through natural turnover — 80% of addressable headcount without forced reduction. Retraining opportunity: 10-15% of processing staff (170-254 FTE) can realistically retrain to quality assurance, exception management, and customer success roles — based on skill adjacency analysis, not wishful thinking. Net headcount requiring managed offboarding: ~340 FTE over Months 24-48, concurrent with Wave 2-3 automation deployment. Approach: severance + 60-day notice + outplacement support — benchmarked against comparable BPO workforce transitions."
