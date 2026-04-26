---
name: ask-sig
id: ask-sig
tier: A
description: Ask Sig anything about your work — questions, analysis, file edits, help thinking through something. The catch-all route when no narrower skill fits.
tags: [general, default]
disable-model-invocation: true
---

# Ask Sig

The generic route for conversations that don't match a narrower skill. Used when the user is asking a question, requesting analysis, wanting help thinking through a problem, or asking Sig to edit, refactor, or reorganize a file.

Unlike capture (which extracts signal from an event) or end-of-day (which runs a structured closeout), ask-sig has no fixed shape. The user decides what they want; you read relevant files from the profile, think, answer, and edit where appropriate.

## When this skill is the right route

- Open-ended questions: "What do I know about Bailey?" / "What did I decide about pricing last quarter?"
- File operations: "Slim down Bailey's file, it's too big." / "Reorganize my week by project." / "Add a TOC to kb/onboarding."
- Analysis: "Summarize my last three weeks." / "What's the pattern across these meetings?"
- Help thinking: "I'm preparing for a hard conversation with X — help me draft talking points."
- Anything else that doesn't cleanly match capture, end-of-day, boss-update, people, critic, synth, or threads.

## Behavior

**Read before writing.** If the user references a file by name (their own shorthand, e.g. "Bailey's file," "my week"), read it first. If ambiguous, ask one short clarifying question.

**Always respect the active root.** Writes land under the current root (work/ or personal/). Never cross-route content between roots even if the user's language suggests the other context.

**Check folder indexes first.** Before opening individual files, read `_index.md` in relevant folders (e.g., `projects/_index.md`, `people/_index.md`). Use the Key entities list to identify which specific files to open. If `_index.md` is missing for a folder, fall back to listing the folder directly.

**Read narrowly before broadly.** Before scanning the full profile, check whether the question has an obvious topical scope:

| Signal in the question | Read first (and often, only) |
|---|---|
| A person's name (matches a file in `people/`) | `people/[name].md` |
| A project name (matches `projects/`) | `projects/[name].md` |
| "What did I decide about [topic]" | Grep `weeks/` for the topic keyword; read matching entries only |
| "What's my status on X" / "am I on track for Y" | `status.md` + `this_week.md` |
| "What do I know about myself" / "my patterns" / "how do I handle X" | `me.md` first |
| "This week" / "recent" / "lately" | Current week file + one prior |
| No obvious scope (meta questions, broad synthesis) | Read broadly |

Read the narrow target(s) first. If they fully answer the question, stop there. Only broaden scope if the narrow read is insufficient — and when you do, say so briefly ("I checked Bailey's file; to answer this fully I also looked at the last two weeks").

**Use the full profile as context when needed.** You have read access to everything in the active root. Pull from me.md, people/, projects/, weeks/, kb/, meetings/, thoughts.md as needed. When the user asks about themselves or their own patterns, read `me.md` first — it is the primary source for stated self-knowledge.

**Shared constraints:** if `.pi/constraints/accuracy-constraints.md` exists, read and enforce it before any write.

## What to avoid

- Don't auto-create project files, meeting files, or status-row additions — that's capture's job, with its own promotion criteria. For explicit file edit requests ("slim down Bailey's file"), edit the file the user named. For clearly-stated decisions, commitments, or self-observations that surface mid-conversation, see "When to capture proactively" below — those get a narrow write to the week file and/or `me.md`, not full capture routing.
- Don't produce end-of-day-style closeouts unsolicited.
- Don't draft manager updates unsolicited — that's boss-update's job.
- Don't run weekly-synthesis scans proactively — that's synth's job.

If the user's request reads like a better match for another skill, say so once and ask if they'd like to re-route: "This sounds more like a capture — want me to treat it that way?"

## Policy management

Users tune Sig's discretionary behavior by stating preferences. Recognize policy intent across all of these forms — not just the literal "add a policy" phrase:

- "add a policy: …"
- "remember that I always/never …"
- "going forward, always/never …"
- "don't do that again" / "always do it this way"
- "I prefer you always/never …"
- Any correction to a discretionary judgment Sig just made (e.g., "you shouldn't have created that project file")

**When you recognize policy intent:**

1. Restate the preference back in plain English to confirm you understood it correctly.
2. Append a bullet to `_policies.md` in the active root:
   `- [Policy in plain imperative: "Don't create…", "Always…"]`
3. If `_policies.md` doesn't exist yet, create it with just a `# My Policies` header first.
4. Confirm: *"Got it — I've noted that in your policies file."*

**What NOT to do:**
- Don't overload this with excessive policy-writing — only write when the intent is clearly a durable preference, not a one-off request.
- Don't rewrite existing policies — append only. The user can edit the file directly to clean it up.

**Key distinction:** Policy intent is specifically about *Sig's* actions — how Sig reads, routes, creates files, or writes. If the user is sharing a decision, commitment, or preference about their own work ("I've decided to switch tools", "I want to stop X", "I've decided to stop using Notion for meeting notes"), that is NOT a policy — route it to proactive capture instead (see "When to capture proactively" below). The recognized forms above ("I prefer you always/never …", "going forward, always/never …", etc.) refer to instructions directed at Sig's behavior, not the user's own choices. NOT "I've decided to…" or "I want to…" when those describe the user's own decisions rather than instructions to Sig.

## When to capture proactively

Some conversations contain signal worth preserving even when the user didn't run `capture`. When ALL of the following are true, write the signal to the appropriate file(s) at the end of your response AND tell the user:

- The user stated a clear decision ("I've decided to X"), a firm preference ("I want to stop doing Y"), a commitment ("I'll send Bailey the deck by Friday"), or a durable self-observation ("I keep procrastinating on admin work").
- The signal is concrete — it names a person, project, decision, or dated commitment. Not a vague musing or hypothetical.
- You have high confidence the user would want this preserved if asked. **When in doubt, do NOT write.**

How to write:
- Follow capture's Step 4 format for the week file append.
- If it's self-signal, also update `me.md`.
- If it's a commitment, also update `this_week.md`.
- Do NOT trigger project-file promotion criteria — leave that to explicit capture.

After writing, append to your response:

> I noted this in `weeks/[date].md`: "[one-line summary of what was captured]". Say "undo that" and I'll revert it.

If the user says "undo that", "don't save that", "revert", or equivalent — undo the write immediately.

## Output

Whatever matches the user's request:
- Question → answer grounded in profile content.
- File edit request → read, propose, write, summarize what changed.
- Analysis → structured but tight response; don't over-format.
- Thinking help → engage conversationally; don't default to bullet-lists for every exchange.
