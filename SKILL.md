---
name: fresh-eyes
description: >-
  Fresh eyes — criticize, improvise, synthesize. Pressure-test AND improve any
  artifact (plan, spec, design, strategy, copy, decision, architecture, code):
  return ONE value-ranked recommendation plus the question the user should have
  asked but didn't. GENERATIVE ("make this stronger / better / different"), NOT
  correctness-checking ("is this right / done?" → a verification pass). Fires on:
  "fresh eyes", "criticize improvise synthesize", "fresh / outside perspective on
  X", "pressure-test this", "stress-test this", "red-team this", "poke holes and
  make it better", "get independent eyes on X", "what am I missing", "what would
  someone else say". Lean toward firing whenever the user wants outside
  perspective or to strengthen a piece of thinking.
---

# Fresh Eyes — router

When someone says "fresh eyes," they are not asking you to re-read your own work
and nod. Whoever produced the artifact carries its blind spots; a "second look"
from the same mind defends the framing it already chose. The value is an outside
read that attacks and rebuilds the thing, then hands back ONE stronger result —
plus the question that should have been asked but wasn't.

This works on **any artifact**, most of which is *not* code: a launch plan, a
pricing model, a spec, a positioning line, a hiring call, a piece of copy. Three
stages are always mandatory — **criticize, improvise, synthesize** — never skip
one. Skipping *improvise* turns this into a nitpick pass; skipping *synthesize*
hands back a pile of opinions instead of a decision.

**Boundary (read this first).** fresh-eyes is **generative** — "make X better /
stronger / different." It is NOT a correctness gate. If the ask is "is this code
right / done / ready to ship?", that's a separate **verification / audit** pass —
run that instead. If both are wanted, run fresh-eyes on the design first, then
hand the result to the verification pass, and say which you're doing.

## Pick your method (do this first)

Fresh-eyes runs one of two ways, chosen by **what this environment can do** — not
by which product name you think you're in:

- **Fan-out method** — use this **if you can dispatch INDEPENDENT parallel
  reviewers**: you have a Workflow tool, or a Task/Agent tool that spawns separate
  sub-agents each with their own fresh context. This is the stronger method —
  genuinely blind, independent reviewers whose agreement is real signal.
  → **Read and follow [`references/fan-out.md`](references/fan-out.md).**

- **Single-mind method** — use this **if you do NOT have those tools**: a single
  chat context (e.g. the Claude app) with no way to spawn independent agents. One
  mind runs the adversarial stances serially, under strict discipline that
  substitutes for independence.
  → **Read and follow [`references/single-mind.md`](references/single-mind.md).**

**Decide by capability, not by label.** If you are unsure whether you can truly
spawn independent parallel agents, use the **single-mind method** — it always
works, and it is honest about not having outside eyes. Never fake independence by
presenting stages of one mind as if they were separate reviewers.

Load only the one method file you need — the other stays on disk and costs nothing.
