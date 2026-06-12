# Continuous Discovery Operator

A multi-phase AI operator that runs Teresa Torres' Continuous Discovery Habits workflow —
from defining a product outcome through extracting opportunities, ideating solutions,
and designing assumption tests.

Built on Jake van Clief's Interpretable Context Methodology (ICM). Each phase is its own
workspace with its own context, rules, and output spec.

---

## Folder Structure

```
discovery-triage-operator/
├── CLAUDE.md                              ← You are here. The map.
├── README.md                              ← Stranger-friendly guide
│
├── 01-outcome/                            ← Define the desired product outcome
│   ├── CONTEXT.md
│   └── docs/
│       └── outcome-framing.md
│
├── 02-interview/                          ← Assess interview quality + coach the PM
│   ├── CONTEXT.md
│   └── docs/
│       └── interview-quality.md
│
├── 03-opportunities/                      ← Extract, classify, route opportunities
│   ├── CONTEXT.md
│   ├── docs/
│   │   ├── classification-rubric.md
│   │   ├── opportunity-solution-tree.md
│   │   └── snapshot-template.md
│   └── examples/
│       └── babor-interviews.md
│
├── 04-solutions/                          ← Ideate solutions for PM-verified opportunities
│   ├── CONTEXT.md
│   └── docs/
│       └── solution-ideation.md
│
├── 05-experiments/                        ← Design assumption tests for solutions
│   ├── CONTEXT.md
│   └── docs/
│       └── assumption-testing.md
│
├── output/                                ← Where finished artifacts land
│   ├── tree.html                          ← The OST visualization (accumulates across phases)
│   ├── snapshots/                         ← Interview snapshots (from 03)
│   └── experiment-cards/                  ← Designed tests (from 05)
│
└── reference/                             ← Shared reference material
    └── babor-context.md                   ← Babor Beauty Group persona + domain context
```

---

## Navigation

| When the PM says... | Go to | The agent... |
|---------------------|-------|-------------|
| "Here's our goal" / "Our outcome is..." | `01-outcome/` | Validates the outcome is a product outcome, not a business metric. Stores it. |
| "I just did an interview" / pastes transcript | `02-interview/` | Assesses interview quality (story vs. opinion), produces coaching notes, then hands off to 03. |
| "Triage this" / "What opportunities are here?" | `03-opportunities/` | Extracts max 5 opportunities, classifies, routes. Produces snapshot + updates tree.html. |
| "Let's work on solutions for [opportunity]" | `04-solutions/` | Takes one PM-verified opportunity, generates 3+ solutions to compare. Updates tree.html. |
| "How do we test this?" / "Design experiments" | `05-experiments/` | Breaks solutions into assumptions, designs tests for the riskiest ones. Updates tree.html. |

---

## Cross-Workspace Flow

```
01-outcome         02-interview         03-opportunities       04-solutions        05-experiments
─────────────     ──────────────      ──────────────────     ───────────────     ────────────────
PM defines    →   PM pastes       →   Agent extracts     →   PM picks target →   Agent breaks
product           transcript          max 5 opportunities    opportunity,        solutions into
outcome                               per interview          agent generates     assumptions,
                  Agent assesses                             3+ solutions        designs tests
                  interview quality   Agent produces
                                      snapshot + updates     Agent updates       Agent updates
                  Coaching notes      tree.html              tree.html           tree.html
                  if needed
                                      ┌──────────────┐
                                      │ HUMAN GATE   │
                                      │ PM reviews    │
                                      │ opportunities,│
                                      │ verifies which│
                                      │ advance       │
                                      └──────────────┘
```

**The tree.html is the shared artifact.** Each phase adds to it. The PM always has one
visualization showing the current state of the tree.

---

## Naming Conventions

- Interview snapshots: `output/snapshots/YYYY-MM-DD-{segment}.md`
- Experiment cards: `output/experiment-cards/YYYY-MM-DD-{assumption}.md`
- The tree: `output/tree.html` (single file, updated by each phase)

---

## What This Operator Is NOT

- Not a chatbot. Each phase agent makes decisions and produces output. It does not ask
  the PM what to do — except at the human gate between opportunities and solutions.
- Not a product strategist. It triages, ideates, and designs tests. It does not set
  product direction. When something is big enough to change direction, it escalates.
- Not a replacement for interviews. It processes what the PM brings in. It coaches on
  interview quality but does not conduct interviews.

---

## Framework References

- Torres, Teresa. *Continuous Discovery Habits* (2021)
- [Opportunity Solution Trees — producttalk.org](https://www.producttalk.org/opportunity-solution-trees/)
- Van Clief, Jake. Interpretable Context Methodology — [Clief Notes](https://www.skool.com/cliefnotes)
