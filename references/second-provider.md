# Second-provider pass — the strongest independence available

Read this when a second AI provider's CLI is installed on the machine. It
**upgrades either method** (fan-out or single-mind); it does not replace them.

## Why this exists

This skill's whole premise is that a second look from the same mind defends the
framing it already chose. That premise does not stop at context boundaries.

Independence comes in tiers, weakest to strongest:

1. **Same model, same context** — not independent at all. Explicitly forbidden.
2. **Same model, fresh context** (a spawned sub-agent) — genuinely blind to the
   reasoning, but shares the model's priors, blind spots, and training. This is
   what the fan-out method buys.
3. **A different company's model** — different priors, different failure modes,
   different things it finds obvious. Its agreement with the primary read is real
   evidence; its disagreement is a flag worth chasing.

Tier 3 is the strongest independence obtainable, and it costs almost nothing:
review is read-only, so a bad reviewer cannot break anything, and it bills to a
different subscription than the one running this session.

**So: if a second provider is available, at least one reviewer seat should be
its.** In the fan-out method, make it one of the parallel reviewers. In the
single-mind method, it is the *only* genuinely outside voice available — which
makes it more valuable there, not less.

## Detect before you offer

Never name a tool that isn't installed. Check first:

```bash
export PATH="$HOME/.local/bin:$PATH"
command -v codex     # OpenAI Codex CLI
command -v agent     # Cursor CLI (also resells other vendors' models on its meter)
command -v gemini    # Google Gemini CLI
```

**A `PATH` miss is not proof of absence.** Several of these ship their CLI
bundled inside a desktop app rather than symlinked onto `PATH` — so
`command -v` returns nothing while the tool is installed, authenticated, and in
daily use. Before concluding a provider is unavailable, check the obvious app
bundles and the provider's state directory (`~/.codex`, `~/.cursor`, and the
like). **If the user says they have it, believe them and go find it** — a wrong
"you don't have that" is worse than no check at all, because it silently removes
the strongest reviewer seat on the table.

Genuinely nothing installed → skip this file entirely and run the chosen method
as written. Say plainly that no second provider was available, so the reviewers
share one model's priors. Do not imply outside eyes you did not have.

## Run it read-only — enforced, not promised

The reviewer must be physically unable to edit. Prompt discipline is not enough.

```bash
# OpenAI Codex — read-only is the DEFAULT sandbox; pass it explicitly anyway so
# the intent survives someone editing this command later.
codex exec --sandbox read-only --json "<review prompt>"

# Codex also has a purpose-built review subcommand — prefer it for code, since it
# is designed for the job rather than steered into it by prompt:
codex exec review        # see `codex exec review --help` for its scope flags

# Cursor — read-only is enforced by ask mode. --trust is required even here, or
# the CLI stalls on a workspace-trust prompt and returns nothing useful.
agent -p --mode ask --trust --output-format json --model <id> "<review prompt>"

# Gemini — note this path needs --yolo for headless operation, which is NOT
# read-only-enforced. Prefer the two above when either is available.
gemini -p "<review prompt>" --yolo
```

**Resolve model ids from the tool, never from memory** (`agent --list-models`,
`codex exec --help`). The "obvious" id is routinely wrong, and a stale id fails
the call rather than degrading gracefully.

## What to ask it

Do **not** ask it to summarize or to agree. Give it the artifact and the same
three-stage job this skill runs, compressed:

```
Here is <artifact>. Context: <the constraint set, the goal, what's already decided>.

1. CRITICIZE — what is actually wrong with this thinking? Attack the framing,
   not the spelling. What does it assume without saying so?
2. IMPROVISE — ignore the above and rebuild it from a blank slate. What would
   you do instead, given the same goal and constraints?
3. SYNTHESIZE — one recommendation: keep it, strengthen it, or rethink it. Say
   which, and why, in under 200 words.

Then: what question should have been asked here that wasn't?

Do not fix anything. Do not write files. Be blunt — hedging is useless here.
```

## Folding the result in — the part that goes wrong

The second provider's output is **evidence, not a verdict**. It has not seen the
conversation, the history, or the constraints that never got written down, so it
will confidently flag things that are already settled.

1. **Verify each point against the artifact yourself before it reaches the user.**
   Cross-model reviewers produce real false positives. Passing them through
   unchecked just relocates the noise onto the user's desk and burns the trust
   that makes this pass worth running.
2. **Where the two reads agree, say so and treat it as strong.** Convergence
   across vendors is the most reliable signal this skill can produce.
3. **Where they disagree, do not silently pick a winner.** Name the disagreement,
   give the strongest version of each side, then make your call and label it as
   yours.
4. **Attribute honestly** in the final answer, e.g.:
   `Second read: <provider/model>, read-only — agreed on 2, split on 1.`
   The moment the user cannot tell which reads were independent, they cannot tell
   how much weight the agreement deserves.

## Never route sensitive material through an outside provider

Credentials, customer data, private business logic, anything under NDA. This holds
for every external provider regardless of what its retention settings say today.
If the artifact contains any of it, either redact before sending or skip this pass
and say why.
