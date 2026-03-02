# SKILL 06 — Tech Strategy

**Purpose:** What technology decisions must be made. Current state assessment, build vs. buy vs. integrate framework, AI stack architecture, data infrastructure gap, key technical risks.

**Inputs:** scratchpad.execution_plan + scratchpad.financial_bridge + scratchpad.reference_layer
**Writes to:** scratchpad.tech_strategy

---

## PHASE 1 — RESEARCH PLAN

I need to establish:

1. **Current state:**
   - What technology does this company run on today? (job postings, engineering blog, product pages, LinkedIn tech stack signals)
   - What are the structural limitations of the current stack under AI transformation?
   - Data infrastructure: centralized vs. siloed? cloud vs. on-prem? structured vs. unstructured?
   - Evidence of tech debt indicators: job posting language, customer complaint patterns, operational metrics from SKILL 01

2. **Build vs. buy vs. integrate:**
   For each technology component required by the SKILL 03/04 transformation:
   - Build: when proprietary data advantage or core IP justifies ownership
   - Buy: when commodity capability is faster, cheaper, sufficient
   - Integrate: when existing vendor relationships provide a faster path

3. **AI stack architecture:**
   - Data layer: where does training/inference data live? quality? format?
   - Model layer: fine-tuned proprietary models vs. off-shelf APIs?
   - Application layer: where does AI output surface — customer-facing or internal?

4. **Data infrastructure gap:**
   - What does the transformation require that doesn't exist today?
   - Data quality, labeling, pipeline, storage, access — gap by gap

5. **Technical risks:**
   - Realistic failure modes from a technology perspective
   - Vendor dependencies, integration complexity, data quality blockers, single points of failure

Search: company tech stack signals (job postings, LinkedIn engineer titles, product pages), AI vendor landscape for this sector, integration complexity benchmarks, implementation cost benchmarks from reference layer

---

## PHASE 2 — GATHER

Collect:
- Tech stack signals from job postings (what technologies do current engineers list?)
- Engineering or product blog evidence of technology choices
- AI/ML vendor landscape specific to this sector
- Implementation complexity benchmarks for the relevant stack type
- Reference layer technology benchmarks and build vs. buy data

For tech stack that cannot be verified from public sources: flag as gap, do not assume.

---

## PHASE 3 — REASON

**CURRENT STATE ASSESSMENT:**
Based on gathered evidence:
- Stack classification: legacy / modern / hybrid — with evidence basis, not assumption
- Data centralization: centralized / fragmented / partially centralized — with evidence
- Tech debt indicators: HIGH / MEDIUM / LOW — with specific evidence (not "all companies have tech debt")
- Data infrastructure readiness for AI: what exists vs. what's needed

**BUILD vs. BUY vs. INTEGRATE DECISION TABLE:**

For each major technology component required by the transformation:
```
| Component | Decision | Rationale | Cost Estimate | Timeline | Lock-in Risk | Confidence |
|-----------|----------|-----------|---------------|----------|--------------|------------|
```

Build decision criteria: proprietary data advantage that vendors cannot replicate; core IP; competitive moat built on owning the model
Buy decision criteria: commodity capability; integration faster than build by >12 months; no competitive advantage to owning the capability
Integrate decision criteria: existing vendor relationship; acceptable lock-in risk; fastest path to capability

**Lock-in Risk (required for all BUY and INTEGRATE decisions):** State what happens if the vendor raises prices 50% in Year 3 or the API changes materially. If no exit path exists within 12 months, this is a HIGH vendor dependency risk that must be surfaced in SKILL 08.

Cost and timeline estimates must be sourced from reference layer or new benchmarks — not assumed.

**AI STACK ARCHITECTURE:**
```
Data layer:        [what infrastructure gets data into training/inference-ready state]
Model layer:       [which components use fine-tuned proprietary models vs. off-shelf APIs]
Application layer: [where AI surfaces in user/customer experience — specific touchpoints]
```

**DATA INFRASTRUCTURE GAP:**
Current state → Required state → Gap description → Effort to close (benchmarked)

The gap must be sized: how much time and investment does closing it require? This feeds back into SKILL 04 Wave 1 timeline and SKILL 05 investment.

**KEY TECHNICAL RISKS:**
For each risk:
- Description: specific to this company, not generic
- Likelihood: HIGH / MEDIUM / LOW with rationale
- Impact: HIGH / MEDIUM / LOW with downstream consequence
- Mitigation: specific and actionable

---

## PHASE 4 — VALIDATE

□ Current state assessment grounded in public evidence (job postings, blog, product pages)?
□ Build vs. buy table covers all major transformation components from SKILL 03/04?
□ Rationale for each decision explicit?
□ Cost and timeline estimates sourced from benchmarks?
□ AI stack architecture covers all three layers?
□ Data infrastructure gap sized with effort estimate?
□ Technical risks specific to this company (not "technology projects are risky")?
□ Tech strategy consistent with execution plan timeline and financial bridge investment?
□ Gaps recorded for unverifiable tech stack elements?

Then write to scratchpad.

---

## CRITICAL RULES

1. **Evidence-based current state.** Do not assume the tech stack. Job postings are a reliable proxy — engineers list the technologies they use. If no evidence exists, flag as a gap.
2. **Build vs. buy requires explicit rationale.** "We should build the AI platform" is not a tech strategy. "We should build the anomaly detection model layer because our 96M annual billing transactions are proprietary training data no vendor can replicate" is.
3. **Cost estimates must be sourced.** "The data infrastructure build will cost $5-8M" requires a comparable: "benchmarked against similar cloud data lake implementations at comparable data volume (AWS case studies 2024)."
4. **AI stack is three layers.** A model without a data layer and application layer is not a stack — it is a model. Define all three.
5. **Data infrastructure gap is upstream of everything.** If the data gap is large, Wave 1 in SKILL 04 must address it before AI models can train. Flag this dependency explicitly.

---

## NEGATIVE EXAMPLES

**BAD:** "The company will need to invest in modern AI/ML infrastructure to support its transformation goals."
**GOOD:** "CURRENT STATE: Conservice Synergy platform (proprietary, circa 2015). Tech stack indicators from LinkedIn job postings (Feb 2026): Java/Python backend, AWS infrastructure, Salesforce CRM integration. No ML engineer or data scientist roles posted in last 12 months — indicates no existing ML capability. Data infrastructure: 8M units × 12 billing cycles = ~96M structured billing transactions/year on AWS. This is high-volume structured data — well-suited for anomaly detection training. Gap: no evidence of labeled anomaly dataset, ML feature pipeline, or model serving infrastructure. Data infrastructure is 70% ready; last 30% (labeling, pipeline, serving) requires Wave 1 investment."

**BAD:** "The company should build its AI capabilities to maintain competitive advantage."
**GOOD:**
```
| Component | Decision | Rationale | Cost | Timeline |
|-----------|----------|-----------|------|----------|
| Anomaly detection model | BUILD | Proprietary 96M transaction training corpus is core IP no vendor can replicate | $2.5M-$4M | M6-M18 |
| LLM billing explanations | BUY | Azure OpenAI commodity; 2 month integration vs. 18 month build; no strategic value to owning LLM layer | $200K-$400K/year | M3-M6 |
| MLOps infrastructure | BUY | Databricks or SageMaker; market standard; build cost $3-5M vs. buy $600K/year = breakeven >5 years | $500K-$700K/year | M2-M4 |
| Customer portal AI | INTEGRATE | Salesforce Einstein via existing CRM relationship; fastest path to customer-facing AI | $150K-$300K/year | M4-M8 |
```
