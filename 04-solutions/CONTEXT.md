# 04 — Solution Ideation

## What This Workspace Is

Takes a single PM-verified opportunity and generates at least 3 distinct solutions to
compare. Torres is explicit: "Don't brainstorm solutions across your entire tree. The
goal is to focus on your target opportunity."

**Upstream:** The PM reviews opportunities from `03-opportunities/` and selects ONE target
opportunity to work on. Only PM-verified opportunities enter this phase.
**Downstream:** Solutions are added to `output/tree.html` under the target opportunity.
The PM selects which solution(s) to test → `05-experiments/`.

---

## What to Load

| Task | Load These | Skip These |
|------|-----------|------------|
| Ideate solutions for a target opportunity | `docs/solution-ideation.md`, the target opportunity card, current `output/tree.html`, relevant snapshots from `output/snapshots/` | Interview quality docs, experiment docs |
| Compare solutions | `docs/solution-ideation.md`, the generated solution set | Everything else |

---

## The Process

### The Human Gate

This phase only activates after the PM has reviewed the opportunity board and explicitly
chosen a target opportunity. The agent does not pick which opportunity to solve — that is
the PM's strategic decision.

**If the PM says "work on solutions" without specifying an opportunity:** Ask which one.
This is the one place in the system where the agent asks the PM to decide, because
prioritization is a human judgment call.

### Step 1: Understand the Opportunity

Before generating solutions, restate the opportunity in full:
- What is the unmet need, pain point, or desire?
- Which customer segment experiences it?
- What evidence supports it? (link to snapshot quotes)
- Where does it sit on the tree?

### Step 2: Generate 3+ Solutions

Torres: "Compare and contrast at least 3 different solutions for your target opportunity."
Research shows comparison produces better decisions than evaluating solutions one at a time.

Each solution must be:
- **Distinct** — not variations of the same idea
- **Feasible to describe** — concrete enough to evaluate, not just a label
- **Framed as what it would do for the customer** — not as a technical spec

A solution can be "a product, a feature, a service, a workflow, a process, documentation,
or anything else" that addresses the opportunity (Torres).

### Step 3: Present for Comparison

For each solution, provide:

| Field | Content |
|-------|---------|
| **Solution name** | Short, descriptive label |
| **What it does** | 1-2 sentences from the customer's perspective |
| **How it addresses the opportunity** | Direct link back to the need/pain/desire |
| **Key assumption** | The riskiest thing that must be true for this to work |
| **Transcript evidence** | Quote(s) from snapshots that support or challenge this approach |

### Step 4: Update the Tree

Add the generated solutions as nodes under the target opportunity in `output/tree.html`.
Color-code them to match the opportunity's branch color (as shown in the Vistaly reference).

---

## Skills & Tools

| Skill / Tool | When | Purpose |
|-------------|------|---------|
| Solution ideation framework | Every ideation session | Structure the 3+ solution comparison |
| Tree update | After solutions generated | Add solution nodes to tree.html |

---

## What NOT to Do

- Never ideate solutions without a PM-verified target opportunity
- Never generate only one solution. The minimum is 3 — comparison is the point.
- Never include effort estimates. Effort belongs to implementation planning, not discovery. Torres: "Don't rule out an opportunity too early."
- Never skip the transcript evidence. Solutions must trace back to what customers actually said.
- Never resolve which solution is "best." Present the comparison. The PM and team decide.
