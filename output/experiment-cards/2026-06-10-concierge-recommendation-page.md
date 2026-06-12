# Experiment Card: Concierge Test — Manual Recommendation Page

| Field | Content |
|-------|---------|
| **Date** | 2026-06-10 |
| **Assumption** | A1: Spa clients want their Derma Visualizer analysis results available on babor.com when they shop |
| **Category** | Desirability |
| **Priority** | 3 of 3 — run after feasibility and ethical gates pass |
| **Solution** | Digital Beauty Pass — Derma Visualizer syncs to BABOR & me account |
| **Opportunity** | Product recommendations from Derma Visualizer analysis exist only on paper (Beauty Pass), creating no digital bridge between spa consultation and online purchase |
| **Outcome** | Increase the percentage of spa clients who make their first online purchase within 30 days of an in-store treatment |

---

## Test Design

**What to do:** Wizard of Oz — simulate the Digital Beauty Pass experience without building any integration.

1. Recruit one willing partner spa (Frau Schmidt in Düsseldorf, or another partner)
2. After 5 consultations where Derma Visualizer is used, the partner (or a team member) manually creates a simple "Your Esthetician's Recommendations" email for each client
3. Email contains: the client's skin type summary (1-2 sentences), 2-3 recommended products with direct links to babor.com product pages, and the esthetician's name
4. Send within 2 hours of the appointment
5. Track: email open rate, click-through to product pages, purchase within 7 days

**What NOT to do:**
- Don't include a discount/voucher — that confounds the signal (are they clicking for the recommendation or the discount?)
- Don't send to clients who already bought products at the spa — we want to test the spa-to-online bridge, not upselling

---

## Success / Failure Criteria

| Metric | Confirm | Invalidate |
|--------|---------|------------|
| **Email open rate** | 3+ of 5 open (60%+) | Fewer than 2 open (under 40%) |
| **Click-through** | 2+ of 5 click a product link | Fewer than 1 clicks |
| **Purchase** | Any purchase within 7 days is strong signal | No purchases — but don't invalidate on this alone if clicks are high |

**Qualitative signal:** If any client replies to the email with a question, comment, or thank you — that's engagement signal worth noting even if they don't purchase.

---

## Time / Effort

Days. Requires:
- One willing partner spa
- 5 post-consultation clients (with email addresses and consent to contact)
- A simple email template (no design needed — plain text with product links)
- 7-day tracking window after the last email is sent

---

## If This Fails

If clients don't open or click:
- Check: was the email format wrong? (Maybe SMS would work better → supports Solution B)
- Check: was the timing wrong? (Maybe 2 hours is too soon, or too late)
- Check: was the content wrong? (Maybe they want the full skin analysis, not just product links)
- If desirability is genuinely low: the opportunity may need revalidation — go back to 03-opportunities and check whether the digital bridge is actually wanted, or whether the pain point is something else entirely
