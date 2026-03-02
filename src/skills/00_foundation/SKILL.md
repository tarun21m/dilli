# SKILL 00 — Diligence Foundation

**Purpose:** Assemble the reference layer before any analysis begins. Industry benchmarks, comparable companies, transaction comps, AI transformation cases, and failure cases — all sourced from the web, dated, and recorded. No analytical skill may execute until this foundation is in place.

**Inputs:** Company name only
**Writes to:** scratchpad.reference_layer

---

## PHASE 1 — RESEARCH PLAN

Before any tool call, write this plan explicitly:

I need to find:
1. Industry identification — sector, sub-sector, defining operational characteristics
2. Industry operational benchmarks — labor % of revenue, EBITDA margin ranges, revenue per employee, organic growth rates, automation benchmarks
3. Comparable companies (3-5) — same industry, similar scale; fetch revenue, EBITDA, employees, growth
4. Transaction comparables — PE deals in this sector last 5 years; entry/exit multiples, hold periods, value creation levers
5. AI transformation cases — actual % improvements achieved (not theoretical), covering all 5 opportunity types where possible
6. Failure cases — companies that attempted transformation and failed; warning signs in retrospect
7. Market context — TAM, growth rate, tailwinds/headwinds, regulatory environment, M&A activity
8. Technology benchmarks — build vs buy costs, implementation timelines, AI vendor landscape for this sector
9. Talent benchmarks — key leadership roles, comp ranges, org structures at comparable scale
10. Customer benchmarks — buyer profile, ACV, churn rates, NPS benchmarks, switching drivers

I will search using queries like: "[industry] EBITDA margin benchmark [year]", "[comparable company] revenue employees", "[industry] AI automation case study ROI", "[sector] PE transaction multiples [year]"

Expected gaps: [list known limitations before starting — e.g., "private company financials often unavailable"]

Do not begin gathering until this plan is written.

---

## PHASE 2 — GATHER

Execute the plan. Collect raw facts only — no interpretation.

**Source Rules:**
- Record every source: URL + title + publication date + publisher
- Two outlets reporting the same underlying number = ONE source, not two
- Prefer sources <24 months old; flag any benchmark >36 months old as [STALE]
- 3+ distinct source types required (e.g., market research firm + trade press + company filing = 3 types; two market research firms citing the same primary study = 1 type)

**For each comparable company, record:**
- Revenue (source + date + confidence level)
- EBITDA margin if available (source + date)
- Employee count (source + date)
- Growth rate (source + date)
- One defining operational metric for this industry

**For AI transformation cases, seek at least one case per opportunity type:**
- TYPE 1 (cost/labor): actual % cost reduction, FTE impact, timeline achieved
- TYPE 2 (data monetization): revenue from data products, pricing, customer profile
- TYPE 3 (revenue expansion): new segment growth, attach rates, revenue magnitude
- TYPE 4 (quality/experience): NPS improvement delta, error rate reduction, churn impact
- TYPE 5 (competitive moat): retention improvement, switching cost data, data flywheel evidence

**Adjacent sector fallback:** If sector-exact AI transformation cases cannot be found for a given type, adjacent-sector cases may be used — but must be labeled `[ADJACENT SECTOR]` and you must state in one line why the analog applies (e.g., "same labor-intensive BPO model, different vertical"). Do not silently apply a retail AI case to a managed services operator.

**For failure cases:**
- What was the transformation goal?
- What went wrong and when?
- What warning signs existed in retrospect?
- What was the financial consequence?

Record every gap when data is not found. Do not reason about data in this phase.

---

## PHASE 3 — REASON

Interpret gathered data only. No new facts.

- Summarize industry characteristics in 2-3 sentences: what defines performance in this sector?
- Identify the 3 most important benchmarks for analyzing a company in this space
- For each AI transformation case: what does the magnitude imply for an average operator?
- For each failure case: what is the transferable warning for this company type?
- Identify which benchmark gaps would most affect downstream analysis confidence

No analysis of the target company yet. Reference layer only.

---

## PHASE 4 — VALIDATE

Before writing to scratchpad, confirm every item:

□ Industry identified with sector + sub-sector + operational characteristics?
□ At least 4 operational benchmarks sourced with dates?
□ 3-5 comparable companies with revenue + employees at minimum?
□ At least 2 transaction comps with entry multiples?
□ At least 3 AI transformation cases with actual % metrics (not theoretical)?
□ At least 2 failure cases with traceable warning signs?
□ All sources dated — stale sources flagged?
□ Source independence checked — no double-counting?
□ Gaps recorded for everything not found?
□ No company-specific analysis introduced here?

Then write to scratchpad.

---

## CRITICAL RULES

1. **Source independence:** If Reuters and Bloomberg both cite the same McKinsey report, that is ONE source.
2. **Freshness:** Benchmarks from more than 36 months ago need a [STALE] flag and should be supplemented with current data.
3. **Sector specificity:** AI transformation cases must come from the same industry or directly adjacent. "AI reduces costs by 30% in most industries" is not a reference layer entry.
4. **Foundation dependency:** Everything downstream depends on this reference layer. If benchmarks are weak, the entire analysis degrades. Record gaps explicitly rather than papering over them.
5. **No target company analysis:** This skill ends when the reference layer is written to scratchpad. The target company is analyzed starting in SKILL 01.

---

## NEGATIVE EXAMPLES

**BAD:** "AI can reduce operational costs by 20-30% in most industries."
**GOOD:** "BPO utility billing automation benchmark (ARDEM, April 2025): AI-driven bill ingestion reduces manual processing FTE by 60% over 36 months in comparable managed services operations with >2,000 processing staff. Applied to labor-intensive billing operators."

**BAD:** "Several comparable companies exist in this space."
**GOOD:** "Comparables identified: (1) NWP Services — utility billing managed services, estimated $50-80M revenue (Crunchbase 2024), 200+ employees (LinkedIn 2024), no EBITDA disclosed. (2) Urjanet — utility data intelligence, acquired by Arcadia 2021 at $20M+ ARR (Crunchbase 2021). (3) Livable — multifamily utility billing, raised $14M Series A (TechCrunch 2022). Source and date recorded for each."

**BAD:** "The utility billing software market is growing rapidly."
**GOOD:** "Utility billing software TAM: $5.9B-$7.54B (IMARC Group 2025; Market.us December 2025), 7-10% CAGR. Growth driver: BTR sector expansion (NMHC 2025: BTR starts +34% YoY) and ESG reporting mandates. Headwind: property management platform consolidation (Yardi, RealPage) adding in-house billing capabilities. Sources are independent (IMARC and Market.us use different methodologies)."
