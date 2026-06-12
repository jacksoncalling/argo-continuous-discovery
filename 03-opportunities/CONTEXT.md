# 03 — Opportunity Extraction

## What This Workspace Is

The engine. Takes an interview transcript (with quality rating from `02-interview/`) and
extracts, classifies, and routes opportunities. Produces two outputs: an interview snapshot
and an update to the shared tree visualization.

**Upstream:** `02-interview/` passes a transcript with quality rating (Rich/Mixed/Thin).
**Downstream:** `output/snapshots/` gets the snapshot. `output/tree.html` gets updated.
The PM reviews opportunities at the **human gate** before anything moves to `04-solutions/`.

---

## What to Load

| Task | Load These | Skip These |
|------|-----------|------------|
| Triage a single interview | `docs/classification-rubric.md`, `docs/snapshot-template.md`, current outcome, quality rating from 02 | Solution/experiment docs |
| Triage a batch | Same as above + prior snapshots in `output/snapshots/` for cross-interview comparison | Solution/experiment docs |
| Check against existing tree | `docs/opportunity-solution-tree.md`, current `output/tree.html` | Solution/experiment docs |

---

## Folder Structure

```
03-opportunities/
├── CONTEXT.md                 ← You are here
├── docs/
│   ├── classification-rubric.md    ← Quick-reference decision table
│   ├── opportunity-solution-tree.md ← Torres OST framework reference
│   └── snapshot-template.md         ← Output format for interview snapshots
└── examples/
    └── babor-interviews.md          ← Three worked examples (standard, solution-only, escalation)
```

---

## The Process

### Step 1: Extract Opportunities (max 5 per interview)

Read the transcript line by line. For every statement describing a customer experience, ask:

**"Is there more than one way to address this?"**

- **Yes** → it is an opportunity. Extract it.
- **No** → it is a solution disguised as an opportunity. Reframe it into the underlying need.

**Reframe pattern:**
- Customer says: "[specific feature request]"
- You extract: the unmet need behind it
- You note: the original suggestion as a "solution signal" (not discarded — it may inform 04-solutions later)

**What qualifies:**

| Qualifies | Does Not Qualify |
|-----------|-----------------|
| A need the customer expressed | A feature the customer requested (reframe it) |
| A pain point in their current workflow | A vague complaint without context (tag `[NEEDS FOLLOW-UP]`) |
| A desire they articulated | An internal business constraint (park it) |
| A gap between expectation and reality | A one-off technical bug report (park for engineering) |

**The max-5 rule:** Extract all opportunities you find, then rank by relevance to the
current product outcome. Present the top 5 in the snapshot. If more than 5 exist, list
the remainder in a "Parked" section with one-line reasons — they are not discarded, just
deprioritized. The PM can promote any parked opportunity.

**Vague statements:** When a statement is too vague to act on, do not discard it. Tag as
`[NEEDS FOLLOW-UP]` with a specific question for the next interview.

### Step 2: Classify Each Opportunity

Each opportunity gets three labels:

**Type** (exactly one): Pain Point / Need / Desire
**Journey Phase** (exactly one): Awareness / Evaluation / Purchase / Onboarding / Core Use / Support / Loyalty
**Confidence** (exactly one): Strong / Moderate / Emerging

See `docs/classification-rubric.md` for the full decision table.

**Confidence is capped by interview quality:**

| Interview Rating | Max Confidence |
|-----------------|---------------|
| Rich | Strong (if cross-interview evidence supports) |
| Mixed | Moderate for story-sourced, Emerging for opinion-sourced |
| Thin | Emerging for all, regardless of cross-interview volume |

### Step 3: Check Against Existing Tree

Compare every opportunity against `output/tree.html` (if it exists):

| Situation | Decision |
|-----------|---------|
| Matches existing opportunity | **MERGE** — add interview as supporting evidence |
| Related but adds new dimension | **ADD AS CHILD** under existing parent |
| No match anywhere | **NOVEL** — suggest tree position |
| Contradicts existing evidence | **SURFACE BOTH SIDES** — do not resolve |
| No tree exists yet | Skip — route on classification alone |

### Step 4: Route Each Opportunity

Every opportunity gets exactly one route:

| Route | When | Output |
|-------|------|--------|
| **ADD TO TREE** | Novel, relevant to outcome, confidence is Moderate+ OR Emerging with strong story evidence | Opportunity card with suggested tree position |
| **MERGE** | Confirms or extends existing opportunity | Reference to existing node + new evidence |
| **NEEDS MORE INTERVIEWS** | Emerging confidence, interesting but single data point | Opportunity card + suggested follow-up question |
| **NEEDS TECHNICAL INPUT** | Feasibility question the product team can't answer | Opportunity card + specific question for engineering |
| **REFRAME** | Solution disguised as opportunity | Original statement + reframed need + solution noted separately |
| **PARK** | Outside current outcome scope, or too vague after reframing | Card parked with reason. Never discarded. |
| **ESCALATE** | See escalation triggers below | Card + escalation reason + who should review |

**Escalation triggers (always escalate, no exceptions):**
- Data privacy / GDPR / DSGVO concern
- Physical safety risk
- Would require abandoning current product outcome
- New customer segment not previously considered
- 2+ interviewees describe same critical failure
- Channel conflict or business model tension
- Ethical concern about how data or product is used

### Step 5: Produce the Snapshot

Follow `docs/snapshot-template.md`. One page max. Must contain:
- Interview quality rating (from 02-interview)
- Interviewee profile (role, segment, context — no PII)
- Experience map (the story they told, step by step)
- Top 5 opportunities with classification and routing
- Solution signals (noted, not acted on)
- One memorable quote
- Follow-up questions for next interview
- Coaching note (if interview was Mixed or Thin)

Save to `output/snapshots/YYYY-MM-DD-{segment}.md`.

### Step 6: Update the Tree

Add new opportunities to `output/tree.html`. Color-code by branch. The tree accumulates
across interviews — each new interview adds evidence or new nodes.

### Step 7: Batch Processing (multiple interviews)

When given multiple transcripts at once:
1. Process each independently first (one snapshot per interview)
2. Produce a batch summary: which opportunities appeared in multiple interviews (confidence upgrade), contradictions, emerging patterns
3. Update confidence levels based on cross-interview evidence

---

## Skills & Tools

| Skill / Tool | When | Purpose |
|-------------|------|---------|
| Classification rubric | Every extraction | Quick-reference for type/phase/confidence decisions |
| Snapshot template | After extraction | Structured output format |
| Tree update | After every triage | Add nodes to the HTML visualization |

---

## What NOT to Do

- Never suggest solutions. You extract opportunities. Solutions are `04-solutions/`'s job.
- Never resolve contradictions. Surface both sides. The team investigates.
- Never discard data. Even irrelevant opportunities get parked with a reason.
- Never ask the PM what to do with an opportunity. Make the routing call. If the rules don't cover it, default to PARK with a note explaining why and what context would help.
- Never skip the interview quality cap. Three thin interviews do not equal one rich one.
- Never extract more than 5 without ranking. The PM needs a decision-ready list, not a dump.
