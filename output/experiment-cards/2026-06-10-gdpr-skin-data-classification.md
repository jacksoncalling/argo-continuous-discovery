# Experiment Card: GDPR Skin Data Classification Check

| Field | Content |
|-------|---------|
| **Date** | 2026-06-10 |
| **Assumption** | A8: Sharing skin analysis data between spa partner systems and babor.com complies with GDPR/DSGVO |
| **Category** | Ethical |
| **Priority** | 2 of 3 — hard legal blocker if it fails |
| **Solution** | Digital Beauty Pass — Derma Visualizer syncs to BABOR & me account |
| **Opportunity** | Product recommendations from Derma Visualizer analysis exist only on paper (Beauty Pass), creating no digital bridge between spa consultation and online purchase |
| **Outcome** | Increase the percentage of spa clients who make their first online purchase within 30 days of an in-store treatment |

---

## Test Design

**What to do:** 30-minute consultation with Babor's Data Protection Officer (DPO) or legal team. One focused question: is Derma Visualizer output classified as "health data" under GDPR Article 9 (special category data)?

**Sub-questions:**
1. Does the 80x magnification skin scan constitute health-related data under Art. 9?
2. If yes, what consent mechanism is required to share it between an independent partner spa (data controller) and Babor corporate (babor.com, separate data controller)?
3. Does the existing BABOR & me loyalty program consent cover this data sharing, or is a separate consent required?
4. Would anonymizing the scan data (skin type classification only, no images) change the classification?

---

## Success / Failure Criteria

| Result | What it means |
|--------|--------------|
| **Confirm** | Skin analysis is NOT special category data, or existing consent mechanisms cover the sharing. Proceed with Solution A. |
| **Partial** | Special category data, but manageable with an explicit consent checkbox during account linking at the spa. Adds friction but doesn't kill the solution. |
| **Invalidate** | Art. 9 applies, and sharing between two separate data controllers (partner spa + Babor corporate) requires a legal framework that doesn't exist and would take months to establish. Solution A is blocked on legal infrastructure. |

---

## Time / Effort

Hours. One meeting with legal/DPO. No engineering work required.

---

## If This Fails

If GDPR blocks raw scan data sharing:
- Redesign: share only the product recommendations (not the scan data) — the esthetician's product selections are commercial data, not health data
- Redesign: keep scan data at the partner, share only a "recommendation token" linking to products
- Fall back to Solution B (SMS) or C (QR), which share product links rather than health data
