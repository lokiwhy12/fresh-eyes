# Fresh Eyes

**A skill for Claude that gives your thinking a real second opinion.**
Hand it a plan, a pitch, a design, a decision, a piece of writing, or the approach behind some code. It tears into it, builds real alternatives, and hands back **one clear call — keep it, strengthen it, or rethink it** — plus the question you should have asked but didn't.

| | |
|---|---|
| **Works in** | Claude Code (terminal, IDE, or the desktop app's Code tab) and the Claude app at claude.ai — any plan, including Free |
| **Strongest where** | Claude can start helper agents (Claude Code): several independent reviewers read your work blind. In a plain chat it runs one disciplined pass instead — useful, but weaker, and the result tells you which one ran |
| **Cost** | A big decision starts 7–8 top-model helpers and takes a few minutes. A short, low-stakes piece gets 2–3 |
| **Not for** | "Does this code work / is it ready to ship?" — that's your tests or a code review. Fresh Eyes judges whether it's the *right thinking* |

**[What you get back](#what-you-get-back)** · **[Install](#install)** · **[First run](#your-first-run)** · **[Visual guide](https://lokiwhy12.github.io/fresh-eyes/guide.html)**

---

## What you get back

Before this repo went public, Fresh Eyes reviewed this README. Here's the top of its answer:

> **FRESH EYES** — from 7 blind reads that clustered here (salient, not proof).
>
> **Recommendation:** Strengthen it, don't rethink it — and don't share the link until the install path is fixed. The writing is good, but a stranger arriving from GitHub can't install it: the zip it assumes doesn't exist, the copy command fails, and the Claude-app steps are out of date. Fix the install, show a real result before the explanation, and give a first-run line that always works.
>
> **The question you didn't ask:** Who exactly is the first person you're sending this to?

Below that, every run gives the strongest criticisms, the best improvements ranked by how much they matter, the ideas that didn't survive scrutiny, any real either/or you have to decide, and how independent its reviewers really were. (This README is the "after.")

---

## Install

### Claude Code

```sh
git clone https://github.com/lokiwhy12/fresh-eyes ~/.claude/skills/fresh-eyes
```

Check it worked: type `/fresh-eyes` — it should appear in the menu. If this is the first skill you've ever installed, run `/reload-skills` first (or start a new session).

- **Update:** `git -C ~/.claude/skills/fresh-eyes pull`
- **Copied an older version in by hand?** Delete `~/.claude/skills/fresh-eyes` first, then clone.
- **No git?** Download [fresh-eyes.zip](https://github.com/lokiwhy12/fresh-eyes/releases/latest/download/fresh-eyes.zip), unzip it, and move the `fresh-eyes` folder into `~/.claude/skills/`.
- **Just one project?** Clone into that project's `.claude/skills/fresh-eyes` instead.

### Claude app (claude.ai) — any plan, including Free

1. Download **[fresh-eyes.zip](https://github.com/lokiwhy12/fresh-eyes/releases/latest/download/fresh-eyes.zip)**.
   *Not* GitHub's green **Code** button or "Source code (zip)" — those name the folder `fresh-eyes-main`, and Claude rejects a folder name that doesn't match the skill.
2. Turn on code execution: **Settings → Capabilities → "Create and edit files."** (Team/Enterprise: an owner turns it on for the organization.)
3. Go to **Customize → Skills → + → Create skill → Upload a skill**, choose the zip, and make sure it's switched on.

Menus move — [Anthropic's current steps](https://support.claude.com/en/articles/12512180) (checked 2026-11-04).

**Use both?** If you sign into Claude Code with the same claude.ai account (Claude Code v2.1.273 or later), your uploaded copy shows up there too. Keep just one copy — delete the folder, or remove the upload.

---

## Your first run

**In Claude Code**, type `/fresh-eyes`, paste your work, and add one line on what you're trying to achieve — or, mid-session, just say *"use fresh eyes on this."*

```
/fresh-eyes Here's my plan: <paste it>. Goal: <what success looks like>.
```

**In the Claude app**, say *"use fresh eyes on this,"* paste the work, and add the same one-line goal.

It's working if the reply starts with **FRESH EYES**. For a first try, pick something short and low-stakes — an email, a bio, a one-paragraph idea. It sizes the review to the stakes, so a big plan gets the big (slower, costlier) treatment.

Other plain phrases work too — *"pressure-test this plan," "poke holes in this and make it better," "what am I missing?"* If you have a lot of skills installed and a plain phrase doesn't trigger it, `/fresh-eyes` always will.

---

## How it works

Every run does three things, in order: **criticize** (find the real weak spots), **improvise** (better versions, different approaches, an angle nobody asked for), **synthesize** (one ranked recommendation). There's nothing to configure — it checks what the session can do:

- **Where Claude can start helper agents** (Claude Code): several **independent reviewers** each read your work blind, from a different angle — a skeptic, a customer, a competitor, a cost realist, a contrarian, a simplifier, plus a domain expert when the work needs one. On big decisions a **cross-examiner** then attacks every new idea and proposes a fix for every criticism — and isn't allowed to pick winners. Then one synthesis.
- **In a plain chat:** one mind runs the same three steps in sequence, under strict rules that stand in for independence. If it's on a small, fast model, it asks you to switch to a top one first.

Either way, the result says how independent its reviewers really were — several copies of one model agreeing is weaker evidence than it looks, and it tells you so.

### Advanced: "full fresh eyes"

If you already have a skill that lets Claude call **other AI companies' models**, say *"full fresh eyes"* and those models join the panel — different companies' models have different blind spots, so their agreement means more. **Fresh Eyes doesn't include that connection.** Your work is sent to those companies; Claude is told to strip secrets and personal details first, but don't send what you can't share. Without that setup it says so and runs the standard version. It never goes "full" unless you ask.

---

## What's inside

It's only instructions — no scripts, nothing to configure. Its reviewers can use the tools your session already allows (reading files, searching the web), so you may see permission prompts.

| File | What it is |
|---|---|
| `SKILL.md` | The entry point — picks the method, then loads the matching file |
| `references/fan-out.md` | The multi-reviewer method |
| `references/single-mind.md` | The one-mind method |
| `references/full.md` | The "full fresh eyes" upgrade |
| `guide.html` | The [visual guide](https://lokiwhy12.github.io/fresh-eyes/guide.html) |

Only the method a run needs is loaded, so no run pays for the others.

## Uninstall

- **Claude Code:** `rm -rf ~/.claude/skills/fresh-eyes`
- **Claude app:** Customize → Skills, then remove Fresh Eyes.

## License

MIT — see [LICENSE](LICENSE).
