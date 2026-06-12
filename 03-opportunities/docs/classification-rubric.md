# Classification Rubric

Quick-reference decision table for the triage operator.

---

## Step 1: Is This an Opportunity?

```
Interview statement
  │
  ├── Describes a customer experience (need, pain, desire)?
  │     → YES: Extract as opportunity → Step 2
  │
  ├── Requests a specific feature or solution?
  │     → REFRAME: Ask "what need does this serve?" → Extract the need
  │
  ├── Reports a bug or one-off technical issue?
  │     → PARK: Not an opportunity. Note for engineering if recurring.
  │
  ├── Describes an internal business constraint?
  │     → PARK: Not a customer opportunity. May be relevant to stakeholders.
  │
  └── Too vague to classify?
        → Tag [NEEDS FOLLOW-UP] + write a clarifying interview question
```

---

## Step 2: Classify

| Question | Options |
|----------|---------|
| What type? | Pain Point · Need · Desire |
| What journey phase? | Awareness · Evaluation · Purchase · Onboarding · Core Use · Support · Loyalty |
| How confident? | Strong (3+) · Moderate (2 or 1+behavior) · Emerging (1 first mention) |

---

## Step 3: Check Against Tree

| Situation | Decision |
|-----------|---------|
| Matches existing opportunity exactly | **MERGE** — add as supporting evidence |
| Related but adds new dimension | **EXTENDS** — add as child under parent |
| No match anywhere on tree | **NOVEL** — suggest tree position |
| Conflicts with existing evidence | **CONTRADICTION** — surface both sides, do not resolve |
| No tree provided | Skip — route on classification alone |

---

## Step 4: Route

| Route | Trigger |
|-------|---------|
| **ADD TO TREE** | Novel + moderate/strong confidence, OR emerging with strong story evidence from a Rich interview |
| **MERGE** | Confirms existing opportunity |
| **NEEDS MORE INTERVIEWS** | Emerging confidence, single data point |
| **NEEDS TECHNICAL INPUT** | Feasibility question (can we build this?) |
| **REFRAME** | Solution disguised as opportunity |
| **PARK** | Out of scope, too vague, or business constraint |
| **ESCALATE** | See escalation triggers below |

---

## Escalation Triggers (always escalate)

- Data privacy / GDPR / DSGVO concern
- Physical safety risk
- Would require abandoning current product outcome
- New customer segment not previously considered
- 2+ interviewees describe same critical failure
- Channel conflict or business model tension
- Ethical concern about how data or product is used
