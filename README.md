# Continuous Discovery Operator

A folder-based AI operator that runs Teresa Torres' Continuous Discovery Habits workflow —
from defining a product outcome through extracting opportunities, ideating solutions,
and designing assumption tests.

Built on Jake van Clief's [Interpretable Context Methodology](https://www.skool.com/cliefnotes) (ICM).
Each phase of work is its own workspace with its own context, rules, and output format.

**[Watch the demo →](https://youtu.be/rrZadXp5u40)**

---

## What This Does

You bring your discovery work — a business goal, interview transcripts, decisions about
which opportunities to pursue — and the operator handles each phase:

1. **Outcome** — helps you shape a business goal into a product outcome you can discover against
2. **Interview Assessment** — reads your transcript and tells you how well it captured specific experiences vs. abstract opinions. Coaches you on better interviewing.
3. **Opportunity Extraction** — extracts max 5 opportunities per interview, classifies each, and routes them (add to tree, merge, needs more interviews, escalate, park)
4. **Solution Ideation** — takes the opportunity you choose and generates 3+ distinct solutions to compare
5. **Assumption Testing** — breaks solutions into assumptions, designs the smallest test for the riskiest one

The operator produces an **interactive HTML tree** (`output/tree.html`) that accumulates
across all phases — one visualization showing your outcome, opportunities, solutions, and
experiments as they build up over time.

It does not ask you what to do. It reads the input, makes the call, explains its reasoning,
and teaches you the framework along the way.

---

## Quick Start

### Option A: Claude Project (Recommended)

1. Create a new Claude Project
2. Upload this entire folder to the project's knowledge base
3. In the project instructions, write:

   ```
   Read CLAUDE.md first. You are this operator. Follow the workspace
   routing in the navigation table. Start with 01-outcome if no
   outcome has been defined.
   ```

4. Start with: "Our goal this quarter is [your business goal]"

### Option B: Claude Code

1. Clone this repo
2. Open the folder in Claude Code
3. Start with: "Our goal this quarter is [your business goal]"
4. Then paste interview transcripts and say: "Triage this interview"

### Option C: Any AI Assistant

1. Copy `CLAUDE.md` into your system prompt — it's the map
2. When working on a specific phase, also load that phase's `CONTEXT.md`
3. Reference `03-opportunities/examples/babor-interviews.md` for calibration

---

## Try It Right Now

Paste this into your first message after setup:

> Our quarterly goal is to increase online revenue by 10%. Here's a transcript
> from an interview I did with a customer yesterday...

The operator will:
1. Help you reframe "increase online revenue" into a product outcome (01-outcome)
2. Assess your interview quality — did you ask about specific experiences or opinions? (02-interview)
3. Extract and classify the top opportunities from the transcript (03-opportunities)
4. Wait for you to choose which opportunity to pursue before generating solutions (04-solutions)

---

## What's in the Folder

```
discovery-triage-operator/
├── CLAUDE.md                              ← The map — folder structure, navigation, flow
├── README.md                              ← You are here
│
├── 01-outcome/                            ← Define the desired product outcome
│   ├── CONTEXT.md                         ← Learning conversation: business goal → product outcome
│   └── docs/
│       └── outcome-framing.md             ← Torres' criteria for good outcomes
│
├── 02-interview/                          ← Assess interview quality + coach the PM
│   ├── CONTEXT.md                         ← Story vs. opinion assessment framework
│   └── docs/
│       └── interview-quality.md           ← Torres' interview quality criteria
│
├── 03-opportunities/                      ← Extract, classify, route opportunities
│   ├── CONTEXT.md                         ← The extraction engine — max 5 per interview
│   ├── docs/
│   │   ├── classification-rubric.md       ← Quick-reference decision table
│   │   ├── opportunity-solution-tree.md   ← Torres OST framework reference
│   │   └── snapshot-template.md           ← Output format for interview snapshots
│   └── examples/
│       └── babor-interviews.md            ← Three worked examples with edge cases
│
├── 04-solutions/                          ← Ideate solutions for PM-verified opportunities
│   ├── CONTEXT.md                         ← 3+ solutions per target opportunity
│   └── docs/
│       └── solution-ideation.md           ← Torres' solution comparison framework
│
├── 05-experiments/                        ← Design assumption tests for solutions
│   ├── CONTEXT.md                         ← Break solutions into testable assumptions
│   └── docs/
│       └── assumption-testing.md          ← Torres' assumption mapping framework
│
├── output/                                ← Where finished artifacts land
│   ├── tree.html                          ← Interactive OST visualization (accumulates)
│   ├── snapshots/                         ← Interview snapshots (one per interview)
│   └── experiment-cards/                  ← Designed tests (one per assumption)
│
└── reference/
    └── babor-context.md                   ← Reference persona: Babor Beauty Group PM
```

---

## The Workflow

```
┌─────────────┐    ┌──────────────┐    ┌──────────────────┐    ┌───────────────┐    ┌────────────────┐
│ 01-outcome   │    │ 02-interview  │    │ 03-opportunities  │    │ 04-solutions   │    │ 05-experiments  │
│              │    │               │    │                    │    │                │    │                 │
│ PM brings    │ →  │ PM pastes     │ →  │ Agent extracts     │ →  │ PM picks ONE   │ →  │ Agent breaks    │
│ business     │    │ transcript    │    │ max 5 opps,        │    │ opportunity,   │    │ solutions into  │
│ goal         │    │               │    │ classifies,        │    │ agent generates│    │ assumptions,    │
│              │    │ Agent rates   │    │ routes each        │    │ 3+ solutions   │    │ designs tests   │
│ Agent helps  │    │ quality:      │    │                    │    │ to compare     │    │ for riskiest    │
│ reframe into │    │ Rich/Mixed/   │    │ Produces snapshot  │    │                │    │                 │
│ product      │    │ Thin          │    │ + updates tree     │    │ Updates tree   │    │ Updates tree    │
│ outcome      │    │               │    │                    │    │                │    │                 │
└─────────────┘    │ Coaches PM    │    │  ┌─────────────┐   │    └───────────────┘    └────────────────┘
                    │ on better     │    │  │ HUMAN GATE  │   │
                    │ interviewing  │    │  │ PM reviews  │   │
                    └──────────────┘    │  │ & verifies  │   │
                                        │  └─────────────┘   │
                                        └──────────────────┘
```

**The tree.html is the shared artifact.** Each phase adds to it. You always have one
visualization showing the current state of your Opportunity Solution Tree.

---

## The Learning System

This operator doesn't just process your inputs — it helps you get better at discovery:

- **Outcome phase:** If you bring a business metric, it explains why that doesn't work
  for discovery and walks you through reframing it into a product outcome
- **Interview phase:** If your transcript is mostly opinions instead of specific
  experiences, it tells you — with Torres' language — how to ask better questions next time
- **Opportunity phase:** Confidence scores are capped by interview quality. Three weak
  interviews don't equal one good one. This creates a natural incentive to improve
  your interviewing
- **Solution phase:** You must choose which opportunity to pursue. The agent won't
  brainstorm across the whole tree — Torres says focus on one target, and the operator
  enforces that

---

## Reference Example: Babor Beauty Group

The worked examples use a Product Manager at **BABOR BEAUTY GROUP** — a vertically
integrated German cosmetics company (own R&D, production, retail, spas, e-commerce,
professional partner network, and Private Label services). She interviews across the
entire value chain: end consumers, beauty professionals, internal teams, and B2B clients.

This context was chosen because Babor's channel complexity creates real tension in
discovery — opportunities that look like product improvements sometimes turn out to be
channel conflicts requiring escalation. See `03-opportunities/examples/babor-interviews.md`
for three worked examples:

1. **Standard triage** — spa manager interview with multiple opportunities extracted and routed
2. **Solution-only interview** — gift buyer who only gives feature requests, every statement reframed
3. **Contradiction + escalation** — independent esthetician whose needs directly conflict with Example 1

---

## Customizing for Your Product

This operator is domain-agnostic. The Babor examples demonstrate the framework, but the
rules work for any product team doing continuous discovery.

To adapt:

1. Start a conversation with your business goal — the operator helps you shape it
2. Optionally provide your current Opportunity Solution Tree so the operator can check
   for duplicates and contradictions
3. Adjust the customer journey phases in `03-opportunities/CONTEXT.md` if your journey
   has different stages
4. Add domain-specific escalation triggers if your industry has specific compliance
   requirements
5. Replace `reference/babor-context.md` with your own company context if you want
   domain-aware triage

---

## Edge Cases Handled

See `03-opportunities/examples/babor-interviews.md` for these in action:

- **Solution-only interviews** — customer gives only feature requests. The operator
  reframes every statement into the underlying need.
- **Contradictions between segments** — two interviewees experience the same feature as
  opposite things. The operator surfaces both without resolving.
- **Channel conflicts** — an opportunity reveals a business model tension above the product
  team's scope. The operator escalates with clear reasoning.
- **Thin interviews** — transcript is mostly opinions. Confidence capped at Emerging,
  coaching note provided.
- **Vague statements** — tagged `[NEEDS FOLLOW-UP]` with a specific question for next time.
- **Out-of-scope opportunities** — parked with a reason, never discarded.

---

## Framework References

- Torres, Teresa. *Continuous Discovery Habits* (2021)
- [Opportunity Solution Trees — producttalk.org](https://www.producttalk.org/opportunity-solution-trees/)
- Van Clief, Jake. Interpretable Context Methodology — [Clief Notes](https://www.skool.com/cliefnotes)

---

## What's Next

### Multi-Outcome Support

Right now, one operator instance runs one outcome — one tree. That matches how Torres
works (focus on one target), but real teams and consultants juggle multiple products,
outcomes, or clients.

The natural evolution is to separate the **methodology** (the five phases) from the
**outcome state** (tree, snapshots, experiment cards):

```
discovery-triage-operator/
├── CLAUDE.md                        ← Shared map
├── phases/                          ← Reusable methodology (01–05)
├── babor-spa-to-online/             ← Outcome A — own tree, own snapshots
│   ├── CONTEXT.md
│   └── output/
├── babor-partner-retention/         ← Outcome B — own tree, own snapshots
│   ├── CONTEXT.md
│   └── output/
```

This matters because the alternative — duplicating the entire folder per product —
creates drift. When the methodology improves (better classification rubric, sharper
coaching prompts), those improvements need to propagate to every instance. A shared
`phases/` folder keeps the framework canonical while each outcome evolves independently.

### Cross-Outcome Learning

Multiple outcomes running in parallel create a second opportunity: learning *across*
discovery streams. Patterns that surface in one product's interviews may apply to another.
A channel conflict escalated in one tree may already be solved in another.

This is where the `/compound` skill fits — extracting reusable learnings from completed
discovery cycles and feeding them back into the shared methodology. Not just "what did we
discover" but "what did the process of discovering teach us about how to discover better."

---

## About

Built by Joshua Baker for [Clief Notes Weekly Challenge #7: The Operator](https://www.skool.com/cliefnotes).

This operator handles the continuous discovery workflow that most product teams either
skip (losing insights), do inconsistently (biasing toward recent interviews), or never
learn from (same interview mistakes repeated). It makes the triage systematic, the
decisions auditable, and the interviewing better over time — while preserving the human
judgment that continuous discovery requires.
