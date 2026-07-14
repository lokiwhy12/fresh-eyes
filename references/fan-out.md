# Fresh Eyes — FAN-OUT method (independent multi-agent)

> ROUTED HERE because this environment CAN dispatch independent parallel reviewers.
> IF you cannot actually spawn independent agents -> STOP, use `single-mind.md`.
> NEVER fake independence (one mind's staged output presented as separate reviewers).

PURPOSE: pressure-test AND improve any artifact (plan, spec, design, strategy, copy, decision, architecture, code); emit ONE value-ranked recommendation OR a justified "leave it alone".
MODE: N blind independent agents + (big calls) cross-examination + your synthesis. Generative (improve), NOT convergent (verify).

## IDENTITY  (the mechanism; this governs behavior)
CORE = INDEPENDENCE: minds with no stake in the current version, no memory of how it was meant to work, attacking + rebuilding it from a blank slate.
FAIL_HARD — do NOT let the fresh agents grade your homework: hand them the artifact + the GOAL and NOTHING of your intent. Leaked intent -> they anchor -> they converge on your answer -> the run is worthless.
STAGES: criticize -> improvise -> synthesize. ALL mandatory. Skip improvise = a nitpick pass. Skip synthesize = a pile of opinions instead of a decision.

## SCOPE_BOUNDARY
IN (fresh-eyes): "make X better / stronger / different" -> generative.
OUT (separate verification pass): "is X correct / done / ready to ship?" -> convergent.
BOTH requested -> run fresh-eyes on the design, THEN hand the result to a separate verification pass; SAY which you are doing.

## SCALE — pick fan-out WIDTH first
Stages are FIXED; width + lens diversity scale.
- QUICK_GUT_CHECK (a paragraph, a small decision) = 2-3 agents, same generalist brief; you just want non-correlated reads. ROUND 1 ONLY — no Round 2 (over-build at this tier).
- BIG_DECISION (strategy, architecture, money, a launch — anything acted on hard / not cheaply unwound) = 4-6 agents, EACH handed an explicit DISTINCT lens. ROUND 1 + ROUND 2.
LENSES (one per agent; NON-overlapping — overlap wastes the fan-out): skeptic (assume it fails; find why first) · customer (who's it for; do they care; what do they resent) · competitor (how it's beaten / routed around) · cost_realist (what it actually takes) · contrarian (the opposite bet) · simplifier (what if half is unnecessary) · domain_expert (deep on pricing / security / copy / ops).
UNSURE how wide -> GO WIDER. Independent agents are cheap; a weak decision someone ships on is not.

## MECHANISM
DISPATCH: the Workflow tool if one is exposed, else parallel Task / general-purpose sub-agents. The harness is irrelevant — the fresh-context fan-out + the three stages is what matters.
MODEL_BAND (a band, not an open ceiling):
- FLOOR: never below the top reasoning tier available. A weak reviewer produces a weak review that still LOOKS real.
- CEILING: the fan-out is N parallel passes — the one place cost multiplies. Pin reviewers explicitly; do NOT let them inherit a lighter model, and do NOT put all N on the priciest tier unless the user asked this run. Prefer ONE pass on the priciest tier over N.
BLINDNESS: each agent blind to the others AND to your intent. No shared scratchpad, no seeing each other's output. Overlap that survives independent eyes = signal; groupthink you engineered = noise.
PIPELINE: Round 1 (independent) -> Round 2 (cross-exam, BIG only) -> Synthesis (consumes BOTH rounds). Gut-check = Round 1 -> Synthesis.
ROUND 2 IS ADDITIVE, never a replacement: Round 1 stays fully independent + blind (that signal is the core asset). Round 2 stresses the NEW ideas; it never re-runs, edits, or overwrites them.

## THE BRIEF — hand each agent this and ONLY this
1. THE ARTIFACT, verbatim — the actual plan / spec / copy / decision, in full. Paste it or point at the exact file. NOT your summary of it.
2. THE GOAL, 1-2 plain lines = the target OUTCOME, not the implementation ("win back churned users", not "improve this email's subject line"). The success criterion they grade against. No goal -> they critique in a vacuum. Your intent -> they just ratify. GIVE the goal, WITHHOLD the intent.
3. THE OUTPUT CONTRACT (below) — load-bearing; without it agents default to a list of nitpicks and skip the improvement, the half that matters most.
4. (BIG only) their assigned LENS.
WITHHOLD deliberately: conversation history · how you got here · what you're leaning toward · your own critique or preferred fix · which option is the favorite · prior objections · sunk-cost framing. The blank slate IS the asset — protect it.

## ROUND 1 — every agent does all three stages

### 1. CRITICIZE — attack it
DO: find the real weaknesses — failure modes, risks, weak/unstated assumptions, blind spots; where it breaks under load, at the edges, with a hostile-or-confused user, 6 months on. What does it quietly bet on that might be false?
EACH FINDING: the problem + WHY it bites. Specific. NOT "this could be cleaner".

### 2. IMPROVISE — better AND different (fill all three; none empty)
- (a) better_alternatives = stronger versions of the SAME idea; keep the approach, raise the ceiling. COUNT >= 2.
- (b) different_approaches = OTHER ways to hit the GOAL entirely; drop the current frame. COUNT >= 2.
- (c) unexpected_angles = the non-obvious reframe nobody asked for / "the premise may be wrong". COUNT >= 1; push for the genuinely surprising one, not a safe restatement. The class agents skip most; where the value usually hides.
ENFORCE anti_nitpick: critique-only OR any class left empty = TASK NOT COMPLETE -> loop it back ("you returned weaknesses but no (b) different approaches and no (c) unexpected angle; produce them"). A pile of objections is a worse first draft, not fresh eyes.
ENFORCE steelman: every alternative = the BEST HONEST version of itself, never a strawman set up to lose. Mandatory + full-strength HERE; the freedom to reject everything is reserved for synthesis, and only after the candidates were real. A "keep it" that beat strawmen is worth nothing.

### UNASKED_QUESTION  (required return line, NOT a fourth stage)
DO: step one level up — off the artifact, onto the QUESTION itself. Name the question that should have been asked but wasn't.
CLASSES (any one fits): prior_decision (what must be settled first) · symptom_check (this artifact is a symptom; the leverage is upstream) · buried_assumption (baked into the QUESTION, not the artifact) · scope_error (framing too narrow or too broad) · expert_gap (what a domain expert would ask that a non-expert wouldn't know to).
WHY YOU: you are uniquely placed BECAUSE you're blind to how they got here; the person in the weeds is anchored to the question they asked.
OUTPUT: ONE line. HONEST_NULL allowed + respected: if the question is genuinely well-scoped and nothing upstream is missing, say exactly that. Do NOT manufacture a profundity.

### 3. SELF-SYNTHESIZE
CLOSE with one line: "if it were mine, I'd do ___, because ___" -> you get N independent best-bets, not N shrugs.

### RETURN — the stack
SHAPE: `weaknesses[] · better-alternatives[] · different-approaches[] · unexpected-angles[] · unasked-question (1 line, honest null OK) · my-pick (1 line)`. Each item 1-2 tight lines.
EMPTY SECTION = FAILED RETURN — except unasked-question, where an honest "well-scoped, nothing upstream" is valid, not a miss.
Agents do NOT rank across each other — that is YOUR job.
KEEP each Round-1 stack INTACT + LABELED (Stack A = skeptic, Stack B = customer, …). Round 2 + synthesis reference them by label. Originals are NEVER edited.

## ROUND 2 — CROSS-EXAMINATION  (BIG_DECISION TIER ONLY)
STAKES_GATE: fires ONLY on the big-decision tier — a launch, an architecture, a money call, a strategy. A quick gut-check does NOT get a Round 2. UNSURE which tier -> you're in gut-check -> skip Round 2, go straight to synthesis.
THE GAP IT CLOSES: Round 1's IMPROVISE outputs are the NEWEST + RISKIEST material precisely because they're novel — nobody pressure-tested them. Every Round-1 attack hit the ORIGINAL; the PROPOSALS were never attacked at all. Round-1-only -> they ride into synthesis COMPLETELY UNVETTED. Round 2 puts the new ideas through the same adversarial wringer + turns the surfaced criticisms into concrete fixes.

### HOW IT RUNS ON TOP OF ROUND 1
ROUND 1 IS FROZEN — you never edit those stacks. Round 2 produces a SEPARATE annotation layer alongside each, never a rewrite.
PAIRING/ROTATION: one peer agent per Round-1 stack. Hand peer *i* a DIFFERENT agent's stack — ideally from a different LENS, so the cross-talk crosses perspectives rather than echoing one. Simple rotation: peer for Stack A gets B, B gets C, … last wraps to A. Dispatch ALL peers in PARALLEL, each blind to the other peers.
EACH PEER RECEIVES — and ONLY this:
1. THE ORIGINAL ARTIFACT, verbatim + THE GOAL (the same two anchors Round 1 got). The peer grades against the OUTCOME, not against the stack.
2. EXACTLY ONE Round-1 stack. Not all of them — seeing every stack lets the peer AVERAGE across them, which is synthesis (your job), not cross-examination.
3. The Round-2 contract + the anti-anchoring guard (below).
STILL WITHHELD: your intent · the conversation history · what you're leaning toward · the OTHER peers' work.

### ROUND-2 CONTRACT — two moves, BOTH mandatory
MOVE_A — CRITIC_ATTACKS_THE_IMPROVEMENTS (the must-have; the actual gap):
DO: take the stack's IMPROVISE outputs (every better-alternative, different-approach, unexpected-angle) and attack them the way Round 1 attacked the original. Per proposal worth engaging: what does it quietly assume · where does it break · what does it cost that the proposer waved off · what NEW failure mode does it introduce · who does it lose.
RULE: treat every proposal as a claim to be DISPROVED, not admired. Accept none on the proposer's say-so. HARDEST look = the unexpected_angle (most novel, least examined).
IF only one move runs -> RUN A.
MOVE_B — IMPROVER_ANSWERS_THE_CRITICISMS (the valuable bonus):
DO: take the stack's CRITICIZE outputs and turn EACH into a concrete solution / mitigation / genuine alternative — the design change, the guardrail, the different path that makes the weakness stop biting — OR a clear statement that it's unsolvable and must be lived with.
RULE: "yes, that's a risk" != a fix (Round 1 already said that).

ANTI-ANCHORING GUARD — print in the peer's prompt VERBATIM:

> You are cross-examining another analyst's stack, not joining their team. Attack
> their proposals and solve their criticisms **from your own independent read of
> the artifact** — keep your own judgment intact. Do **NOT** adopt their framing,
> defer to their conclusions, soften your take to agree, or let their stack become
> the new anchor you converge on. The failure mode here is groupthink: two minds
> collapsing into one view, which destroys the different-approaches and unexpected
> angles this exercise exists to produce. If, after honestly cross-examining, you
> still see the artifact differently, **say so** — your divergence is signal. I
> want friction, not consensus.

PEER RETURNS (a cross-annotation layer, kept SEPARATE from the stack):
`attacks-on-their-improvements[]` (which proposal · the hole · how hard it bites) · `solutions-to-their-criticisms[]` (which weakness · the concrete fix, or "live with it, because…") · `where-I-still-diverge` (1 line, or "converged honestly").
ENFORCE both moves. Only-attacks OR only-solves = half of Round 2 -> loop it back. Trimmed under pressure -> KEEP MOVE_A.
AFTER ROUND 2 you hold TWO layers, both intact + labeled: the N frozen Round-1 stacks + the N Round-2 cross-annotations. Round 2 NEVER overwrites Round 1 — if a peer's attack is wrong, the original proposal still stands on its Round-1 merits; synthesis weighs both. NOTHING is merged yet — that's synthesis.

## SYNTHESIZE — one integrated result, not an average (YOUR job, not theirs)
RULE: don't average — TAKE THE BEST. Averaging independent views back to the bland middle throws away the exact edge you paid for. Integrate, don't tally.

SEAL FIRST — you are the ONLY un-blind link:
DO: BEFORE reading a single stack, write SEALED_READ = 2-3 lines = the recommendation you currently believe.
THEN read everything. THEN state plainly whether/how the stacks MOVED you — what you changed your mind about / what survived / what you dropped.
IF nothing moved you -> say so AND show the independent reads genuinely agreed (not that you skimmed past them).
WHY: your prior is exactly the bias the blind fan-out existed to remove, and it leaks straight back in here at the last step. Declare the bias; do NOT amputate the context (you need the owner's context to rank by value).

CONSUME BOTH LAYERS (when Round 2 ran):
- Round-1 improvement HOLED badly by its peer -> drops in rank or out. Novel != survived. Don't promote it for being exciting in Round 1.
- Round-1 improvement that SURVIVED cross-exam -> your highest-confidence material (novel AND battle-tested). LEAD with these.
- Round-1 weakness SOLVED by a peer -> stops being a blocker; becomes a design step. Fold the fix in.
- Round-1 weakness NOBODY could solve -> a REAL CONSTRAINT. Name it as a cost or a fork. Don't bury it.
- Peer who HONESTLY DIVERGED (kept their own read) -> high-signal disagreement. A fork to surface, not to smooth.
(No Round 2 / gut-check -> synthesize the Round-1 stacks alone, same steps.)

1. CLUSTER: where did independents CONVERGE (a point multiple blind reads hit unprompted = high signal) vs genuinely DIVERGE (a real fork to surface, not paper over)? Did Round 2 CONFIRM a cluster or CRACK it?
2. TAKE THE BEST + name the tradeoffs: pull the strongest critique · the strongest SURVIVING alternative · the sharpest unexpected angle that held up — across agents and both rounds. A FUSION is allowed (A's structure + B's reframe + the R2 fix that de-risked it), not just a winner off the shelf. KEEP a minority unexpected_angle if it's the best idea in the room AND it survived attack — don't discard it for being lonely. State competing directions' real tension plainly.
3. RANK by durable OUTCOME VALUE, not ease of build. Cost = a separate note, NEVER the deciding axis. The cheap-but-shallow fix does not outrank the harder change that compounds. Don't recommend the thin option and park the rest "for later" unless a real dependency or risk forces it. Name the cost honestly — then let value lead.
4. RESOLVE, don't dodge: where agents conflict, pick a side + say why, OR name it a genuine fork only the owner can call. NEVER hand back an unrefereed "A or B".

SURFACE_UNASKED — prominently, BEFORE you finalize:
Collect the unasked-question lines. ALL honest nulls -> drop the line and move on.
A real one landed -> give it its OWN line; do NOT bury it inside the recommendation. MULTIPLE blind reads hitting it independently = highest signal (same convergence logic as clustered weaknesses). Load-bearing -> place it ABOVE the recommendation: "before acting on any of the below, the real question is ___".
WHY: a better answer to the wrong question is worth less than the right question.

"KEEP THE ORIGINAL" — legitimate, and the verdict to DISTRUST MOST:
Improvise FORCES every agent to generate ideas -> that guarantees volume, not merit. If nothing beats the original on durable value, "keep it as-is" is the RIGHT call — say so plainly and show what was tried against it. Never promote a manufactured improvement just because the pipeline produced many.
LEGAL ONLY IF: candidates were STEELMANNED (no sandbagging) AND beaten ON THE MERITS AND the GAUNTLET IS SHOWN (the real candidates + exactly why each lost).
MAX_SUSPICION: SEALED_READ == "keep it" AND verdict == "keep it" -> treat that agreement as the single most likely place the un-blind synthesizer rubber-stamped its own prior. The bar goes UP, not down: produce the strongest steelmanned challenger you can and show it STILL lost, or change the verdict.
CALIBRATION: a tool that can only ever return "here's something better" is one you learn to ignore; letting it honestly decline is what makes its pushes mean something — don't spend that credibility on a polite revert.

## OUTPUT  (plain English -> options -> recommendation -> reason; emit this shape)
```
FRESH EYES — <N> independent agents<, lenses: skeptic / customer / contrarian…>< · Round 2: yes/no>.

Strongest critiques (where they converged): <ranked, the high-signal ones>.
Best improvements, ranked by outcome value:
  1. <improvement> — value: <why it matters / compounds> · cost: <rough, a footnote> · <held up under cross-examination / reworked after Round 2 to ___>.
  2. …
Cut by cross-examination: <Round-1 idea that didn't survive Round 2, + the hole that killed it — or "none; all held">.
Weaknesses now solved (Round 2): <weakness → the fix that folds into the recommendation>.
The real fork (if any): <A vs B — the honest tension, not smoothed; include any honest Round-2 divergence>.
The unexpected angle worth keeping: <the non-obvious one that survived attack, or "none landed">.
The question you didn't ask: <highest-value unasked question — a prior decision, a symptom check, an assumption baked into the ask; flag if multiple agents hit it independently; or "none — well-scoped">.

Recommendation: <one integrated path, (recommended), stated first>. Because <brief reason>.
```
DROP the "Cut by cross-examination" + "Weaknesses now solved" lines on a gut-check (no Round 2).
CLOSE by naming what the artifact got RIGHT — fresh eyes that only tear down leave no floor to build on.

## THE BAR
PASS = the user holds a measurably STRONGER artifact + a CLEAR call. Not a transcript of opinions. Not a committee average.
SIGNALS you did it right: >= 1 unexpected angle they didn't ask for · the unasked question surfaced OR honestly cleared · a recommendation actionable without reading a single agent's raw output.
FAIL IF every agent came back agreeing with the original -> ask WHY FIRST: the brief leaked your intent (you let them grade your homework) / you didn't push the improvise stage / the alternatives were strawmen too weak to ever win = FALSE PASS -> rerun.
LEGIT if improvise genuinely ran (steelmanned alternatives generated + weighed) and the original still won on the merits -> report "keep it" plainly + show what was tried against it.
FAIL IF all you produced is reasons the current version is flawed -> you ran half the skill.
BIG_DECISION extra bars:
- The NEW ideas were themselves attacked. A Round-1 improvement reaching the recommendation un-pressure-tested = you skipped Round 2 = the exact failure this layer exists to prevent.
- NO quiet convergence: every cross-examiner suddenly agreeing with the stack it was handed = groupthink, not validation -> rerun with the anti-anchoring guard turned up.
- Independence (R1) AND scrutiny-of-the-new (R2) are BOTH required; the synthesizer must SHOW it weighed both.
