# Fresh Eyes — criticize, improvise, synthesize

> ## ℹ️ What this is (read first)
> Fresh Eyes is a **skill** that gets a real second opinion on any piece of
> thinking — a plan, a design, a pitch, a business decision, a bit of copy, an
> architecture, code. You point it at something you made and it **tears into it,
> rebuilds it with real alternatives, and hands you back one honest call — keep it,
> strengthen it, or rethink it** — plus "the question you should have asked but
> didn't." It does **not** check whether something is *correct* (that's a separate
> verification pass); it re-examines whether it's the right thinking. Open **[`guide.html`](guide.html)** in a browser for a
> 2-minute visual walkthrough.

One skill, two engines under the hood — and it picks the right one automatically:

- **Fan-out engine** (when it has the tools): spins up several **independent**
  reviewers who each start from a blank slate, then a "trade homework" round where
  they attack each other's new ideas, then one synthesis. This runs in **Claude
  Code** (and anywhere that can dispatch parallel sub-agents).
- **Single-mind engine** (when it doesn't): one mind runs the same critique →
  improve → synthesize discipline in sequence. This is what runs in the **Claude
  app (claude.ai)**, which has no way to spawn separate agents.

You never choose. The skill checks what it can do and routes itself — so the exact
same folder works correctly in both places.

---

## Install

Skills **don't sync between Claude Code and claude.ai** — you install the same
folder in each place you want it. Pick the one(s) you use.

### In Claude Code (your terminal / IDE)

Unzip, then drop the `fresh-eyes` folder into your skills directory:

```sh
cp -R fresh-eyes ~/.claude/skills/fresh-eyes
```

(Use `.claude/skills/` inside a project instead, if you only want it there.) Start
a new session — Claude discovers it automatically. In Claude Code it'll use the
**fan-out** engine.

### In the Claude app (claude.ai)

1. Zip the `fresh-eyes` folder (if you unzipped it) so you have a single `.zip`.
2. In claude.ai go to **Settings → Features** (also called Capabilities) and
   **upload the skill zip** under custom skills.
3. Requires a **Pro, Max, Team, or Enterprise** plan with **code execution
   enabled**. Custom skills are per-account (each person uploads their own).

In the app it'll use the **single-mind** engine automatically.

> Prefer to have Claude do it: open Claude Code in the unzipped folder and say
> *"install this skill into my ~/.claude/skills/ folder,"* or in the app just
> upload the zip in settings.

---

## Using it

You don't run a command — **just ask, in plain words.** Any of these will trigger
it: *"fresh eyes on this,"* *"pressure-test this plan,"* *"poke holes in this and
make it better,"* *"what am I missing here,"* *"what would someone else say about
this?"*

Give it the thing you want looked at (paste it, or point Claude at the file) and
what you're actually trying to achieve. It comes back **leading with one clear
recommendation you can act on** — then, as optional depth: the strongest
criticisms, the best improvements ranked by how much they matter, any real
either/or you have to decide, and the unasked question.

**What it's *not* for:** "is this code correct / done / ready to ship?" That's a
verification pass, a different job. Fresh Eyes makes things *better*, it doesn't
sign off that they're *right*.

---

## What's inside

| File | What it is |
|------|-----------|
| `SKILL.md` | The entry point. A thin router that picks fan-out vs single-mind, then loads the matching method. |
| `references/fan-out.md` | The multi-agent method (independent reviewers + trade-homework round). Loads only in Claude Code. |
| `references/single-mind.md` | The single-context method (one disciplined pass). Loads only in the app. |
| `README.md` | This file. |
| `guide.html` | A visual, plain-English walkthrough — open it in any browser. |

The two method files load **only when their path is chosen**, so neither engine
ever pays the cost of the other — that's why one folder can serve both places
without bloat.

---

## Requirements

- **Claude Code:** nothing extra — it's just a folder of instructions. Drop it in
  and go.
- **Claude app (claude.ai):** a Pro / Max / Team / Enterprise plan with code
  execution enabled (that's what lets custom skills run).
- Works best on a **top reasoning-tier model** — the skill will tell you to switch
  up if it detects it's running on a small/fast model, because the whole value is
  hard adversarial reasoning.

---

## Uninstall

- **Claude Code:** `rm -rf ~/.claude/skills/fresh-eyes`
- **Claude app:** remove it from Settings → Features.

It writes nothing outside itself.
