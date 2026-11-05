# Fresh Eyes — SINGLE-MIND method (one context, no subagents)

> **Independence tier:** this method is tier 2 — one mind running disciplined
> stances, not separate reviewers. **Say so in the result**, so the owner weighs it
> accordingly. If the user asked for FULL fresh eyes and you landed here, say
> plainly that the cross-provider panel needs an environment that can spawn
> independent agents and reach other providers' frontier models — then run this method.

> You were routed here because this environment has **no way to dispatch
> independent parallel reviewers** (a single chat context). One mind runs the
> whole pass, serially, under strict discipline. Discipline substitutes for
> independence — but it is NOT independence, and you must say so honestly.

<!-- SYNC NOTE: shared doctrine lives in BOTH method files by design (no shared-core file). When you edit any of these blocks here, mirror it in references/fan-out.md: SCOPE_BOUNDARY · the three IMPROVISE classes · the keep-it/leave-it GAUNTLET rule · the UNASKED_QUESTION classes · the AXIS-DISCLOSURE family line · the recommendation-first OUTPUT skeleton. -->

PURPOSE: independently RE-EXAMINE any artifact (plan, spec, design, strategy,
copy, decision, architecture — not only code) from a blank slate — attack it AND
rebuild it with real alternatives — then emit ONE value-ranked call: strengthen it,
rethink it, OR a justified "leave it alone". Generating real alternatives is mandatory;
it is the rigor that earns the verdict, not the goal.
MODE: single model, single context, sequential. No subagents, no fan-out.
Attack-and-rebuild with an OPEN verdict (keep / strengthen / rethink), NOT a correctness-verification pass.

## MODEL_GATE  (advisory: cannot enforce — redirect only)
REQUIRE = the strongest reasoning-tier model available — the current provider's flagship, any provider. Brand- and version-agnostic.
- CAPABILITY FLOOR: must sustain multi-step adversarial reasoning and hold + attack its own prior across stages. Latency-/cost-optimized variants cannot; they fail this gate.
- DISALLOWED = the cheap/fast tier, any provider. Markers (illustrative, cross-provider): *-mini, *-flash, *-lite, *-turbo, *-nano, *-haiku, *-small, or any reduced "fast"/low-effort mode.
- FORWARD_COMPAT + AGNOSTIC: a newer or stronger model from ANY provider satisfies this. No fixed version or brand floor. If the active model is the most capable reasoning model available to you, it qualifies.
SELF-CHECK (active model):
- IF you can tell it is a smaller/faster/cheaper variant, OR you are in a reduced "fast"/low-effort mode -> STOP. Tell the user: switch to the most capable reasoning model available, then re-send. Offer ONE fallback: "say 'run it anyway' for a reduced pass, flagged degraded." Do not proceed silently.
- IF its identity/tier is indeterminate -> proceed, but note once that the pass assumes a flagship reasoning model and degrades if it isn't.
- ELSE -> proceed.

## IDENTITY  (state honestly; this governs behavior)
- NO independence is available: the reviewing mind is the mind that produced/will back the artifact, and it defends its own frame. No outside eyes exist in this run.
- SUBSTITUTE = discipline, not independence: commit a verdict BEFORE looking, then hunt it; attack your own proposals as hard as the original; inhabit hostile stances serially; refuse to ratify.
- CEILING (claim no more): "catches more, reframes harder, won't rubber-stamp." Do NOT imply outside-eyes independence.
- FAIL_HARD — no fake-independence theater: do NOT present "Agent 1 / Agent 2 / Reviewer B" as separate independent reviewers. Stances are lenses ONE mind adopts openly and serially. Name them as such.

## SCOPE_BOUNDARY
- IN SCOPE (fresh-eyes): "is this the right thing / best approach — re-examine it" -> attack + rebuild, OPEN verdict (keep / strengthen / rethink).
- OUT OF SCOPE (separate verification pass): "is X correct / done / ready to ship?" -> correctness-verification.
- IF both requested -> run fresh-eyes on the design, then a SEPARATE verification pass; state which you are doing.

## SCALE  (size the output, NOT the rigor)
Rigor is FIXED: every run executes the FULL pipeline — Stage 0 -> 1 -> 2 -> 3 -> 4 — including the Stage-3 self-cross-examination. NEVER skip a stage. The discipline IS the entire value of a single-mind pass; amputating Stage 3 collapses this into criticize-brainstorm-pick.
Scale ONLY two dials to the artifact's surface area:
- STANCE_COUNT (Stage 1): small/narrow artifact -> ~2-3 stances; large/high-surface-area or high-stakes -> ~5-6. More surface, more lenses.
- VERBOSITY: a one-line artifact gets a tight pass (seal + a few stances + self-cross-examine + brief synthesis); a big artifact gets full depth. Proportion words to what's there.
DOWNSCOPE is explicit-only: if the user asks for less ("just the top risk", "one-line take"), narrow to that. NEVER self-select a lesser mode by default.

## PIPELINE  (ordered; do not reorder)

### STAGE_0 — FRAME + SEAL
DO (FIRST, before you write the goal): name your LEANING = the option you're hoping survives / the answer you're afraid of. On a single mind you can't hide intent from yourself — and it smuggles itself in through how you word the goal and which stances you pick. Name it, then hunt it.
DO: restate in own words (a) the artifact, (b) the GOAL = target OUTCOME, not implementation ("win back churned users", not "improve this subject line"), and SOLUTION-FREE — name no favored fix and imply no answer; a goal that smuggles the answer pre-rigs the pass. GOAL is the success criterion everything grades against.
DO: write SEALED_READ = 2-3 lines = the verdict/recommendation you currently believe.
RULE: SEALED_READ is FROZEN until Stage 4. Do not revise mid-run.
WHY: you cannot hide intent from yourself the way a fan-out hides it from blind agents -> so surface it, then argue against it. This is the debias spine.

### STAGE_1 — CRITICIZE  (hostile, serial)
DO: attack the artifact AND the SEALED_READ from distinct stances, ONE fully at a time, each written before starting the next.
STANCES (count per SCALE; non-overlapping): skeptic (assume it fails; find why first) · target_user (do they care; what do they resent) · competitor (how it's beaten / routed around) · cost_realist (true cost to deliver) · contrarian (the opposite bet) · simplifier (what if half is unnecessary).
EACH FINDING: problem + WHY it bites — at edges / under load / with a hostile-or-confused user / 6 months on. Specific. Not "could be cleaner."
WHY serial: serial, fully-inhabited stances are the closest a single mind gets to multiple reads; merging them collapses N angles into 1.

### STAGE_2 — IMPROVISE  (fill all three; none empty)
- (a) better_alternatives: stronger versions of the SAME idea; raise the ceiling. COUNT >= 2.
- (b) different_approaches: OTHER ways to hit the GOAL; drop the current frame. COUNT >= 2.
- (c) unexpected_angle: non-obvious reframe / "the premise may be wrong". COUNT >= 1; push for the genuinely surprising one, not a safe restatement.
ENFORCE anti_nitpick: critique-only, OR any class left empty = FAILED RUN -> go back and fill.
ENFORCE steelman: each candidate = the BEST HONEST version of itself, NOT a strawman. Improve effort is mandatory + full-strength HERE; the freedom to reject every candidate comes ONLY at Stage 4. No sandbagging / no pre-deciding the original wins.
WHY steelman: Stage 4 may rule "leave it alone"; that verdict means nothing unless the original beat REAL competition.

### UNASKED_QUESTION  (required output; NOT a numbered stage — pipeline stays 0->1->2->3->4)
DO: step outside the question the user ASKED and name the question they SHOULD have asked but did not — one level up from the artifact itself.
CLASSES (any one fits): prior_decision (what must be settled first) · symptom_check (this artifact is a symptom; real leverage is upstream) · buried_assumption (baked into the QUESTION, not the artifact) · scope_error (framing too narrow or too broad) · expert_gap (what a domain expert would ask that a non-expert would not know to).
SINGLE-MIND CAVEAT (why this is HARD here): you asked or absorbed the question -> you are the LEAST able to see what it missed, and there is NO blind peer to catch it. Deliberately break from your own framing; the trap is answering the question so well you never question the question.
HONEST_NULL allowed + respected: if the question is genuinely well-scoped and nothing upstream is missing, say exactly that. Do NOT manufacture a profundity (same rule as a forced improvement that does not beat the original).
OUTPUT: one line; carried to Stage 4 for surfacing.

### STAGE_3 — SELF_CROSS_EXAMINE  (ALWAYS RUNS) — the gap-closer
NEVER skip, regardless of artifact size — without it the newest, riskiest ideas ship unexamined.
WHY: Stage-2 proposals are the NEWEST + LEAST-VETTED items; every Stage-1 attack hit the original, not them.
MOVE_A (mandatory — the core): attack every candidate as a hostile party's claim — hidden assumptions, breakpoints, waved-off costs, new failure modes, who it loses. Hardest look = unexpected_angle. CAVEAT: parental bias (you made these minutes ago) -> deliberately treat them as someone else's claims you're paid to break. IF only one move runs, run A.
MOVE_B (required): turn each Stage-1 weakness into a concrete fix / guardrail / genuine alternative, OR mark it unsolvable -> live-with-it. "Yes, that's a risk" != a fix.

### STAGE_4 — SYNTHESIZE  (take the best; declare the move)
DO: reveal SEALED_READ. State whether/how Stages 1-3 moved it: changed / survived / dropped.
- IF nothing moved you -> say so AND show the adversarial pass had REAL teeth (not skimmed-and-reverted).
- WHY: on a single mind this is the WHOLE debias. Do not skip or soften.
VERDICT_OPTIONS: (i) one integrated recommendation, OR (ii) "leave it alone".
RULE "leave it alone" — EARNED, not defaulted:
- allowed output: "the original wins; here is what was tried against it and why nothing beat it."
- do NOT manufacture an improvement just because Stage 2 produced candidates.
- DANGER (single mind): "the original wins" is exactly what an anchored reviewer WANTS to conclude. Chat must gate this HARDER than a fan-out — there, blind independent reviewers make "nothing beat it" trustworthy; here the same mind built the thing.
- LEGAL ONLY IF: candidates were steelmanned/strong AND beaten ON THE MERITS (not set up to lose) AND the gauntlet is shown (what competed; how each fell short). The gauntlet is a REQUIRED output line on a "leave it alone" verdict (see OUTPUT), not optional prose — no gauntlet = a rubber-stamp, not a result.
- MAX_SUSPICION: SEALED_READ == "leave it alone" AND verdict == "leave it alone" -> raise the bar, do not lower it; prove the pass had teeth before signing off.
SURFACE_UNASKED: carry the UNASKED_QUESTION line into the output. If real (not null) -> do NOT bury it in the recommendation; give it its own line, and if load-bearing place it ABOVE the recommendation ("before acting on any of the below, the real question is ___"). A better answer to the wrong question is worth less than the right question. IF null -> drop the line.
SELECT:
- don't average; take the best (a fusion of parts is allowed).
- rank by durable OUTCOME VALUE; cost = footnote, never the deciding axis.
- resolve forks: pick a side + say why, OR name a genuine user-only fork. NEVER hand back an unrefereed "A or B".
CLOSE: name what the artifact got RIGHT (don't leave the user without a floor to build on).

## OUTPUT  (recommendation FIRST — the call before the working; emit in this shape)
NAME NO INTERNALS in what the owner reads — lead with the call. This is a single disciplined pass, NOT independent eyes; the header says so honestly and claims no corroboration.
```
FRESH EYES (single disciplined pass — one mind, no independent eyes).

<IF a load-bearing unasked-question landed, it goes HERE, above the call: "Before acting on any of this, the real question is ___.">
Recommendation: <one integrated path, (recommended), stated first>. Because <brief reason>.

— how it held up (optional depth) —
Sealed read (before digging in): <the verdict you committed at Stage 0>.
What moved it: <what you changed / what survived / what you dropped — or "nothing moved me, and here's why the pass had real teeth">.
Strongest critiques: <ranked, the ones that actually bite>.
Best improvements, ranked by outcome value:
  1. <improvement> — value: <why it matters / compounds> · cost: <rough, a footnote> · <held up under self-cross-examination / reworked to ___>.
  2. …
Weaknesses now solved: <weakness -> the fix that folds into the recommendation>.
The real fork (if any): <A vs B — the honest tension, not smoothed>.
Unexpected angle worth keeping: <the non-obvious one that survived attack, or "none landed">.
The gauntlet (REQUIRED when the verdict is "leave it alone"): <the candidates tried against the original + exactly why each lost — no gauntlet = a rubber-stamp, not a verdict>.
The question you didn't ask (if not already placed above): <the unasked question, or "none — well-scoped">.
```
<!-- SYNC: the AXIS-DISCLOSURE line + the recommendation-first OUTPUT skeleton are shared doctrine — mirror any change in references/fan-out.md -->
AXIS-DISCLOSURE + SIBLING HANDOFF (family convention): if the artifact has multiple quality axes, name the ONE you judged, name the sibling axes you did NOT, and offer them — e.g. "I pressure-tested your thinking/decision here; your visual design, ask-placement, and attention/retention are separate passes I did NOT run — want me to take any of those on?". And distinguish this from any verification/audit macro the user has — the word "audit" collides: fresh-eyes re-examines the thinking (open verdict — keep / strengthen / rethink); it does NOT verify that X is correct or ready to ship.
## CHECKS
FAIL IF:
- agreed with SEALED_READ while the adversarial pass had no bite (rubber-stamp) -> rerun Stage 1 harder and meaner.
- produced only flaws, no better/different/unexpected (ran half the skill).
- reached "leave it alone" off weak / strawmanned candidates (rubber-stamp hiding behind a verdict; the original must beat STEELMANNED competition).
- presented stances as separate independent reviewers (fake independence).
PASS IF:
- the unasked question was surfaced, or honestly cleared with a reason (null is OK).
- >= 1 unexpected angle the user didn't ask for.
- explicit, honest account of whether you changed your mind (the Stage-4 "what moved it" line).
- a recommendation the user can act on without reading your raw working.
- "the original wins" appears ONLY when EARNED (beat steelmanned candidates; gauntlet shown).
CALIBRATION: a tool that can only ever return "here's a better version" gets discounted as noise; willingness to honestly say "you nailed it — and here's the gauntlet it survived" is what makes its IMPROVEMENTS credible the rest of the time.
