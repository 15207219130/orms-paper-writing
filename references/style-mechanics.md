# Style Mechanics: Tense, Voice, Hedging, and Prose Discipline

These conventions apply to *every* section, which is why the workflow loads this file on almost every
task. They are the difference between prose that reads as a top-journal paper and prose that reads as
a competent draft. Most are invisible when done right and conspicuous when done wrong.

## Self-containment: write for a reader who will never see your code

This is the single most damaging failure mode when drafting a paper inside a repository, and it is the
one to guard against most actively. When you have the implementation open in context — the model code,
the experiment scripts, the config files, the data loaders — you unconsciously start treating the
codebase as shared knowledge with the reader and write compressed, implementation-anchored references
that are intelligible *only* to someone who also has the code open. But the journal reader has the PDF
and nothing else. A reviewer who hits a sentence they cannot understand without your repository will
treat it as a defect, and rightly: a top-journal paper is self-contained by construction. **Every
symbol, parameter value, instance, data field, and algorithmic step that appears in the paper must be
defined in the paper, in the paper's own mathematical and conceptual vocabulary — never in terms of
code artifacts that live only in the repository.**

The leak takes several recognizable forms. Watch for and rewrite each:

- **Code identifiers used as if defined.** "the `solve_subproblem()` routine," "we update `x_ijk` in
  the inner loop," "the `Instance` object," "the `df_demand` dataframe," "the `cfg.penalty` flag."
  Function names, class names, variable names from the code, and config keys mean nothing to the
  reader. Replace them with the paper's notation and concepts: "the pricing subproblem (§4.2)," "we
  update the routing variables $x_{ijk}$," "each problem instance," "the demand data."
  *(Defined mathematical symbols like $x_{ijk}$ are fine — they were introduced in the model. The code
  variable `x_ijk` is fine only because it coincides with that symbol; `n_trucks` is not — use $|K|$.)*
- **File names, paths, scripts, libraries, repo structure.** "as set in `params.json`," "see
  `run_experiment.py`," "we call `gurobipy`'s `optimize()`," "the results in `output/run3/`." None of
  these belong in the prose. The methodology must read the same whether or not the code exists. (Naming
  the solver and version — "solved with Gurobi 11.0" — is correct and expected; naming *your* scripts
  is not.)
- **Hard-coded magic numbers lifted from the code.** "we set the penalty to 1000," "the tolerance is
  1e-6," "we use 500 iterations" — where those values are constants copied from the source. Surface
  each into a *defined parameter with units and a reason*, or into the experimental-setup /
  parameters table: "the unserved-demand penalty is set to $p_i = \$50$ per request, reflecting the
  estimated goodwill cost (§6.1)." A bare number that the reader cannot trace to a defined quantity is
  a leak.
- **Algorithms described as code rather than as method.** "we loop over all customers and append
  feasible ones to a list, then sort by ratio" is an implementation transcript. Present the algorithm
  as language-agnostic pseudocode or mathematical steps over *defined* symbols, describing *what* is
  computed and *why*, not the data structures that happen to hold it.
- **Results untraceable to a stated setup.** A table or number whose instances, parameters, or
  generating process were defined only in a script. Every reported result must rest on an experimental
  setup described in the paper (instances, parameter ranges, benchmarks — see
  `numerical-experiments.md`); the code is an *online companion that supplements* the description, never
  a *prerequisite* for understanding it.
- **Index/field meanings that live only in the data.** "column 3 is the energy need," "the third
  element of the tuple." Define what each quantity is in the paper's notation; the reader never sees
  your data schema.

The reliable test, applied sentence by sentence to anything you draft from code: *could a reader who
has only the PDF — no repository, no scripts, no data files — understand this, and in principle
reproduce it from the paper alone?* If a sentence needs the code to be intelligible, translate it into
defined notation and concepts before it goes in. When you genuinely cannot surface a value or setup
because the user hasn't supplied its meaning or units, flag it (e.g. "[define: what is this 1000 — units
and rationale?]") rather than transcribing the raw artifact and moving on.

The one legitimate place to name the repository is a reproducibility statement — "the code and data are
available in the online companion" — and even there, the paper's methodology must stand on its own
without it.

## Separate the general method from the specific instantiation

A paper proposes a *method* and then *evaluates* it on one concrete configuration — a particular
dataset size, a chosen number of classes/buckets/regions, and specific hyperparameter values
(retrieval depth, sample counts, iteration budgets, tolerances, penalty weights). A common and
quietly damaging failure is to let the instantiation's numbers leak into the description of the
*method itself*, so the framework reads as though those numbers were requirements. When the abstract
says the method "retrieves from a 104-record corpus," or the method section says "each of the 104
records is assigned to one of 11 buckets," or "we run 500 iterations," a reviewer immediately wonders:
*does this only work at 104? at 11 buckets? is 500 load-bearing?* The generality the paper is trying
to claim is undercut by its own framing. This is the same discipline as self-containment, one level
up: there you keep the *code* out of the method; here you keep *this evaluation's particular numbers*
out of it.

The rule: **describe the method with its instantiation-specific quantities as named inputs (symbols),
and report the concrete values in the experimental-setup section, explicitly labeled as choices for
this evaluation rather than constants of the method.** State the independence outright where it
matters: "nothing in the framework depends on the corpus size or the number of buckets." The method
should read identically whether the corpus holds 100 records or 100{,}000.

Where each number belongs:

- **Method / abstract / framing — general.** Use symbols ($N$ samples, top-$k$ retrieval, $K$
  iterations, tolerance $\varepsilon$) and point forward to where they are set. No bare
  evaluation-specific count appears here as if intrinsic.
- **Experimental setup — concrete, labeled as choices.** Collect the values in a configuration
  paragraph or table: "we set $k=4$, $N=20$, $K=3$…; these are configuration choices, not constants
  of the method, and can be retuned for a different instance or compute budget without changing the
  pipeline."
- **Results — concrete.** Reported numbers naturally carry the specifics of the run ("on the
  31-instance test set, the method…"); that is exactly their job, so leave them.
- **Artifacts you contribute** (a dataset, benchmark, or corpus) — concrete *and* legitimate: a
  benchmark genuinely has a size. Keep the count, but label it as the instantiation ("104 active
  records in the instantiation evaluated here") and keep it textually separate from the framework that
  consumes it; a framework contribution and a benchmark contribution are two different things.

The reliable test, applied to any method-describing sentence: *if this specific number were different,
would the sentence become false?* If yes, the number is being treated as a constant of the method —
replace it with a symbol and move the value to the setup. A magic count sitting in the abstract or the
method section is the tell.

## Voice: first-person plural "we," active

The corpus is uniformly **"we"-active**. "We show," "we propose," "we conduct," "we observe." The
authors are agents who do things. Passive voice is reserved for two places: **setup/definitions**
("A control U(x,r) is said to be a bid-price control if…", "demands are assumed to be non-negative")
and **implementation/data details** ("the data is provided directly by the platform," "instances are
generated from…"). Single-author papers still use "we" by convention; do not switch to "I."

Avoid the bureaucratic passive that hides the agent ("it was found that," "an algorithm is
proposed"). Name who does what.

## Tense by section

Tense tracks *what kind of thing* you are describing:

- **Prior work (lit review):** past for what a paper did ("Belobaba (1987) proposed…"), present for
  claims that still hold / attributed results ("Talluri and van Ryzin show that…").
- **Model and theory:** present / timeless ("The network has m legs…", "Proposition 1 establishes…",
  "the optimal policy consists of…"). Definitions are timeless.
- **Proof steps:** present and imperative ("Note that…", "Suppose…", "Fix a sample path ω…"), past
  for a completed sub-step within the argument.
- **Completed experiments:** past for what you *did* ("we conducted experiments using two networks"),
  present for what an exhibit *shows* ("Table 5 shows…", "the gains are on the order of 1–5%").
- **Conclusion:** present for the standing contributions, future/modal for directions.

## Hedging: match the verb to the strength of the claim

This is the most reviewer-sensitive habit in the corpus. **The verb register must track the claim
type**, or the paper either overclaims (fatal with referees) or underclaims (looks timid):

- **Proven / theoretical results — hard verbs, no hedge:** "we show," "we prove," "we establish,"
  "it is optimal," "the policy is asymptotically optimal." A theorem is not "suggested."
- **Empirical / simulation / estimated claims — hedged verbs:** "suggests," "tends to," "appears to,"
  "seems to," "may," "is consistent with." "The DCOMP method appears to be more robust…"; "this may
  explain why… the LP bid-prices seem to generate more revenue."
- **Generality caveats on numerical results:** state the scope honestly — "the magnitude of these
  results is specific to this particular set of numbers and choice probabilities"; "such asymptotic
  analyses are known to be quite crude… one must treat such performance guarantees with a fair degree
  of caution."
- **Causal claims from observational/quasi-experimental data:** explicitly downgrade — "suggestive
  rather than definitive causal evidence."

A useful mantra: *prove* in the theory sections, *suggest* in the experiments, and never blur the
two. When uncertain whether a claim is supported at the strength stated, hedge it down — it is far
safer with reviewers and is what the corpus authors do.

## Prose discipline

- **Flowing paragraphs, not bullet points,** for the argument itself. The body of these papers is
  continuous prose. Reserve enumerated structures for the places where the corpus actually uses them:
  a numbered/bulleted contributions list, a stepwise proof roadmap, a constraint-by-constraint
  walkthrough, an experiment plan, a future-work menu. Default to prose; enumerate only with reason.
- **Topic sentences.** Each paragraph opens with the point it makes; the rest supports it. Reviewers
  skim — the first sentence of each paragraph should carry the argument.
- **Introduce every display equation with a clause** and interpret it after if it isn't
  self-evident. No naked equations dropped between paragraphs.
- **One term per concept, fixed for the whole paper.** Decide on "fleet allocation" (not sometimes
  "fleet assignment"), "efficient set," "bid price" — and never silently introduce a synonym. Define
  on first use (often italicized), then reuse verbatim.
- **Connectives that do work.** "Note that…", "However…", "In contrast…", "Indeed…", "Specifically…",
  "Roughly speaking…" — the corpus uses these to signal logical moves. Use them to mark genuine
  turns, not as filler.

## Word choice: terms that read as non-OR register

Some words are technically correct but sit outside the working vocabulary of OR/MS papers, and a
native-register reader notices them. Prefer the idiom the corpus actually uses.

- **The "certificate" family — `certificate` / `certified` / `certify` / `certification` — is
  uncommon in OR/MS prose and should be avoided**, even in exact-algorithm sections where the
  *concept* (a proof that a bound, gap, or the pricing subproblem is optimal) is central. Do not
  call a bound, gap, or termination "certified." Rewrite by grammatical role: the verb →
  *prove … optimal* / *proves* ("$\bar c^\star\ge0$ **proves** the RMP relaxation is optimal";
  "pricing is **proven optimal**"); the noun → *optimality guarantee*, *proof of optimality*, or
  *convergence guarantee*; "certified optimality gap" → *guaranteed optimality gap* (or plain
  *optimality gap*); "certified bound" → *valid bound*; a checking/verification oracle that
  "certifies" components → *validates* / *confirms*. Note that *guarantee*, *valid*, *prove*, and
  *validate* are all fine OR register — the term to drop is specifically the *certif-* family.
  (User-confirmed preference.)

## Avoid AI-writing tells

LLM prose has recognizable fingerprints that read as un-academic and can make a careful reviewer
suspicious. Watch for and remove:

- **The rule of three everywhere** — reflexively grouping things in triples ("robust, scalable, and
  efficient"). Real papers vary their list lengths.
- **Inflated / promotional adjectives** — "powerful," "seamless," "cutting-edge," "novel" used as
  decoration. The corpus earns "novel" by showing novelty, and otherwise stays plain. ("Strikingly
  simple" appears — but as an earned observation about a specific result, not as boilerplate.)
- **Empty signposting** — "It is important to note that," "It is worth mentioning that" used with
  nothing important following. Cut, or make the following clause actually substantive.
- **Vague attributions** — "studies have shown," "it is widely believed" without a citation. In this
  genre every such claim is pinned to a specific reference (see `citations-and-coherence.md`).
- **Em-dash overuse**, **negative parallelisms** ("not only… but also…" on repeat), and **superficial
  "-ing" clause analyses** tacked onto sentence ends ("…, highlighting the importance of…",
  "…, underscoring its significance").
- **Uniform sentence rhythm** — vary sentence length; mix short declaratives with longer complex
  sentences as the corpus does.

For a focused de-AI pass on a finished draft, the **`humanizer`** skill is purpose-built for this and
can be invoked.

## Cross-references and house mechanics

- **Forward:** "In §5 we develop…", "Section 4 presents our solution approach." Use section names or
  numbers consistently with the journal's convention (§ symbol vs. "Section").
- **Backward:** "by Proposition 1," "as shown in Table 3," "consistent with the bound in Theorem 1."
- **Proofs:** `Proof. … □` blocks; long proofs to an appendix/e-companion with a pointer.
- **Number formal results; don't give them a parenthetical title.** State theorem-like results bare —
  `\begin{proposition}\label{...}`, so the reader meets "Proposition 3" — not with the optional
  `[title]` argument (`\begin{proposition}[Endogenous monotonicity of cleaning intensity]`). The
  lead-in sentence before the statement and the in-words restatement after it already carry the
  descriptive content, so a bracketed title just duplicates them in a worse register and clutters the
  statement; put that content in the surrounding prose. This targets the numbered results
  (`theorem`/`lemma`/`proposition`/`corollary`); `remark`/`assumption`/`definition` may keep a short
  title when it aids navigation. (User house preference — both titled and untitled results occur in
  the journals.)
- **Numbers:** keep equation/section/theorem numbering consistent after edits (a frequent silent
  breakage — verify in the coherence pass).
- **Captions are brief — not a second body.** A table or figure caption identifies the exhibit and
  gives the minimum key to read it (what the columns/axes are, the instance, the units) — *not* a
  paragraph of analysis, derivation, or method exposition. The interpretation, the takeaway, and the
  mechanism belong in the body text that introduces the exhibit (see the locate→read→interpret rhythm
  in `numerical-experiments.md`); a worked example belongs in the prose, with the figure merely
  illustrating it. If a caption has grown to several sentences of argument, that argument is in the
  wrong place — move it into the text and leave a one- or two-sentence caption.

## Self-check

- **Self-contained?** Could a reader with only the PDF understand every sentence — no code identifiers,
  file/script names, config keys, untraced magic numbers, or implementation-transcript algorithms; every
  symbol/value/instance defined in the paper's own notation?
- **Method vs. instantiation separated?** No evaluation-specific count (dataset size, number of
  classes/buckets, hyperparameter value) baked into the abstract or method framing as if intrinsic;
  method described with symbols, concrete values in the setup labeled as choices, contributed
  artifacts' sizes labeled as the instantiation — would the framing survive the numbers changing?
- "We"-active throughout, passive only for definitions and implementation details?
- Tense correct per section (timeless model/theory, past+present in experiments, past for prior
  work)?
- Verb register matches claim strength — proven results stated hard, empirical results hedged, scope
  caveats present?
- Argument in flowing prose; enumerations only where the genre uses them?
- One term per concept, fixed throughout; every display introduced and (if needed) interpreted?
- AI tells removed (rule-of-three, promo adjectives, empty signposting, vague attributions, em-dash
  spam)?
- Non-OR-register terms avoided — no *certif-* family (certificate/certified/certify/certification);
  use prove-optimal / optimality guarantee / valid bound / guaranteed gap / validate instead?
- Captions kept short (exhibit + reading key), with the analysis, takeaway, and any worked example in
  the body text rather than packed into the caption?
