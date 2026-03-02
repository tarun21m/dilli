# SKILL 01 — Company Depth

**Purpose:** Establish the factual foundation for the target company. Business model, scale, ownership, competitive position, operational profile, financial metrics. Facts only — no analysis, no opportunity framing, no recommendations.

**Inputs:** scratchpad.reference_layer
**Writes to:** scratchpad.company_depth

---

## PHASE 1 — RESEARCH PLAN

Write this plan before any tool call:

I need to establish:
1. Business model — what does this company do precisely? Revenue model, unit economics, ARPU, how it charges customers
2. Scale — revenue, employees, units/accounts served, geographies, growth trajectory
3. Ownership — current owner, ownership history, PE sponsor if applicable, acquisition date. (If current sponsor has held for 4+ years, exit motivation is HIGH. If <18 months, exit motivation is LOW).
4. Competitive position — market share claims, key differentiators vs. named competitors, known vulnerabilities
5. Data assets — volume, type, uniqueness, structural advantage or vulnerability
6. Financial metrics — all disclosed or estimable: revenue, EBITDA, growth rate, margins
7. Customer profile — buyer type, contract structure, concentration, churn, NPS or satisfaction data
8. Operational model — what is the core delivery process? Labor/tech intensity? Where are humans in the loop?

**Search sequence (all 8 steps) with Scraping Fallbacks:**
1. [Company] LinkedIn — employee count, growth signals, job posting patterns.
   *(Fallback if blocked: Google Search `site:linkedin.com/company [Company Name] "employees"`)*
2. [Company] Crunchbase — revenue estimates, funding history, ownership, investor names.
   *(Fallback if blocked: Google Search `site:crunchbase.com/organization [Company]`)*
3. [Company] press releases + news — product announcements, acquisitions, management changes, awards
4. [Company] customer reviews — Trustpilot, G2, BBB — complaint categories, recurring themes, volume
5. [Company] competitors/alternatives — market positioning, win/loss signals, feature comparisons
6. [Company] financial data — PitchBook, GrowJo, RocketReach revenue estimates.
   *(Fallback if blocked: look for recent M&A press releases involving company + 'growth' to infer scale)*
7. [Company] + "acquisition" OR "investment" — ownership history and PE thesis signals
8. Reference layer benchmark comparison — compare every metric found against comparable company benchmarks

Expected gaps: [list known limitations — EBITDA almost never disclosed for private companies; customer concentration rarely public]

---

## PHASE 2 — GATHER

Collect facts. No interpretation.

**Stop Loss / Time-Bounding Rule:**
Maximum 4 sequential searches for undisclosed financial metrics. If not found within 4 attempts, declare the gap, trigger the derivation chain, and move on. Do not burn cycles chasing ghosts.

**Number Validation Rules:**
- Revenue: find 2+ independent sources (Crunchbase, LinkedIn revenue estimates, press releases, job posting proxy). Document each source, date, and credibility note.
- Employee count: find 2+ independent sources (LinkedIn current + Crunchbase or press release). Document variance between sources.
- Any disclosed operational metric: validate against reference layer comparable benchmarks.
- EBITDA: if not disclosed (common for private companies), do NOT skip it and do NOT invent it. Flag as gap. Prepare derivation chain for Phase 3.

**For each data point collected:**
- Record the URL/source, publication date, and credibility note
- Flag whether it is primary (company filing, press release, official statement) or secondary (third-party estimate)
- Flag any data point >24 months old

**For customer sentiment:**
- Count total reviews and proportion negative/positive across platforms
- Identify and count recurring complaint categories (not general impressions)
- Record NPS or customer satisfaction score if findable from any source

---

## PHASE 3 — REASON

Interpret against reference layer. No new facts.

**For every financial metric:**
- Compare against reference layer comparable company benchmarks
- State explicitly: above benchmark / in-line / below benchmark — and by how much
- If EBITDA undisclosed: derive with explicit chain using 2-3 methods and triangulate

**EBITDA derivation format (when undisclosed):**
```
Method A (sector benchmark): Revenue × [sector median EBITDA %] = $X
  Source: [benchmark source + date]
Method B (revenue/employee proxy): Headcount × [estimated loaded cost/FTE] → estimated OpEx → EBITDA
  Source: [industry cost benchmarks]
Method C (sponsor signal): [PE acquisition / investor interest implies floor]
  Source: [deal announcement or investment thesis language]
Convergence: [within 15%? within 30%? divergent?]
Selected estimate: $X-Y range. Confidence: LOW (derived, not disclosed). ●●○○
```

**For competitive position:**
- State the actual differentiator with evidence (not marketing language)
- State the competitive vulnerability with evidence
- Reference specific competitors identified in reference layer

**For operational model:**
- Is this labor-intensive or tech-intensive? What is the ratio and what does it imply for transformation potential?
- Where are humans performing work that AI could automate? Be specific.

---

## PHASE 4 — VALIDATE

**JSON Intermediate State:**
Before writing the final text output, construct a structured JSON object representing the metrics found. This anchors the numbers and prevents context-window amnesia:
```json
{
  "metric": "Revenue",
  "value_range": ["$X", "$Y"],
  "confidence": "MEDIUM",
  "sources": [{"url": "...", "date": "..."}]
}
```

**Validation Checklist:**
□ Business model described precisely (not generically)?
□ Revenue stated with source + date + confidence level?
□ Employee count from 2+ sources?
□ EBITDA: either disclosed with source, or estimated with 2-method derivation chain marked LOW?
□ Every metric compared to reference layer benchmarks with above/in-line/below notation?
□ Customer profile includes contract type + NPS/satisfaction data if findable?
□ Competitive position includes both differentiator AND vulnerability with evidence?
□ Ownership history captured?
□ No opportunity analysis introduced (that belongs in SKILL 02)?
□ Gaps recorded for all data not found?

Then write to scratchpad.

---

## CRITICAL RULES

1. **Facts only.** Do not write "This suggests AI opportunity..." in SKILL 01. That is SKILL 02's job. Collect the facts and stop.
2. **EBITDA gap treatment:** EBITDA is almost never public for private companies. Do not skip it — estimate it explicitly with a 2-method derivation chain and LOW confidence. An honest estimate with shown methodology is more useful than silence.
3. **Benchmark every metric.** "Revenue: $400M" tells a reader nothing. "Revenue: $400M — above comparable managed services operators at $50-200M, suggesting premium scale or pricing power" is actionable.
4. **Customer sentiment is operational data.** Count complaints, categorize them, record the NPS score. These are facts, not opinions. Record without editorializing.
5. **Source variance is information.** If two revenue estimates differ by 22%, say so. The variance itself tells you something about data quality.

---

## NEGATIVE EXAMPLES

**BAD:** "Conservice is a leading utility billing company with a strong market position and significant scale."
**GOOD:** "Conservice: utility billing managed services, 8M residential units, 20,000+ property providers. Revenue: $422.7M (RocketReach 2025) to $515.6M (GrowJo 2024) — 22% variance between estimates, reflecting limited public financial data for private company. Midpoint: $469M. 3,387 employees (LinkedIn March 2025). Revenue/employee: $124,800-$152,200 — below managed services benchmark of $175K-$225K (reference layer: sector median), indicating high labor intensity. ●●●○ MEDIUM confidence on revenue — two sources, 22% variance."

**BAD:** "The company faces some customer satisfaction challenges."
**GOOD:** "NPS: -64 (Comparably 2026). 561+ BBB complaints (Feb 2026). Trustpilot: 71% 1-star (Feb 2026, 234 reviews). Recurring complaint categories by frequency: billing opacity 43%, dispute resolution delays 31%, unexplained charge itemization 26%. This is operational fact — it quantifies a measurable gap, not an impression."

**BAD:** "EBITDA data was not publicly available for this private company."
**GOOD:** "EBITDA undisclosed. Derived estimate: 10-14% margin. Method A: IT/managed services sector benchmark 8-20% (Umbrex 2026), labor-intensive model with $124.8K-$152.2K revenue/employee places at low end → 10-14%. Method B: BPO analogs with similar headcount-to-revenue ratios operate at 10-15% EBITDA pre-automation (ARDEM 2025). Method C: TPG acquisition Dec 2025 implies sponsor conviction in positive material EBITDA — sets floor at >5%. Convergence: 10-14% range. Absolute: $42M-$72M on $422.7M-$515.6M revenue base. Confidence: LOW. ●●○○"
