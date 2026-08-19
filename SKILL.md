---
name: fresh-eyes
description: >-
  Fresh eyes — criticize, improvise, synthesize. Pressure-test AND improve any
  artifact (plan, spec, design, strategy, copy, decision, architecture, code):
  return ONE value-ranked recommendation plus the question the user should have
  asked but didn't. An independent RE-EXAMINATION that attacks the thing AND rebuilds it
  from a blank slate, landing on an open verdict — keep it, strengthen it, or
  rethink it. Generating real alternatives is MANDATORY, not the goal. It rethinks the THINKING; it
  does NOT verify correctness ("is this right / done / ready to
  ship?" → a separate verification pass). Fires on:
  "fresh eyes", "criticize improvise synthesize", "fresh / outside perspective on
  X", "pressure-test this", "stress-test this", "red-team this", "poke holes and
  make it better", "get independent eyes on X", "what am I missing", "what would
  someone else say". Lean toward firing whenever the user wants outside
  perspective or an impartial re-examination of a piece of thinking. If a second
  AI provider's CLI is installed, it gives one reviewer seat to that provider —
  the strongest independence available.
---

# Fresh Eyes — router

When someone says "fresh eyes," they are not asking you to re-read your own work
and nod. Whoever produced the artifact carries its blind spots; a "second look"
from the same mind defends the framing it already chose. The value is an outside
read that attacks AND rebuilds the thing from a blank slate, then hands back ONE
honest call on it — keep it, strengthen it, or rethink it — plus the question that
should have been asked but wasn't.

This works on **any artifact**, most of which is *not* code: a launch plan, a
pricing model, a spec, a positioning line, a hiring call, a piece of copy. Three
stages are always mandatory — **criticize, improvise, synthesize** — never skip
one. Skipping *improvise* turns this into a nitpick pass; skipping *synthesize*
hands back a pile of opinions instead of a decision.

**Boundary (read this first).** fresh-eyes is an **independent re-examination** — it
attacks AND rebuilds the *thinking / approach* from a blank slate and lands on an
open verdict (keep it, strengthen it, rethink it). It is NOT a correctness gate. If
the ask is "is this code right / done / ready to ship?", that's a separate
**verification / audit** pass — run that instead. If both are wanted, re-examine the
design with fresh-eyes first, then hand the result to the verification pass, and say
which you're doing.

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

## Then check for the independence upgrade (both methods)

Both methods above run on **one vendor's model**. A fresh context is blind to the
reasoning, but it still shares the model's priors, blind spots, and the things it
finds obvious. A **different company's model** does not — which makes it the
strongest independence obtainable here.

So, whichever method you picked: **if a second provider's CLI is installed, give
it at least one reviewer seat.** It is close to free — review is read-only, so a
bad reviewer cannot break anything — and it bills to a different subscription
than the one running this session.

→ **If a second provider is available, read and follow
[`references/second-provider.md`](references/second-provider.md)** alongside your
method file.

If none is installed, run the method as written and **say so in the result** —
that the reviewers shared one model's priors, so agreement between them is weaker
evidence than it looks. Never imply outside eyes you did not have.

Load only the one method file you need — the other stays on disk and costs nothing.
