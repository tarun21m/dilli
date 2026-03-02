# System Methodology, Evals & Guardrails

The value of this architecture is not in the prompts themselves, but in the structural constraints placed on the agent. These principles and guardrails ensure the agent behaves like a fiduciary researcher rather than a creative writer.

---

## The Approach & State Management

The diligence agent operates sequentially, not in parallel. Each skill is strictly dependent on the skill before it.

**The Scratchpad as Single Source of Truth:**
Skills do *not* pass context directly to one another. Instead, they all read from and write to a centralized JSON `scratchpad` (Layer 3). When `SKILL 01` (Company Depth) finds a fact, it writes it to the `scratchpad`. When `SKILL 03` (Value Architecture) needs that fact to model a transformation, it reads it from the `scratchpad` — it does not re-research it. 

This architecture prevents the LLM "context amnesia" common in long loops.

**Sequential Composition:**
The order is intentional and mathematically bounded:
1. `SKILL 00` builds the overarching **Reference Layer** (benchmarks & comps).
2. `SKILL 01` establishes the **EBITDA Base**.
3. `SKILL 02` sizes **Opportunity Magnitude** against that base.
4. `SKILL 03` translates magnitude into a **Target Operating Model**.
5. `SKILL 04` sequences the **Execution Timeline** to reach that model.
6. `SKILL 05` bridges the baseline and the target into an **Investment Profile**.
7. `SKILL 06 & 07` identify the **Tech & Talent** required to execute the timeline.
8. `SKILL 08` attacks the formulated thesis to build a **Risk Register & Floor Case**.
9. `SKILL 09` runs a programmatic **Cross-Block Consistency Check** against all scratchpad outputs.

If SKILL 01 cannot find an EBITDA number, it cannot invent one. It must write "Undisclosed" and generate a calculated estimate. This uncertainty propagates forward: SKILL 05 cannot assign a `HIGH` confidence rating to the financial bridge if the baseline was `LOW` confidence. Finally, SKILL 08 must consume that uncertainty, treating the low-confidence bridge as a structural vulnerability and modeling an aggressive floor case in response.

---

## Validation Architecture

The system does not trust the LLM to get it right on the first try. It uses a three-level validation stack:

- **Inline Validation:** Every SKILL ends with Phase 4 (Validate). Outputs cannot be written to the `scratchpad` state until the LLM successfully completes a checklist proving it triangulated its math, sourced its claims, and didn't violate constraints.
- **Checkpoint Validation:** Hard stage-gates between phases (Checkpoints A, B, C) where execution can halt for review before committing significant tokens/money to the next phase of deep reasoning.
- **Final Validation (SKILL 09):** A dedicated cross-block consistency check. The agent reads the final `scratchpad` state and issues an actionable **GO**, **CONDITIONAL GO**, or **NO-GO** recommendation based on evidence integrity and gap closure.

---

## The 7 Core Principles

**PRINCIPLE 1 — Plan before you search**
The agent writes a research plan for each block before executing a single search. What questions must this block answer? What sources would answer them? This is task decomposition strictly applied to diligence.

**PRINCIPLE 2 — Separate gathering from reasoning**
*Raw research phase:* collect facts, numbers, sources. 
*Reasoning phase:* interpret, structure, score confidence. 
Never mix them. Mixing produces lower quality on both, and gives the LLM room to hallucinate facts to fit a narrative.

**PRINCIPLE 3 — Structured state object, not prose**
Everything the agent learns lives in a typed object (`scratchpad`). Blocks read from it and write to it. No block re-derives what a prior block established. This is what makes the analytical chain compound rather than wander.

**PRINCIPLE 4 — Confidence is explicit, not implied**
Every claim must answer: what's the source, how was it derived, how confident are we? This is not just a UI feature — it is a discipline that forces the agent to differentiate internally between *verified* and *estimated*.

**PRINCIPLE 5 — Calibration over prompt tuning**
Don't iterate prompts in the abstract. Run against Conservice (or another known company) as the gold standard. Does the output match what was built manually? That's the only test that matters.

**PRINCIPLE 6 — Graceful degradation is honest degradation**
Private company, thin data, limited sources — the agent says so explicitly rather than filling gaps with plausible-sounding estimates at high confidence. It marks what it couldn't find, and explicitly adjusts confidence down.

**PRINCIPLE 7 — Industry context changes what you look for**
A utility billing company search is different from a SaaS company search. The agent detects industry context in Block 1 and loads the right analytical lens for all subsequent blocks. Labor intensity patterns, data asset types, competitive dynamics — these are all industry-specific.

---

## Evaluation & Calibration Approach

### Structural Validity (Deterministic)
Does the output follow the schema? Right sections, right depth, right conciseness? Numbers present where required? Sources cited? This IS testable deterministically via code.

### Analytical Quality (Human Judgment)
Is the insight non-generic? Would a senior PE analyst find this useful? Does it surface something non-obvious? This requires human judgment — it is not currently automatable.

### Consistency (Statistical)
Run the same company twice — do you get materially different conclusions?
* High variance = weak prompts.
* Low variance = prompts and constraints are doing the work.
This IS testable statistically.

---

## Guardrails

**HARD GUARDRAILS (enforced in code):**
- **Schema compliance:** right sections present
- **Length limits:** no block exceeds N tokens
- **Source requirement:** minimum 2 sources per claim for HIGH confidence
- **Confidence required:** every quantitative claim has a score
- **No hallucination tells:** flag "likely", "probably", "appears to be" as signals of thin evidence leaking into prose

**SOFT GUARDRAILS (prompt-enforced, human-reviewed):**
- Conciseness quality
- Insight depth
- Non-obviousness of structural opportunity
- Financial bridge credibility

---

## The 4-Part Calibration Protocol

1. **AUTOMATED — schema + structure compliance**
   Fast, runs every time, catches regressions instantly.
2. **HUMAN SPOT CHECK — analytical quality**
   Review 2-3 outputs per week. Flag where it was generic, where it was sharp. Feed observations back into prompts.
3. **BLIND COMPARISON — consistency**
   Run the same company on different days. Compare outputs — are conclusions stable? High variance flags prompt weakness.
4. **ADVERSARIAL — stress test**
   Run on a company with almost no public data. Does it degrade gracefully or hallucinate confidently? This catches the most dangerous failure mode before it reaches an Investment Committee.

---

## The Reference Layer (SKILL 00)

Before analyzing a target company, the system builds an overarching "Reference Layer" to ground all downstream assumptions. This consists of:

1. **INDUSTRY BENCHMARKS:** Operational metrics for this sector. Labor as % of revenue, margin profiles, revenue per employee, growth rates. *Crucially: benchmarks are dated (benchmarks from 2021 are not 2025 benchmarks).*
2. **COMPARABLE COMPANIES:** 3-5 peers in the same space. Public where possible for disclosed metrics; private peers via estimates. Key metrics tracked: revenue, margins, headcount, growth rate, valuation multiples. What they did right, what they got wrong.
3. **TRANSACTION COMPARABLES:** Recent PE deals in this sector. Entry/exit multiples, hold periods. Value creation levers that worked. What drove multiple re-rating.
4. **AI TRANSFORMATION BENCHMARKS:** What has AI *actually* delivered in this industry. Specific case studies — not theoretical. Labor reduction %s achieved in practice. STP rates, AHT improvements, exception rates.
5. **MARKET CONTEXT:** TAM, growth rate, structural tailwinds/headwinds. Regulatory environment. M&A activity and consolidation trends. Customer concentration risks in this sector. Why now — macro factors creating urgency.
6. **FAILURE CASES:** Companies in this space that failed to transform. Or got disrupted, or missed the window. What the warning signs were. This feeds directly into the Risk Management block and inversion thinking.
7. **MANAGEMENT / TALENT BENCHMARKS:** What does a strong leadership team look like for this type of transformation? Compensation benchmarks for key roles. Org structures that work at this scale.
