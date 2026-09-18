# The Logic of the Methodology Sections

`model-formulation.md` and `solution-method.md` cover the conventions for writing a model and
an analysis section. This file covers the **argument** those sections are making — what has to
be established, in what order, and how it differs across the four kinds of paper in the corpus.

Method: full-text analysis of 2,067 OR / MS / M&SOM articles, classified by methodological
type from their own vocabulary. Keyword-based detection; read percentages as indicative.

**Type mix of the corpus** (a paper can carry two labels):

| | analytical / game | optimization / algorithm | empirical | simulation |
|---|---|---|---|---|
| **OR** (n=94) | 21% | **55%** | — | 3% |
| **MS** (n=1,224) | **31%** | 14% | **31%** | 1% |
| **M&SOM** (n=749) | **34%** | 17% | 21% | 3% |

Simulation-primary papers are rare in all three (1–3%); simulation almost always appears as
the *evidence* for an analytical or optimization paper rather than as the contribution.

---

## 1. What a methodology section has to prove

Three things, in this order, whatever the type:

1. **That the model is the right abstraction** — it keeps what drives the phenomenon and drops
   what does not. This is what assumptions are for, and it is an argument, not a list.
2. **That it is analyzable** — a tractable object comes out the other end. Every type has its
   own version: closed-form equilibrium, a solvable relaxation, an identified estimand, a
   calibrated simulator.
3. **That what comes out answers the question the introduction asked.** A model that is
   defensible and tractable but answers a different question is the most common deep failure,
   and it is invisible to the author because each section is locally correct.

The order is not decorative. Reviewers read the assumptions asking "is this the phenomenon?",
then the analysis asking "does this go through?", then the results asking "was this worth it?"

---

## 2. Assumption logic — the measured practice

| | **OR** | **MS** | **M&SOM** |
|---|---|---|---|
| Median numbered `Assumption k` blocks per paper | **0** | **0** | **0** |
| Mean numbered blocks | 1.0 | 0.5 | 0.4 |
| Median informal "we assume / restrict / abstract away" sentences | 4 | 3 | 4 |
| Assumption followed by justification within 2 sentences | 19% | 21% | 23% |
| Explicitly promises to relax an assumption later | 4% | 7% | **9%** |

**Formal numbered assumption blocks are the exception, not the norm.** The median paper in all
three journals has zero of them. Assumptions are made in prose, in the flow of building the
model, three or four times. Reserve a numbered `Assumption 1` for a condition that later
results explicitly invoke ("under Assumption 1, Proposition 3 holds") — that is what the
numbering is for. A draft that opens the model section with a bulleted list of eight numbered
assumptions is importing a convention from a different literature.

**Adjacent justification is a minority practice (~20%) — and that is a weakness to exploit,
not a norm to copy.** Most assumptions in print are stated and left. The ones that are defended
are defended in one of four ways, and this is the vocabulary to use:

- **Practice**: "In alignment with current practice, we assume the cell growth rate is known at
  the beginning of the initial fermentation." *(M&SOM 2023)*
- **Data**: "In practice, the bounds and the distribution of the growth rate can be determined
  based on historical data and R&D studies." *(M&SOM 2023)*
- **Precedent**: "following Smith (2019)" / "as is standard in this literature".
- **Tractability, admitted**: "for analytical tractability we assume …, and we relax this in
  Section 6."

The fourth is the strongest because it is honest and because it comes with a promise the paper
keeps. Only 4–9% of papers make that promise — a draft that makes it and then delivers an
Extensions section relaxing exactly that assumption is doing something most published papers
do not, and referees notice.

**Rule of thumb:** justify the assumptions a referee could use to reject the paper — the ones
that do analytical work (symmetry, linearity, a single period, full information) — and let the
descriptive ones stand. Justifying everything reads as anxiety; justifying nothing reads as
carelessness.

---

## 3. Build order, and the benchmark

Among analytical/game papers, an explicit **benchmark case** — first-best, centralized,
full-information, or "no contract" — appears in **57% (MS) and 68% (M&SOM)**, and its first
mention sits at **0.19–0.23 of the body**, i.e. right after the model is set up and before the
main analysis.

This is the strongest structural convention in analytical OM writing, and it is load-bearing
for two reasons: the benchmark defines the inefficiency the paper is about (without it,
"the contract improves profit" has no unit of measurement), and it gives the reader a solved
version of the model before the hard one, so the notation is already familiar when the
difficult analysis starts.

Canonical build order for an analytical paper:

```
1. Setting in prose         — who decides what, in what order, under what information
2. Primitives and notation  — sets, parameters, decision variables; notation conventions stated
3. Timing                   — the sequence of events, explicitly
4. Objective                — each player's payoff
5. Assumptions              — in prose, justified where they do analytical work
6. Benchmark                — first-best / centralized; solved, with its inefficiency named
7. Main analysis            — backward induction to the equilibrium
8. Structural results       — comparative statics, monotonicity, thresholds
```

**Extensions belong late, not woven through**: papers with an Extensions or Robustness section
place it at **0.71 (OR) / 0.80 (MS) / 0.83 (M&SOM)** of the section spine — second to last,
after the main analysis has landed and before the conclusion.

---

## 4. The result ladder

Most common order of the first three numbered result types:

| | Most common ladders |
|---|---|
| **OR** | `Lemma > Theorem` (15%), `Theorem > Lemma > Proposition` (8%), `Theorem > Lemma` (7%) |
| **MS** | `Proposition` alone (10%), `Lemma > Proposition` (8%), `Theorem > Proposition` (7%) |
| **M&SOM** | `Lemma > Proposition` (12%), `Lemma > Proposition > Corollary` (9%), `Proposition` alone (9%) |

The OM convention (MS, M&SOM) is **Lemma → Proposition → Corollary**: lemmas do the technical
work (existence, uniqueness, a closed form for a subproblem), propositions carry the economic
content the paper is about, corollaries extract the special cases that make the managerial
point. OR is Theorem-forward — a theorem is the deliverable, and lemmas are the scaffolding
under it. Using "Theorem" for a comparative-static result in an M&SOM paper reads as a
register error; using "Proposition" for the paper's central guarantee in OR undersells it.

**How results are framed, measured:**

| | **OR** | **MS** | **M&SOM** |
|---|---|---|---|
| Preceded by a set-up sentence ("The following proposition shows…") | 18% | 18% | 21% |
| Followed within ~900 characters by an intuition or mechanism cue | 22% | **29%** | **29%** |
| Followed by a practical / managerial cue | 4% | 4% | 5% |
| States that proofs are in the appendix / e-companion | 55% | 62% | **65%** |

Two readings. First, **only about one formal result in four is explained in words nearby** —
so the papers that do explain are visibly better to read, and a draft that attaches an
intuition paragraph to every proposition is above the median rather than merely conforming.
Second, **almost nothing (4–5%) bridges from a formal result to practice on the spot** — that
bridge is deferred to the numerical section and the conclusion. Do not try to make every
proposition managerially meaningful in place; make the *paper* managerially meaningful, and
let the propositions be about the model.

The published pattern for a result that matters:

```
set-up sentence  → formal statement → intuition/mechanism in words → (scope condition)
"The following proposition characterizes when the subsidy backfires."
Proposition 3. ...
"Intuitively, a higher subsidy raises the manufacturer's marginal return, which
 the supplier anticipates and extracts through the wholesale price; the net effect
 on investment is therefore negative whenever the supplier's bargaining weight
 exceeds θ̂."
```

Real example of the intuition move, from *M&SOM 2024*:

> "From Lemma 1, it can be seen that when f ≥ c_r the equilibrium recycling rate is 1. In other
> words, if the recycling reward is set sufficiently high to cover all recycling costs, all
> consumers will recycle. This implies that any reward f > c_r is suboptimal, as it only
> increases the manufacturer's costs while providing unnecessary added incentives."

Note the sequence inside one short passage: formal content → "in other words" restatement →
"this implies" consequence. That is the whole move.

---

## 5. Per-type playbooks

### 5a. Analytical / game-theoretic (MS 31%, M&SOM 34%, OR 21%)

What the section must establish: that the strategic tension is real, that the equilibrium
exists and is unique (or that multiplicity is handled), and that the comparative statics are
interpretable.

- Justify the **game form** before the functional forms. Why Stackelberg rather than Nash, why
  this leader, why this information structure — this is the modeling choice a referee attacks.
- **Solve the benchmark first** (§3). Name the inefficiency it reveals.
- Linear demand / quadratic cost need one sentence of precedent, not a defense. The
  *sequence of moves* and the *information structure* need a real argument.
- Put existence/uniqueness in a lemma, not in the text, so later results can invoke it.
- For evolutionary games specifically: state the population, the payoff-difference dynamic, and
  what a rest point means *behaviorally* before any stability analysis. Readers in OM will not
  supply that interpretation themselves, and stability results with no behavioral reading are
  the most common reason this literature reads as mechanical.

### 5b. Optimization / algorithmic (OR 55%, M&SOM 17%, MS 14%)

What the section must establish: that the formulation is correct and the hard part is named,
and that the algorithm's advantage comes from a structural property, not from tuning.

- Present the formulation, then **name the obstacle explicitly** — dimensionality, nonconvexity,
  integrality, the number of scenarios. The obstacle is the bridge to the solution section and
  should be a sentence, not an implication.
- Complexity or hardness, when available, goes early: it licenses everything that follows.
- The algorithm section should open with **why this approach** — which structural property it
  exploits (decomposability, submodularity, a convex relaxation) — before the pseudocode.
- Guarantees are the contribution: bound, convergence, approximation ratio. Tie each one back
  to the structural property that produces it.
- Reformulations earn their place by a stated benefit (tighter relaxation, fewer variables,
  separable subproblems), never by being derived.

### 5c. Empirical / econometric (MS 31%, M&SOM 21%)

What the section must establish: that the estimand answers the research question and that the
identification is credible.

- Data section first (23% of MS and 22% of M&SOM papers have one): provenance, period,
  sample construction, and what is *not* observed.
- **State the identification strategy as an argument**, not a specification: what variation is
  being used, why it is as good as random, what would break it.
- Threats to identification are named and addressed in place; robustness checks (11% of MS
  papers have a dedicated section) go late, near the Extensions position (0.80 of the spine).
- Hedge to match what the design supports. The corpus does this explicitly — e.g. "given the
  non-random geographic assignment, the single treated market, and treatment–control imbalance,
  we interpret the results as suggestive rather than definitive causal evidence."

### 5d. Simulation / digital twin (1–3% as a primary type)

Because simulation-primary papers are rare, the burden is higher: a simulation is credible in
these journals only when it is *validated*, not merely built.

- Say what the simulator is a model **of**, and what it is calibrated **against** — real system
  data, published parameters, or a solved special case.
- **Validate before you use it**: reproduce a known quantity (an analytical result in a limiting
  case, an observed operational statistic) and show the match. A simulator that has never been
  checked against anything is treated as an elaborate assumption.
- Design the experiment as a *design* — factors, levels, replications, the variance-reduction
  scheme, how many runs and why — not as a parameter sweep.
- Report uncertainty (confidence intervals across replications), and state the regime in which
  the conclusions hold.
- Structure it like the analytical papers regardless: benchmark scenario first, then the
  interventions, then the sensitivity.

---

## 6. Worked contrast — assumptions

Negative constructed; positive rebuilt from published practice.

### ✗ Assumptions as a list

> We make the following assumptions:
> **Assumption 1.** The demand function is linear: q = a − bp.
> **Assumption 2.** Both firms are risk neutral.
> **Assumption 3.** The green investment cost is quadratic: C(e) = ke²/2.
> **Assumption 4.** Information is symmetric.
> **Assumption 5.** The game is played once.

Five numbered blocks against a corpus median of zero; no justification for any of them; and no
signal about which ones matter. Assumptions 1 and 3 are conventional and need a half-sentence
of precedent. Assumptions 4 and 5 are doing the analytical work — symmetric information and a
one-shot game are exactly what a referee will attack — and they are buried at the same weight
as the functional forms.

### ✓ Assumptions as an argument

> We take the demand function to be linear and the investment cost quadratic, as is standard in
> this literature (Smith 2018, Wang 2021); the qualitative results in Section 4 do not depend
> on these forms, as we verify numerically in Section 6.
>
> Two assumptions do real work. First, we assume both parties observe each other's investment
> before committing. This reflects how joint green-resilience programs operate in practice —
> audited investment levels are contractually disclosed (IPE 2021) — and it is what allows the
> risk-sharing contract to condition on investment. Second, we assume the population shares
> adjust over repeated interactions rather than jumping to a one-shot best response, which is
> the behavioral content of the evolutionary formulation. **We relax the observability
> assumption in Section 6.2 and show that the stable investment level falls but the threshold
> structure survives.**

Three sentences of precedent for the conventional forms, a real argument for the two that
matter, and a promise that Section 6.2 keeps — the move only 9% of M&SOM papers make.

---

## 7. Diagnostic questions

- Could a referee name the one assumption that, if relaxed, would break the result? Is it
  defended in the text, or hidden at the same weight as the functional forms?
- Is there a benchmark case, and is the inefficiency it reveals named? (68% of M&SOM analytical
  papers have one.)
- Are numbered `Assumption k` blocks reserved for conditions later results actually invoke?
- Does the ladder match the journal — Lemma → Proposition → Corollary for OM, Theorem-forward
  for OR?
- Does each substantive result have an intuition sentence within a short paragraph? (Only ~29%
  of published results do; this is a cheap way to be better than the median.)
- For optimization papers: is the obstacle named in a sentence, and does the algorithm's
  advantage trace to a structural property rather than to tuning?
- For empirical papers: is the identification stated as an argument, with the threat that would
  break it named?
- For simulation papers: has the simulator been validated against something external before
  being used to draw conclusions?
- Does the analysis answer the question the introduction asked — or a neighbouring one?
