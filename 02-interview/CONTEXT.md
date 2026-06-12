# 02 — Interview Assessment

## What This Workspace Is

The quality gate. Before opportunities are extracted, the interview transcript is assessed
for how well it captured specific customer experiences. This is the learning system — it
coaches the PM to conduct better discovery interviews over time.

**Upstream:** PM pastes a transcript. Outcome must already be defined in `01-outcome/`.
**Downstream:** `03-opportunities/` receives the transcript with a quality rating attached.

---

## What to Load

| Task | Load These | Skip These |
|------|-----------|------------|
| Assess a new transcript | `docs/interview-quality.md`, the current product outcome | Solution/experiment docs |
| Review coaching notes | `docs/interview-quality.md`, prior snapshots in `output/snapshots/` | Everything else |

---

## The Process

1. Confirm a product outcome exists. If not → redirect to `01-outcome/`.
2. Read the full transcript before extracting anything.
3. Assess interview quality using the Story–Generalized–Opinion framework (see below).
4. Produce a one-line quality rating: **Rich**, **Mixed**, or **Thin**.
5. If Thin → add a coaching note with specific Torres-grounded advice.
6. Pass the transcript + quality rating to `03-opportunities/`.

### Story vs. Opinion Framework

Torres distinguishes between interviewing for **story** and interviewing for **opinion**.
The quality of the input determines the ceiling of the output.

**What to scan for in the transcript:**

| Signal in Transcript | Classification | Fidelity |
|---------------------|---------------|----------|
| Interviewee describes a specific, recent experience with concrete details — names, dates, sequences ("Last Tuesday I tried to order and...") | **Story-based** | High — grounded in something that actually happened |
| Interviewee gives a generalized account that blends multiple experiences ("Usually I...", "Most of the time...", "Whenever I...") | **Generalized** | Moderate — usable but less reliable, details are averaged |
| Interviewee offers opinions, predictions, or hypotheticals ("I think X would be good", "I would probably...", "You should...") | **Opinion-based** | Low — what people say they would do and what they actually do diverge |

**Also scan the interviewer's questions:**

| Question Pattern | Assessment |
|-----------------|------------|
| "Tell me about the last time you..." / "Walk me through what happened when..." / "What happened next?" | Good — invites specific story |
| "What do you usually do when...?" / "How do you typically...?" | Acceptable — invites generalized account, not ideal |
| "What do you think about...?" / "Would you use X?" / "How do you feel about...?" / "What would you want?" | Weak — invites opinion, not experience |

### Quality Rating

| Rating | Criteria | Effect on Downstream |
|--------|---------|---------------------|
| **Rich** | Transcript is mostly specific experiences with concrete details. Interviewer asked story-based questions. | Full confidence range available in 03-opportunities. |
| **Mixed** | Some specific stories, some generalized statements, possibly some opinion questions. | Confidence varies per opportunity. Story-sourced opportunities can reach Moderate; opinion-sourced capped at Emerging. |
| **Thin** | Mostly opinions, predictions, feature requests. Interviewer asked abstract questions. | All opportunities capped at Emerging regardless of cross-interview evidence. Flag for re-interview. |

### Coaching Notes

When the rating is **Thin**, produce a coaching note:

> **Interview coaching note:** This transcript contains mostly [opinions / feature requests /
> generalized statements] rather than specific experiences. Torres recommends asking
> "Tell me about the last time you [did X]" to get the interviewee into a specific story.
> When people answer abstract questions, they construct a narrative that blends multiple
> experiences — it drifts from reality.
>
> **Suggested re-interview prompt:** "You mentioned [specific thing from transcript]. Can you
> walk me through the last time that happened? What were you trying to do, and what
> actually happened?"

When the rating is **Mixed**, note which parts of the transcript were story-based (higher
value) and which were opinion-based (lower value), so 03-opportunities can weight accordingly.

### Interview Count Tracking

Torres requires **minimum 3-4 story-based interviews** before mapping the opportunity space.
Track how many interviews have been processed for the current outcome. If the PM has fewer
than 3, note:

> "This is interview [N] of the minimum 3-4 Torres recommends before mapping. The
> opportunity space will stabilize after more interviews. Opportunities extracted now
> are provisional."

---

## Skills & Tools

| Skill / Tool | When | Purpose |
|-------------|------|---------|
| Interview quality assessment | Every new transcript | Rate Rich/Mixed/Thin, produce coaching notes |
| Interview counter | Every new transcript | Track progress toward minimum 3-4 interviews |

---

## What NOT to Do

- Do not extract opportunities here. That is `03-opportunities/`'s job. This workspace only assesses quality.
- Do not judge the PM. Coaching notes are constructive, not critical. The goal is better interviews next time, not shame about this one.
- Do not reject a Thin transcript. Process it — but with confidence caps. Even opinion-based interviews contain signal. They just need follow-up validation.
- Do not rewrite the transcript. Work with what was said. Note quality issues, don't fix them retroactively.
