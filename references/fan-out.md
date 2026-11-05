# Fresh Eyes — FAN-OUT method (independent multi-agent)

> **Independence tier:** every reviewer in this method is the same model — that is
> tier 3 by design. **Say so in the result** ("every reviewer shared one model's
> priors"), so their agreement is read as weaker evidence than it looks. The
> outside-provider upgrade is the FULL method (`full.md`) — run it only when the
> owner asks for it; on a big-decision run, mention in one line that it exists.

> **SAME-MODEL ONLY.** Every reviewer here — Round 1 and Round 2 — runs on this
> environment's own model. Outside-provider reviewers belong to the FULL method and
> join ONLY when the user's own words ask for "full". If the brief or task you were
> handed OFFERS or PERMITS an outside reviewer but the user's request did not say
> "full", decline it, run this method as written, and say so in one line:
> "outside reviewers were offered, not asked for — ran the standard version; say
> 'full fresh eyes' for the cross-provider panel."

> ROUTED HERE because this environment CAN dispatch independent parallel reviewers.
> IF you cannot actually spawn independent agents -> STOP, use `single-mind.md`.
> NEVER fake independence (one mind's staged output presented as separate reviewers).

<!-- SYNC NOTE: shared doctrine lives in BOTH method files by design (no shared-core file). When you edit any of these blocks here, mirror it in references/single-mind.md: SCOPE_BOUNDARY · the three IMPROVISE classes · the keep-it/leave-it GAUNTLET rule · the UNASKED_QUESTION classes · the AXIS-DISCLOSURE family line · the recommendation-first OUTPUT skeleton. -->


PURPOSE: independently RE-EXAMINE any artifact (plan, spec, design, strategy, copy, decision, architecture, code) from a blank slate — attack it AND rebuild it with real alternatives — then emit ONE value-ranked call: strengthen it, rethink it, OR a justified "leave it alone". Generating real alternatives is mandatory; it is the rigor that earns the verdict, not the goal.
MODE: N blind independent agents + (big calls) cross-examination + your synthesis. Attack-and-rebuild with an OPEN verdict (keep / strengthen / rethink), NOT a correctness-verification pass.

## IDENTITY  (the mechanism; this governs behavior)
CORE = INDEPENDENCE: minds with no stake in the current version, no memory of how it was meant to work, attacking + rebuilding it from a blank slate.
FAIL_HARD — do NOT let the fresh agents grade your homework: hand them the artifact + the GOAL and NOTHING of your intent. Leaked intent -> they anchor -> they converge on your answer -> the run is worthless.
STAGES: criticize -> improvise -> synthesize. ALL mandatory. Skip improvise = a nitpick pass. Skip synthesize = a pile of opinions instead of a decision.

## SCOPE_BOUNDARY
IN (fresh-eyes): "is this the right thing / best approach — re-examine it" -> attack + rebuild, OPEN verdict (keep / strengthen / rethink).
OUT (separate verification pass): "is X correct / done / ready to ship?" -> correctness-verification.
BOTH requested -> run fresh-eyes on the design, THEN hand the result to a separate verification pass; SAY which you are doing.

## SCALE — pick fan-out WIDTH first
Stages are FIXED; width + lens diversity scale.
- QUICK_GUT_CHECK (a paragraph, a small decision) = 2-3 agents, same generalist brief; you just want non-correlated reads — treat any overlap as "worth a look", NEVER as corroboration; no proof-from-agreement claims at this tier. ROUND 1 ONLY — no Round 2 (over-build at this tier).
- BIG_DECISION (strategy, architecture, money, a launch — anything acted on hard / not cheaply unwound) = the SIX core lenses, one agent each, + domain_expert as a SEVENTH agent when the artifact turns on a specialist domain. ROUND 1 + ROUND 2.
CORE LENSES (one per agent; NON-overlapping — overlap wastes the fan-out): skeptic (assume it fails; find why first) · customer (who's it for; do they care; what do they resent) · competitor (how it's beaten / routed around) · cost_realist (what it actually takes) · contrarian (the opposite bet) · simplifier (what if half is unnecessary).
CONDITIONAL LENS: domain_expert (deep on pricing / security / legal / copy / ops) — add it whenever the artifact turns on one of those; if you leave it out, say why in the depth section.
UNSURE how wide -> GO WIDER. Independent agents are cheap; a weak decision someone ships on is not.

## MECHANISM
DISPATCH: the Workflow tool if one is exposed, else parallel Task / general-purpose sub-agents. The harness is irrelevant — the fresh-context fan-out + the three stages is what matters.
MODEL_BAND (a band, not an open ceiling):
- FLOOR: never below the top reasoning tier available. A weak reviewer produces a weak review that still LOOKS real.
- CEILING: the fan-out is N parallel passes — the one place cost multiplies. Pin reviewers explicitly; do NOT let them inherit a lighter model, and do NOT put all N on the priciest tier unless the user asked this run. Prefer ONE pass on the priciest tier over N.
BLINDNESS: each agent blind to the others AND to your intent. No shared scratchpad, no seeing each other's output. Overlap that survives independent eyes = signal; groupthink you engineered = noise.
PIPELINE: Round 1 (independent) -> Round 2 (cross-exam, BIG only) -> Synthesis (consumes BOTH rounds). Gut-check = Round 1 -> Synthesis.
SEAL TIMING: write SEALED_READ (see SYNTHESIZE) the moment Round 1 is dispatched — BEFORE you open a single Round-1 return. Numbering items and checking coverage both mean reading the stacks; a seal written after that is written to match.
ROUND 2 IS ADDITIVE, never a replacement: Round 1 stays fully independent + blind (that signal is the core asset). Round 2 stresses the NEW ideas; it never re-runs, edits, or overwrites them.

## THE BRIEF — hand each agent this and ONLY this

**FIRST, seal your own leaning (debias step — do this BEFORE you write the goal).** In one line, name the option you're hoping survives / the answer you're afraid of. Your leaning does not leak through the artifact — it leaks through (1) how you word the goal and (2) which lenses you pick. Naming it up front is what lets you catch both channels. Keep it sealed; reveal it only at synthesis (SEAL FIRST, below, already requires this).

1. THE ARTIFACT, verbatim — the actual plan / spec / copy / decision, in full. Paste it or point at the exact file (in a FULL run: paste only — `full.md` DATA RULE). NOT your summary of it.
2. THE GOAL, 1-2 plain lines = the target OUTCOME, not the implementation ("win back churned users", not "improve this email's subject line"). SOLUTION-FREE: it must name NO favored fix and imply no answer — if your goal line hints at the option you want, or reads as "should we do X?", it is leaking; rewrite it outcome-only. The success criterion they grade against. No goal -> they critique in a vacuum. Your intent -> they just ratify. GIVE the goal, WITHHOLD the intent.
3. THE OUTPUT CONTRACT (below) — load-bearing; without it agents default to a list of nitpicks and skip the improvement, the half that matters most.
4. (BIG only) their assigned LENS — and at the big-decision tier hand out the FULL non-overlapping roster, do NOT hand-pick a subset. Cherry-picking lenses (running only cost_realist, say) is itself a debias leak: it quietly buries the options you'd rather not have examined. The whole roster, not the ones that suit your leaning.
5. (BIG + genuinely CROSS-DOMAIN only) LENS DOCTRINE — when the artifact really spans a sibling skill's domain (a full sales video also lives or dies on its hooks; a launch page also has ask-placement and visual design), you MAY hand ONE agent a domain doctrine file as its judging rubric — a FILE-READ (point it at whatever method file covers that domain), NOT a skill-to-skill call. Scope hard: cross-domain artifacts worth a big-decision fan-out only. A single tweet's cold open or one paywall stays single-mind and does NOT get this.
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
LEAK TRIPWIRE (check every return): if an agent quotes your intent back, names the option you favored, or grades against your preferred fix instead of the GOAL — using knowledge the brief did NOT contain — the brief LEAKED. (If the ARTIFACT itself states a preferred option, an agent naming it is reading, not a leak.) — flag the run DEGRADED and re-dispatch that agent (or the round) with a clean brief. An agent that absorbed your leaning is not an independent read; counting it as one is the exact failure the blind fan-out exists to prevent.

## ROUND 2 — CROSS-EXAMINATION  (BIG_DECISION TIER ONLY)
STAKES_GATE: fires on the big-decision tier — a launch, an architecture, a money call, a strategy. A clear quick gut-check does NOT get a Round 2. UNSURE which tier -> treat it as BIG and run Round 2: it is one agent, and skipping it lets untested ideas ride straight into the call.
THE GAP IT CLOSES: Round 1's IMPROVISE outputs are the NEWEST + RISKIEST material precisely because they're novel — nobody pressure-tested them. Every Round-1 attack hit the ORIGINAL; the PROPOSALS were never attacked at all. Round-1-only -> they ride into synthesis COMPLETELY UNVETTED. Round 2 puts the new ideas through the same adversarial wringer + turns the surfaced criticisms into concrete fixes.

### WHO RUNS IT — ONE cross-examiner over ALL the stacks
ROUND 1 IS FROZEN — you never edit those stacks. Round 2 is a SEPARATE layer keyed to them, never a rewrite.
ONE fresh agent (same model band as Round 1) cross-examines EVERY stack, item by item. NOT one peer per stack: several copies of one model attacking several stacks is division of labor, not independent reads — headcount buys almost no independence here and every copy costs a full top-tier pass. One examiner covers the same ground AND sees what per-stack peers never could: where two stacks COLLIDE.
WANT REAL INDEPENDENCE? That is the FULL method (`full.md`): outside-provider models write their own stacks in Round 1, and this same seat sits on a panel with them in Round 2. Base Round 2 is same-model by design — disclose it.
NUMBER EVERY ITEM before dispatch, so coverage is checkable: within each stack, label every improvement — better-alternatives, different-approaches AND unexpected-angles all go in the `imp` sequence — and every weakness (A-imp-1, A-imp-2 … A-weak-1 …). (Seal first — see SEAL TIMING.)
THE EXAMINER RECEIVES — and ONLY this:
1. THE ORIGINAL ARTIFACT, verbatim + THE GOAL (the same two anchors Round 1 got). It grades against the OUTCOME, not against any stack.
2. ALL the Round-1 stacks, intact, labeled, items numbered.
3. The Round-2 contract + the no-verdict rule + the anti-anchoring guard (below), verbatim.
STILL WITHHELD: your intent · the conversation history · what you're leaning toward · your sealed read.

### ROUND-2 CONTRACT — go RESULT BY RESULT; both moves on EVERY stack, by label
MOVE_A — CRITIC_ATTACKS_THE_IMPROVEMENTS (the must-have; the actual gap):
DO: for EVERY improvement in EVERY stack (each better-alternative, different-approach, unexpected-angle), attack it the way Round 1 attacked the original: what does it quietly assume · where does it break · what does it cost that the proposer waved off · what NEW failure mode does it introduce · who does it lose.
RULE: treat every proposal as a claim to be DISPROVED, not admired. Accept none on the proposer's say-so. HARDEST look = each unexpected_angle (most novel, least examined). A proposal that genuinely holds still gets an entry: "survives — tried <X, Y>". Never manufacture a hole to look thorough.
IF you must cut, cut Move B — never Move A.
MOVE_B — IMPROVER_ANSWERS_THE_CRITICISMS (the valuable bonus):
DO: for EVERY weakness in EVERY stack, give a concrete solution / mitigation / genuine alternative — the design change, the guardrail, the different path that makes it stop biting — OR a clear statement that it's unsolvable and must be lived with.
RULE: "yes, that's a risk" != a fix (Round 1 already said that).
COLLISIONS (only an all-stacks examiner can produce these): where one stack's proposal breaks another's, or one stack's weakness kills another stack's proposal — by label ("A-imp-2 reintroduces the failure B-weak-1 names"). None found -> say "no collisions".

NO-VERDICT RULE — print in the examiner's prompt VERBATIM (this is what stops one all-seeing examiner from becoming a second synthesizer):

> You are a cross-examiner, not a judge. Go stack by stack, item by item. Attack
> every proposal, answer every criticism, and flag collisions — each by its label.
> REQUIRED, and NOT verdicts: how hard each hole bites (judged on its own); for
> each weakness, a concrete fix OR an honest "live with it, because…"; pointing
> out where two items CONFLICT; and where your own read of the artifact differs —
> or "converged honestly" if it doesn't. Never invent a fix or a disagreement to
> fill a line. FORBIDDEN: ranking stacks or proposals against each other, picking
> winners, blending ideas together, recommending an overall course of action, or
> summarizing "the best ideas." Choosing happens later, by someone else; doing it
> here contaminates the result. If you catch yourself writing "overall", "the
> winner", or "I'd go with", stop and delete it.

ANTI-ANCHORING GUARD — print in the examiner's prompt VERBATIM:

> You are cross-examining other analysts' stacks, not joining any of them. Attack
> their proposals and solve their criticisms **from your own independent read of
> the artifact** — keep your own judgment intact. Do **NOT** adopt their framing,
> defer to their conclusions, soften your take to agree, or let any stack become
> the new anchor you converge on. The failure mode here is groupthink: minds
> collapsing into one view, which destroys the different approaches and unexpected
> angles this exercise exists to produce. If, after honestly cross-examining, you
> still see the artifact differently, **say so** — your divergence is signal. I
> want friction, not consensus.

EXAMINER RETURNS (a separate layer keyed by label, never merged into the stacks):
`per-stack[]` = { stack · `attacks[]` (item label · the hole · how hard it bites — OR "survives — tried X, Y") · `solutions[]` (item label · the concrete fix — OR "live with it, because…") } · `collisions[]` · `where-I-diverge` (1 line, or "converged honestly").
COVERAGE CHECK (yours, before synthesis): every numbered improvement and weakness has an entry. Missing items -> they go into the ONE RE-ASK (below). Still missing after it -> mark those items NOT CROSS-EXAMINED: they can never lead the recommendation or count as "survived", and the depth section names them.
THINNING means entries that name no concrete mechanism (no assumption, breakpoint, cost, or fix) — NOT short entries. "survives — tried <X, Y>" is a full entry when X and Y are concrete. SCALE ESCAPE: if a pass thins, split the stacks across TWO examiners, each with the FULL brief and told which stacks are theirs, PLUS one collision-only pass over ALL stacks — a split must never hide a cross-half collision. Never back to one-per-stack.
VERDICT LEAK: a separable ranking / winner-pick / overall recommendation -> discard that part unread. Woven through the item entries (no clean part to cut) -> it goes into the ONE RE-ASK with the no-verdict rule restated. Still woven after it -> exclude that return and dispatch ONE fresh examiner; if that also fails, every item is NOT CROSS-EXAMINED and you say plainly that Round 2 failed.
ONE RE-ASK PER EXAMINER — missing labels, a missing move, and a woven verdict all ride in a single re-ask (the FULL brief again, all stacks — a partial packet cannot see collisions — told exactly what to supply). No loops. After it: improvements still lacking a Move-A entry are NOT CROSS-EXAMINED; weaknesses still lacking a Move-B entry are UNTESTED, not unsolvable (see synthesis).
REPLACEMENT: only an EXCLUDED examiner is replaced — at most ONE replacement, which gets its own first dispatch and its own one re-ask. If the replacement also ends excluded or empty, ROUND 2 FAILED: every item is NOT CROSS-EXAMINED, and the run still closes (see THE BAR).
AFTER ROUND 2 you hold TWO layers: the frozen Round-1 stacks + ONE cross-examination layer keyed to them. Round 2 NEVER overwrites Round 1 — if the examiner's attack is wrong, the original proposal still stands on its Round-1 merits; synthesis weighs both. NOTHING is merged yet — that's synthesis.

## SYNTHESIZE — one integrated result, not an average (YOUR job, not theirs)
RULE: don't average — TAKE THE BEST. Averaging independent views back to the bland middle throws away the exact edge you paid for. Integrate, don't tally.

SEAL FIRST — you are the ONLY un-blind link:
DO: BEFORE opening a single Round-1 return (see SEAL TIMING — that includes numbering them for Round 2), write SEALED_READ = 2-3 lines = the recommendation you currently believe.
THEN read everything. THEN state plainly whether/how the stacks MOVED you — what you changed your mind about / what survived / what you dropped.
IF nothing moved you -> say so AND show the independent reads genuinely agreed (not that you skimmed past them).
WHY: your prior is exactly the bias the blind fan-out existed to remove, and it leaks straight back in here at the last step. Declare the bias; do NOT amputate the context (you need the owner's context to rank by value).

CONSUME BOTH LAYERS (when Round 2 ran):
- Round-1 improvement HOLED badly by the cross-examiner -> drops in rank or out. Novel != survived. Don't promote it for being exciting in Round 1.
- Round-1 improvement that SURVIVED cross-exam -> your highest-confidence material (novel AND battle-tested). LEAD with these.
- Round-1 weakness SOLVED by the cross-examiner -> stops being a blocker; becomes a design step. Fold the fix in.
- Round-1 weakness the examiner genuinely tried and marked "live with it, because…" -> a REAL CONSTRAINT. Name it as a cost or a fork. Don't bury it.
- Round-1 weakness with NO Round-2 entry (Move B trimmed, or item not cross-examined) -> UNTESTED. Say so plainly; never present it as a constraint the owner must live with.
- Cross-examiner who HONESTLY DIVERGED (kept its own read) -> high-signal disagreement. A fork to surface, not to smooth.
- COLLISION flagged (two ideas that can't both ship as written) -> resolve it, or name it as a fork. Never recommend both halves of a collision.
(No Round 2 / gut-check -> synthesize the Round-1 stacks alone, same steps.)

1. CLUSTER: where did independents CONVERGE vs genuinely DIVERGE (a real fork to surface, not paper over)? Did Round 2 CONFIRM a cluster or CRACK it? READ CONVERGENCE HONESTLY: the agents are the SAME model, so they share blind spots — agreement means a point is SALIENT and survived reframing, NOT that it is proven correct. Weight it by LENS-DISTANCE: a skeptic and a customer landing on the same point is real signal; two similar lenses agreeing is near-noise; a lone sharp dissent can outrank a same-lens chorus. Never sell "they agreed" to the owner as proof.
2. TAKE THE BEST + name the tradeoffs: pull the strongest critique · the strongest SURVIVING alternative · the sharpest unexpected angle that held up — across agents and both rounds. A FUSION is allowed (A's structure + B's reframe + the R2 fix that de-risked it), not just a winner off the shelf. KEEP a minority unexpected_angle if it's the best idea in the room AND it survived attack — don't discard it for being lonely. State competing directions' real tension plainly.
3. RANK by durable OUTCOME VALUE, not ease of build. Cost = a separate note, NEVER the deciding axis. The cheap-but-shallow fix does not outrank the harder change that compounds. Don't recommend the thin option and park the rest "for later" unless a real dependency or risk forces it. Name the cost honestly — then let value lead.
4. RESOLVE, don't dodge: where agents conflict, pick a side + say why, OR name it a genuine fork only the owner can call. NEVER hand back an unrefereed "A or B".

SURFACE_UNASKED — prominently, BEFORE you finalize:
Collect the unasked-question lines. ALL honest nulls -> drop the line and move on.
A real one landed -> give it its OWN line; do NOT bury it inside the recommendation. MULTIPLE blind reads hitting it independently = strongest SALIENCE (worth surfacing, still not proof — same-model reads share blind spots), same convergence logic as clustered weaknesses. Load-bearing -> place it ABOVE the recommendation: "before acting on any of the below, the real question is ___".
WHY: a better answer to the wrong question is worth less than the right question.

"KEEP THE ORIGINAL" — legitimate, and the verdict to DISTRUST MOST:
Improvise FORCES every agent to generate ideas -> that guarantees volume, not merit. If nothing beats the original on durable value, "keep it as-is" is the RIGHT call — say so plainly and show what was tried against it. Never promote a manufactured improvement just because the pipeline produced many.
LEGAL ONLY IF: candidates were STEELMANNED (no sandbagging) AND beaten ON THE MERITS AND the GAUNTLET IS SHOWN (the real candidates + exactly why each lost). The gauntlet is a REQUIRED output line on any "keep it" verdict (see OUTPUT), not optional prose — no gauntlet shown = a rubber-stamp, not a result.
MAX_SUSPICION: your SEALED_READ leaned toward keeping the original AND the verdict keeps it ("keep it", "keep as-is", "leave it alone" — any wording; judge the meaning, not the string) -> treat that agreement as the single most likely place the un-blind synthesizer rubber-stamped its own prior. The bar goes UP, not down: produce the strongest steelmanned challenger you can and show it STILL lost, or change the verdict.
CALIBRATION: a tool that can only ever return "here's something better" is one you learn to ignore; letting it honestly decline is what makes its pushes mean something — don't spend that credibility on a polite revert.

## OUTPUT  (recommendation FIRST — the call before the machinery; plain English, emit this shape)
NAME NO INTERNALS in what the owner reads: no "agent", "Round 2", "lens", "stack", "cross-examination" in the headline or the recommendation. The ONE exception is the confidence tag — how many blind reads clustered on the call — because that basis is decision-relevant (and per convergence-honesty it means "salient", NOT "proven"). The owner gets the call at the top; everything else is optional depth below.
```
FRESH EYES — <confidence tag, e.g. "from 6 blind reads that clustered here — salient, not proof">.

<IF a load-bearing unasked-question landed, it goes HERE, above the call: "Before acting on any of this, the real question is ___.">
Recommendation: <one integrated path, (recommended), stated first>. Because <brief reason>.

— optional depth (skip if you just want the call) —
Strongest critiques (where blind reads clustered): <ranked>.
Best improvements, ranked by outcome value:
  1. <improvement> — value: <why it matters / compounds> · cost: <rough, a footnote> · <held up under scrutiny / reworked to ___>.
  2. …
Ideas that didn't survive scrutiny: <a proposal that got holed + the hole that killed it — or "none; all held">.
Weaknesses now solved: <weakness → the fix that folds into the recommendation>.
The real fork (if any): <A vs B — the honest tension, not smoothed>.
The unexpected angle worth keeping: <the non-obvious one that survived attack, or "none landed">.
The gauntlet (REQUIRED when the verdict is "keep it as-is"): <the real candidates tried against it + exactly why each lost — no gauntlet = a rubber-stamp, not a verdict>.
The question you didn't ask (if not already placed above): <the unasked question, or "none — well-scoped">.
```
GUT-CHECK OUTPUT (no Round 2 ran): DROP the "Ideas that didn't survive scrutiny" + "Weaknesses now solved" lines, AND reword what's left so nothing claims a test that never happened — confidence tag "from <N> quick reads — overlap is worth a look, not corroboration"; each improvement tagged "untested at this tier" (never "held up under scrutiny"); the unexpected-angle line reads "the non-obvious one worth a look (untested)".
CLOSE by naming what the artifact got RIGHT — fresh eyes that only tear down leave no floor to build on.
<!-- SYNC: the AXIS-DISCLOSURE line + the recommendation-first OUTPUT skeleton are shared doctrine — mirror any change in references/single-mind.md -->
AXIS-DISCLOSURE + SIBLING HANDOFF (family convention): if the artifact has multiple quality axes, name the ONE you judged, name the sibling axes you did NOT, and offer them — e.g. "I pressure-tested your thinking/decision here; your visual design, ask-placement, and attention/retention are separate passes I did NOT run — want me to take any of those on?". And distinguish this from any verification/audit macro the user has — the word "audit" collides: fresh-eyes re-examines the thinking (open verdict — keep / strengthen / rethink); it does NOT verify that X is correct or ready to ship.

## THE BAR
PASS = the user holds a CLEARER, better-founded CALL on the artifact — a stronger version, a rethink, or a WELL-EARNED "keep it as-is" — reached impartially. Not a transcript of opinions. Not a committee average. (A keep-it verdict passes only when it beat real, steelmanned alternatives — see the gauntlet.)
SIGNALS you did it right: >= 1 unexpected angle they didn't ask for · the unasked question surfaced OR honestly cleared · a recommendation actionable without reading a single agent's raw output.
FAIL IF every agent came back agreeing with the original -> ask WHY FIRST: the brief leaked your intent (you let them grade your homework) / you didn't push the improvise stage / the alternatives were strawmen too weak to ever win = FALSE PASS -> rerun.
LEGIT if improvise genuinely ran (steelmanned alternatives generated + weighed) and the original still won on the merits -> report "keep it" plainly + show what was tried against it.
FAIL IF all you produced is reasons the current version is flawed -> you ran half the skill.
BIG_DECISION extra bars:
- The NEW ideas were themselves attacked. A Round-1 improvement reaching the recommendation un-pressure-tested = you skipped Round 2 = the exact failure this layer exists to prevent.
- NO quiet convergence: a cross-examination where every proposal "survives" and nothing collides is SUSPECT -> rerun it ONCE with the anti-anchoring guard turned up. If the rerun is also clean AND its "survives" entries name concrete attempts, accept it and say so ("two cross-examinations found no holes"). Never invent a hole to clear this bar.
- COVERAGE: every numbered Round-1 item has a Round-2 entry OR is explicitly marked NOT CROSS-EXAMINED / UNTESTED and named in the depth section. An item in neither state rode in unvetted. None of the marked items leads the recommendation — EXCEPT when Round 2 failed outright: then still give the call, labeled "UNTESTED — Round 2 failed; nothing here was cross-examined", and offer a rerun. A run must always close.
- Independence (R1) AND scrutiny-of-the-new (R2) are BOTH required; the synthesizer must SHOW it weighed both.
