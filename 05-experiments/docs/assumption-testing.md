# Assumption Testing — Teresa Torres' Framework

## Why Assumptions, Not Solutions

Teams default to testing entire solutions: build a prototype, show it to users, see if
they like it. This is expensive and tests everything at once — if it fails, you don't
know which part failed.

Torres' approach: break the solution into its underlying assumptions, find the riskiest
one, and test THAT. Smaller test, faster signal, clearer learning.

## The Five Categories

| Category | Core Question | Failure Mode |
|----------|-------------|-------------|
| **Desirability** | Do customers want this? | They don't care, even if we build it perfectly |
| **Usability** | Can customers figure it out? | They want it but can't use it |
| **Feasibility** | Can we build this? | We want to build it but can't |
| **Viability** | Does it work for the business? | We can build it, customers want it, but it loses money or conflicts with strategy |
| **Ethical** | Should we build this? | We can and customers want it, but it causes harm |

Test desirability first in most cases. If customers don't want it, nothing else matters.

## Test Design Principles

**Smallest possible test.** What is the minimum you can do to get signal on this
assumption? A conversation, a landing page, a paper prototype, a Wizard of Oz test,
a concierge test, a data analysis.

**Clear success/failure criteria BEFORE running the test.** If you decide what counts
as success after seeing the results, you will rationalize whatever happened.

**One assumption per test.** If you're testing two things at once, a failure won't
tell you which assumption broke.

## Test Formats (from smallest to largest)

| Format | Time | Best For |
|--------|------|----------|
| **Interview question** | Minutes | Desirability — "Would this matter to you?" (caveat: opinion, not behavior) |
| **Data analysis** | Hours | Feasibility / Viability — "Does the data support this?" |
| **Paper prototype** | Hours | Usability — "Can they navigate this flow?" |
| **Landing page / fake door** | Days | Desirability — "Do they click?" (behavioral, not opinion) |
| **Wizard of Oz** | Days | Feasibility — "Can we deliver this manually before automating?" |
| **Concierge** | Days | Desirability + Usability — "Will they use it if we do it for them?" |
| **Coded prototype** | Week | Usability + Feasibility — "Does it work in practice?" |

## Connecting Back to the Tree

Every experiment maps to:
- One **assumption** (what we're testing)
- One **solution** (what the assumption belongs to)
- One **opportunity** (what the solution addresses)
- The **outcome** (what we're ultimately trying to change)

If any link in this chain breaks, the experiment is disconnected from value. The
tree visualization makes this chain visible.

## Source

Torres, Teresa. "Opportunity Solution Trees." producttalk.org.
> "Break your solutions down into their underlying assumptions."
> "Do a little more discovery than you think you need."
