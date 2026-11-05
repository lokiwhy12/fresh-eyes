# Fresh Eyes — criticize, improvise, synthesize

> ## ℹ️ What this is (read first)
> Fresh Eyes is a **skill** that gets a real second opinion on any piece of
> thinking — a plan, a design, a pitch, a business decision, a bit of copy, an
> architecture, code. You point it at something you made and it **tears into it,
> rebuilds it with real alternatives, and hands you back one honest call — keep it,
> strengthen it, or rethink it** — plus "the question you should have asked but
> didn't." It does **not** check whether something is *correct* (that's a separate
> verification pass); it re-examines whether it's the right thinking. Open
> **[`guide.html`](guide.html)** in a browser for a 2-minute visual walkthrough.

One skill, two built-in methods — it picks the right one automatically — plus an
optional upgrade you have to ask for:

- **Multi-reviewer method** (when it can spin up helpers — Claude Code, or anywhere
  that can run parallel sub-agents). Several **independent** reviewers each read
  your work blind, from a different angle: a skeptic, a customer, a competitor, a
  cost realist, a contrarian, a simplifier (plus a domain expert when the work
  needs one). For big decisions, a separate **cross-examiner** then goes through
  every new idea and every criticism one by one — attacking each idea, proposing a
  fix for each criticism — and is forbidden to pick winners. Then one synthesis.
  For small things it just takes 2–3 quick independent reads.
- **Single-mind method** (when it can't). One mind runs the same
  criticize → improvise → synthesize discipline in sequence, under strict rules
  that stand in for independence. This is what runs in the **Claude app
  (claude.ai)** chat, which can't spawn separate helpers.
- **"Full fresh eyes" (optional upgrade).** Say *"full fresh eyes"* and, if your
  setup can reach other AI companies' models, it adds the strongest model from each
  of them — writing their own ideas blind, and cross-examining everyone else's.
  Different companies' models have different blind spots, so their agreement is
  much stronger evidence. **This needs a separate skill that knows how to call
  those models** (Fresh Eyes deliberately names no company or tool). Without one,
  it tells you the full panel isn't available and runs the standard version. It
  never goes "full" unless *you* say so.

You never choose between the first two. The skill checks what it can do and routes
itself, so the same folder works in both places.

---

## Install

### In Claude Code (your terminal / IDE)

Unzip, then drop the `fresh-eyes` folder into your skills directory:

```sh
cp -R fresh-eyes ~/.claude/skills/fresh-eyes
```

(Use `.claude/skills/` inside a project instead, if you only want it there.) Start
a new session — Claude discovers it automatically and uses the **multi-reviewer**
method.

### In the Claude app (claude.ai)

1. Zip the `fresh-eyes` folder (if you unzipped it) so you have a single `.zip`.
2. In claude.ai open **Settings**, find **Skills** (under Capabilities), and
   **upload the zip** as a custom skill.
3. Custom skills need a paid plan with code execution enabled, and they're
   per-account (each person uploads their own).

In the app it uses the **single-mind** method automatically.

### Using both?

A skill uploaded to your claude.ai account can also show up in Claude Code when
you're signed into the same account (it appears as `anthropic-skills:fresh-eyes`).
If you see it there, you don't need the folder copy too — and if you have both,
remove one so they don't compete.

> Prefer to have Claude do it: open Claude Code in the unzipped folder and say
> *"install this skill into my ~/.claude/skills/ folder,"* or in the app just
> upload the zip in settings.

---

## Using it

You don't run a command — **just ask, in plain words.** Any of these will trigger
it: *"fresh eyes on this,"* *"pressure-test this plan,"* *"poke holes in this and
make it better,"* *"what am I missing here,"* *"what would someone else say about
this?"* Add the word **"full"** (*"full fresh eyes on this"*) only if you have the
extra setup described above and want the cross-company panel.

Give it the thing you want looked at (paste it, or point Claude at the file) and
what you're actually trying to achieve. It comes back **leading with one clear
recommendation you can act on** — then, as optional depth: the strongest
criticisms, the best improvements ranked by how much they matter, the ideas that
didn't survive scrutiny, any real either/or you have to decide, and the unasked
question. It also says plainly how independent its reviewers really were, so you
know how much weight their agreement deserves.

**What it's *not* for:** "is this code correct / done / ready to ship?" That's a
verification pass, a different job. Fresh Eyes makes things *better*; it doesn't
sign off that they're *right*.

---

## What's inside

| File | What it is |
|------|-----------|
| `SKILL.md` | The entry point. A thin router that picks the method, then loads the matching file. |
| `references/fan-out.md` | The multi-reviewer method (independent reviewers + the cross-examiner). Loads only where helpers can be spun up. |
| `references/single-mind.md` | The single-context method (one disciplined pass). Loads only where helpers can't be spun up. |
| `references/full.md` | The "full fresh eyes" upgrade. Loads only when you ask for "full" and the extra setup exists. |
| `README.md` | This file. |
| `guide.html` | A visual, plain-English walkthrough — open it in any browser. |

Each method file loads **only when it's chosen**, so no run pays for the others.

---

## Requirements

- **Claude Code:** nothing extra — it's just a folder of instructions. Drop it in
  and go.
- **Claude app (claude.ai):** a paid plan with code execution enabled (that's
  what lets custom skills run).
- Works best on a **top reasoning-tier model** — the skill tells you to switch up
  if it's running on a small/fast model, because the whole value is hard
  adversarial reasoning.
- **Usage:** a big-decision run in Claude Code starts six to eight reviewers, so it
  uses noticeably more of your allowance than a normal reply. Small asks get the
  lighter 2–3 reader version.

---

## Uninstall

- **Claude Code:** `rm -rf ~/.claude/skills/fresh-eyes`
- **Claude app:** remove it from Settings → Skills.

It writes nothing outside itself.
