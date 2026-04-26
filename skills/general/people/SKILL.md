---
name: people
id: people
tier: A
description: Prepare for a 1:1 — agenda, follow-ups, feedback draft, and questions. Reads the person's file plus recent context.
tags: [people, meetings]
---

# People

Prepare for a 1:1. Given a person's name, read their file plus recent context, then produce an agenda, follow-ups, feedback (if relevant), and questions. Every line specific. No "how are things going" items.

---

## Read Before Writing

1. `people/<name>.md` — the person's file (try case-insensitive if exact match fails)
2. `weeks/*.md` (last 3 weeks) — recent context mentioning them
3. `meetings/*.md` — any meeting file where their name appears
4. `status.md` and `this_week.md` — open items that involve them
5. `strategy.md` — threads relevant to their role

If no `people/<name>.md` exists, say so, create a stub, and still proceed from whatever context is available.

---

## Output Format

### 1. Agenda (3-5 topics)

Each topic specific to what has changed since the last 1:1. Format:

```
- [Topic] — [why this topic now, in one sentence with a file reference]
```

Prioritize topics in this order:
1. Commitments either party made previously that are due or overdue
2. Signals from recent meetings/weeks that need discussion
3. Thread/strategy decisions that affect their scope
4. Career/growth topics if relevant

Omit topics that are routine or can be email.

### 2. Threads to follow up on

Specific past items — with file paths — that need explicit check-in. "Last Tuesday you said X in weeks/2026-03-30.md; has that resolved?"

### 3. Feedback draft (only if relevant)

Include this section only if there's specific evidence-based feedback to give. If there isn't, say so and skip the section.

Format:
```
**Context:** [specific incident or pattern, with file reference]
**Impact:** [what effect this had on you, the team, or the work]
**Ask:** [what you want to see next time]
```

No generic praise. No "keep up the good work." If you don't have a specific thing, skip.

### 4. Questions to ask

Aimed at surfacing what you don't know. Not test questions. Not leading questions. Examples of good framing:

- "What's a decision you made this week that you'd redo?"
- "What is the team saying about X that isn't making it into standups?"
- "Where are you spending time that isn't on your stated priorities?"

Max 3 questions. Each must plausibly surface new information.

---

## Discipline

- **Specificity test.** If a line could apply to any 1:1 with anyone, cut it.
- **Cite files.** Every agenda item, follow-up, and piece of feedback references a specific file.
- **Feedback is optional.** A 1:1 without feedback is fine. Generic feedback is worse than no feedback.
- **Question quality.** Three good questions beat seven mediocre ones.

---

## Few-shot Reference

If `examples/` exists alongside this skill with past 1:1 prep, read and match voice. If not, flag at top of output.
