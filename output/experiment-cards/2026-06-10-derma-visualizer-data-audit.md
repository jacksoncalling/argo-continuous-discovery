# Experiment Card: Derma Visualizer Data Audit

| Field | Content |
|-------|---------|
| **Date** | 2026-06-10 |
| **Assumption** | A3: The Derma Visualizer outputs structured data that can be mapped to babor.com product SKUs |
| **Category** | Feasibility |
| **Priority** | 1 of 3 — riskiest assumption, test first |
| **Solution** | Digital Beauty Pass — Derma Visualizer syncs to BABOR & me account |
| **Opportunity** | Product recommendations from Derma Visualizer analysis exist only on paper (Beauty Pass), creating no digital bridge between spa consultation and online purchase |
| **Outcome** | Increase the percentage of spa clients who make their first online purchase within 30 days of an in-store treatment |

---

## Test Design

**What to do:** Obtain a sample Derma Visualizer export from one partner spa. Examine the output format. Separately, pull the babor.com product catalog taxonomy. Attempt to map Visualizer output fields to product categories/SKUs.

**Questions to answer:**
1. Does the Visualizer export structured fields (skin type, hydration level, oil level, sensitivity, concern indicators)?
2. Or does it produce only raw images / unstructured PDF reports?
3. If structured: do the skin classifications correspond to product categories in the babor.com catalog?
4. If unstructured: could the esthetician's manual product translation be captured as structured metadata alongside the scan?

---

## Success / Failure Criteria

| Result | What it means |
|--------|--------------|
| **Confirm** | Visualizer exports structured data with skin classifications that map to product categories. The data bridge is technically possible. |
| **Partial** | Visualizer has some structured fields but not enough for automatic product mapping. A hybrid approach (structured scan + esthetician input) could work. |
| **Invalidate** | Visualizer produces only images/PDFs. The product recommendation is entirely tacit knowledge in the esthetician's head. Solution A needs re-architecture — or falls back to Solution B/C. |

---

## Time / Effort

Hours. Requires:
- Access to one Derma Visualizer export file (ask Frau Schmidt or another partner)
- babor.com product catalog schema or category taxonomy
- One technical person to assess data format compatibility

---

## If This Fails

If the Visualizer can't produce structured data, Solution A as designed doesn't work. Options:
- Redesign: partner manually selects products in a digital tool (structured input at consultation time) rather than syncing scan data
- Fall back to Solution B (SMS link) or Solution C (QR code), which don't require scan data integration
- Investigate whether the AI Hautanalyse (online tool) could serve as the bridge instead of the in-spa Visualizer
