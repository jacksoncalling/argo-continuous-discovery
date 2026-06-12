# 05 — Assumption Testing

## What This Workspace Is

The validation layer. Takes solutions from `04-solutions/` and breaks them down into
underlying assumptions, then designs the smallest possible test for the riskiest
assumption. The goal is to learn whether a solution will work before building it.

**Upstream:** PM selects which solution(s) to test from the comparison in `04-solutions/`.
**Downstream:** Experiment cards saved to `output/experiment-cards/`. Tree updated.

---

## What to Load

| Task | Load These | Skip These |
|------|-----------|------------|
| Design experiments for a solution | `docs/assumption-testing.md`, the solution card, the parent opportunity card, relevant snapshots | Interview/outcome docs |
| Review experiment results | `docs/assumption-testing.md`, the experiment card, the solution it tests | Everything else |

---

## The Process

### Step 1: Map Assumptions

For the selected solution, list every assumption that must be true for it to work.
Categorize each:

| Category | Question | Example |
|----------|---------|---------|
| **Desirability** | Do customers want this? | "Spa clients want digital recommendation cards" |
| **Usability** | Can customers figure it out? | "Gift buyers can complete the simplified quiz in under 60 seconds" |
| **Feasibility** | Can we build this? | "We can integrate Derma Visualizer data with the online shop" |
| **Viability** | Does the business model support it? | "Attribution tracking won't create channel conflicts with partners" |
| **Ethical** | Should we do this? | "Tracking client purchases across channels respects privacy expectations" |

### Step 2: Prioritize by Risk

Rank assumptions by: how confident are we that this is true? The least confident
assumption is the one to test first. If that assumption fails, the solution fails —
no point testing the others.

Torres: "Test riskiest assumptions across all three ideas." If comparing 3 solutions,
test the riskiest assumption of EACH — don't go deep on one solution before checking
the others.

### Step 3: Design the Smallest Test

For each assumption to test, design an experiment:

| Field | Content |
|-------|---------|
| **Assumption** | What must be true (one sentence) |
| **Category** | Desirability / Usability / Feasibility / Viability / Ethical |
| **Test** | What will you do to test it? (specific action) |
| **Evidence needed** | What result would confirm the assumption? What would invalidate it? |
| **Time/effort** | How long will this take? (hours, not weeks — keep tests small) |
| **Solution it validates** | Which solution from 04 does this test? |

### Step 4: Produce Experiment Cards

Save each experiment as a card in `output/experiment-cards/YYYY-MM-DD-{assumption}.md`.
Update `output/tree.html` — experiments appear as the bottom layer of the tree, under
their parent solution.

### When to Ship vs. When to Test More

Torres notes this depends on three factors:
- **Solution risk level** — how costly is it to be wrong?
- **Organizational risk tolerance** — how much uncertainty can the team absorb?
- **Available time** — pressure to ship vs. pressure to learn

For teams new to discovery: "Do a little more discovery than you think you need."

---

## Skills & Tools

| Skill / Tool | When | Purpose |
|-------------|------|---------|
| Assumption mapping | Every solution selected for testing | Break solution into testable assumptions |
| Experiment card template | After prioritization | Structured output for each test |
| Tree update | After experiment design | Add experiment nodes to tree.html |

---

## What NOT to Do

- Never test all assumptions at once. Prioritize by risk. If the riskiest fails, the rest are moot.
- Never design experiments that take weeks. If a test can't produce signal in days, it's too big — break it down further.
- Never skip back to the solution level. If an assumption fails, the solution may need rethinking — go back to `04-solutions/`, not forward to building.
- Never declare a solution "validated" from one experiment. Assumptions reduce risk incrementally. Multiple tests may be needed.
