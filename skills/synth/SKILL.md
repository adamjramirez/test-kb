---
name: synth
id: synth
tier: A
description: Weekly synthesis — surfaces patterns, stale items, contradictions, and next-week priorities across your full profile.
tags: [synthesis, review]
---

# Synth

Your weekly sensemaking partner. Read everything in the profile, then surface what's actually changing — patterns, stale threads, contradictions, novel signals. Produce a Friday-reflect-style synthesis you edit, not a summary you read.

**Note:** this skill reads the full profile tree. Run with a long-context model (Gemini 2.5 Pro or equivalent). Small-context models will truncate and miss cross-file patterns.

---

## Read Before Writing

Read every file in this order. Do not skim — the value is in connections across files.

1. `me.md` — stated self-knowledge; grounds all pattern analysis in what the user has said about themselves
2. `status.md` — what's active right now
3. `strategy.md` — operating model and all active threads
4. `forward-plan.md` — longer-term direction
5. `TODO.md` and `this_week.md` — open actions
6. `weeks/*.md` (last 4 weeks) — recent history
7. `meetings/*.md` (last 10 meetings) — recent interactions
8. `people/*.md` — relationship state
9. `projects/*.md` — active initiatives

If a file is missing, note it and continue. Don't invent context.

---

## Output Format

Produce markdown with these five sections, in this order:

### 1. Patterns
What's recurring across pods, people, or threads? Cite file paths and quote verbatim. Max 5 patterns. No generic observations ("engineers are learning AI" — too broad). A real pattern names the specific instance.

### 2. Stale items
Open TODOs or status rows that haven't moved in 2+ weeks. List them with the file they're in and the last date they were touched. Include why you think they're stuck, if evidence supports it.

### 3. Contradictions
Where new information conflicts with prior plans, decisions, or thread assumptions. Each contradiction: quote both sides, name the files, propose which side to resolve toward (or flag "needs your call").

### 4. Novel signals
What changed this week that wasn't in last week's reflect? Only include things that weren't already in prior `weeks/` files. This is the section most at risk of restating known state — be strict.

### 5. Priorities for next week
Maximum 3. Each priority must trace to a specific pattern, contradiction, or novel signal above. Not a todo list — a ranked bet on where your attention produces the most leverage next week.

---

## Discipline

- **Cite everything.** Every claim names a file. Unsourced claims get cut.
- **No flattery.** Don't say the team is doing great unless the data specifically shows it.
- **No restating.** If something is already in last week's reflect, don't repeat it unless it has evolved. Reference it and move on.
- **Honesty about gaps.** If the data is thin for a section, say so. "No contradictions surfaced this week" is a valid output.
- **This is a first draft to edit, not a report to read.** Write tight enough that the user sharpens it, not accepts it.

---

## Few-shot Reference

If `examples/` exists alongside this skill, read the examples there — these are past Friday reflects the user wrote. Match their voice and specificity. If no examples exist yet, proceed; flag at the top of output that no examples were available.
