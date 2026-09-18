# Writing the Problem: a house style for optimization papers

Built from the problem statements of the corpus's **346 optimization / algorithmic papers** — in
particular the **114 M&SOM papers that carry an explicit `Problem definition:` block** (a
gold-standard corpus: the journal forces authors to write the problem in one place) and the **213
optimization papers with a recoverable model or problem-statement section**.

This is a writing file: the order sentences come in, the verbs, the assumption prose, the naming
conventions. For *what the model should be*, see the `orms-model-design` skill.

---

## 1. The problem definition — measured shape

| | |
|---|---|
| Median length | **64 words, 3 sentences** |
| Interquartile range | 44–94 words, 2–4 sentences |

Where each element first appears (0 = first sentence, 1 = last), with how often it appears at all:

| Element | Present | Median position |
|---|---|---|
| The **decision** being made | **68%** | **0.00** |
| The **problem sentence** ("we study the problem of…") | **65%** | **0.00** |
| The **uncertainty** | 32% | 0.17 |
| The **constraint / scarcity** | 31% | 0.33 |
| Why it is **hard** | 25% | 0.50 |
| What is **done today** | 11% | 0.50 |
| The **distinctive feature** (the twist) | 15% | 0.50 |
| The **objective** | 36% | **1.00** |
| A **method** named | 16% | 0.00 |
| A statistic / stake | 11% | 0.00 |

Three things to take from this.

**The decision comes first and the objective comes last.** Not the other way round. Drafts almost
always open with the objective ("We minimize total cost subject to…") because that is how the model
is written down; published problem definitions open with *who decides what*, and the objective
arrives as the closing clause. Position 0.00 versus position 1.00 is the sharpest single contrast
in this measurement.

**Keep the method out.** Only 16% name a method inside the problem definition, and only 11% carry a
statistic. The problem definition is not the hook and not the methods summary — the hook lives in
the introduction's first paragraph, the method in the `Methodology` block. A problem definition that
says "we develop a branch-and-price algorithm" has spent its space on the wrong thing.

**Most of it is optional.** Uncertainty, constraint, difficulty, current practice and the twist each
appear in only 11–32% of definitions. The obligatory core is *decision + problem sentence +
objective*, in that order, in about 64 words. Everything else is earned.

---

## 2. The four slots

```
[1] SETTING + DECIDER + DECISION        ← first sentence, always
[2] WHAT MAKES IT NON-TRIVIAL           ← one clause or one sentence: the uncertainty,
                                          the coupling, the scarcity, or the twist
[3] THE PROBLEM SENTENCE                ← "We study the problem of ⟨gerund⟩ ⟨object⟩"
[4] THE OBJECTIVE                       ← last, as a purpose clause
```

Slots 1 and 3 often merge into a single sentence, which is why both sit at position 0.00.

**Worked fills, from published M&SOM problem definitions:**

> **[1]** "Mobile outreach teams of healthcare workers visit a fixed set of remote sites to provide
> healthcare services. **[2]** Because of dynamics in demand and supply, once-rational site-to-team
> assignment decisions can become far from optimal over time. **[3+4]** This paper considers the
> problem of reassigning sites to teams to maximize effectiveness."

> **[1]** "We consider a surgery sequencing and scheduling problem with uncertain durations of
> surgeries in the context of an operating theater. **[2]** From real data collected from a hospital,
> we observe the common practice, namely, 'to follow,' in which surgeries are conducted sequentially
> and immediately one after another, according to a specific schedule."

> **[1+3]** "We study a nurse staffing problem under random nurse demand and absenteeism.
> **[2]** Although the demand uncertainty is exogenous, the absenteeism uncertainty is
> decision-dependent, that is, the number of nurses who show up for work partially depends on the
> nurse staffing level."

> **[1]** "Given the variety of urgency levels in highly utilized operating rooms, capacity
> allocation decisions can have a major impact on how wait times are rationed. **[3]** We examine a
> longer-term sequential capacity planning problem in which a hospital allocates operating room time
> to different surgical specialties. **[4]** We seek to minimize an urgency-weighted wait-time
> metric."

Notice slot 2 in each: *dynamics make old assignments stale*; *the observed practice is
"to-follow"*; *absenteeism is decision-dependent*. One clause, and it is always the thing that makes
this problem not a textbook problem. That clause is the paper.

---

## 3. Two legitimate openings, and how to choose

**53% open on the world, 47% open on the paper.** Both are house style; they do different jobs.

| Opening | Share | Use when |
|---|---|---|
| A fact about the world (noun subject) | 46% | The setting is unfamiliar, or its scale is the reason to care |
| "We …" | 36% | The problem class is already recognized by the reader |
| Adverbial ("In / During / Given / Under…") | 11% | A condition defines the problem ("Given the variety of urgency levels…") |
| "This paper …" | 7% | — |

World-first: *"Human donor milk provides critical nutrition for millions of infants born preterm…
Approximately half of all milk banks in North America do not have the resources to measure
macronutrient content, which means pooling is done heuristically."*
Paper-first: *"We study a nurse staffing problem under random nurse demand and absenteeism."*

Rule of thumb: if a referee in your area would not immediately recognize the operational setting,
open on the world. If they would, open on the paper and spend the saved words on slot 2.

---

## 4. Verbs

Counts across the 114 problem definitions:

| Verb | Count |
|---|---|
| we **study** | 39 |
| we **consider** | 16 |
| we present / develop / focus on | 4 each |
| we examine / propose | 3 each |
| we seek to / address / introduce / design | 2 each |

**Two verbs carry 70% of the load.** "Study" and "consider" are the register. Everything else is a
long tail, and verbs that do not appear at all — *investigate, explore, delve into, shed light on,
attempt to* — are register errors that mark a draft as outside the field. Use "we study" by default;
use "we consider" when the emphasis is on the setting rather than the question.

For the problem object itself the construction is `the problem of ⟨gerund⟩`: *reassigning, matching,
managing, deciding, choosing, detecting, setting*. A gerund forces you to name the action; "the
⟨adjective⟩ ⟨noun⟩ problem" lets you hide behind a label.

---

## 5. The model section — measured build order

Across 213 optimization model/problem sections, order of first appearance:

| Step | Present | Median position |
|---|---|---|
| Verbal setting before any math | 79% | 0.03 |
| Sets and indices | **93%** | 0.06 |
| **Assumptions** | **80%** | **0.14** |
| Notation convention statement | 23% | 0.20 |
| Decision variables | 53% | 0.21 |
| Parameters | 79% | 0.22 |
| Objective | 85% | 0.31 |
| Constraint-by-constraint walkthrough | 58% | 0.40 |
| Explicit problem label | 4% | 0.56 |

**The surprise is where the assumptions are.** They arrive at 0.14 — before the decision variables
and the parameters, woven into the setup of the primitives, not collected into a block after the
formulation. Median count: **2** explicit "we assume" sentences (IQR 1–5). This matches the
across-corpus finding that the median paper has *zero* numbered `Assumption k` blocks
(`journal-benchmarks.md`).

So the published sequence is:

```
prose description of the system
  → sets and indices, with assumptions stated as each primitive is introduced
  → notation conventions (if any)
  → parameters and decision variables
  → objective
  → the formulation block
  → constraint-by-constraint walkthrough in prose
```

Real openings, all four legitimate patterns:

> *"We consider a multistore assortment planning problem where a single seller operates m stores and
> sells n substitute products to infinitesimal customers. The market size is normalized to one, and
> we assume that a fraction λᵢ of customers visit store i…"* — setting, normalization and assumption
> in two sentences.

> *"Consider an electric vehicle whose state at any time t is characterized by the amount of energy
> y(t) stored in its battery and the instantaneous power consumption for driving d(t). We require
> that y(t) is never smaller than y̲ and never larger than ȳ. To mitigate battery degradation, we set
> these limits to 20% and 80% of the nominal battery capacity…"* — primitive, constraint,
> *and the practical reason for the constraint*, in three sentences.

> *"In this section, we introduce the model that we study for the dynamic project expediting problem.
> To this end, we first provide a high-level description of the problem and introduce a network
> structure… We then formalize the problem as a Markov decision process, describing its states,
> controls, probabilities, and costs."* — a roadmap opening (19% of sections open "In this section…").

> *"We first consider a base model where the only decision that needs to be considered is product
> framing under inventory constraints. The base model will be used in addressing the joint framing
> and fulfillment problem in Section 5. We will use [N] to denote the set {1,…,N}… Unless otherwise
> noted, all vectors are to be treated as column vectors."* — base model announced as a stepping
> stone, then notation conventions.

---

## 6. Assumption prose

Four moves, all from optimization papers in the corpus. Use the one that matches what the
assumption actually is.

**Precedent** — for conventional modeling choices:
> "We assume that at most one customer arrives in each period and each customer purchases at most one
> product. This is a standard assumption in the literature (see Jasin 2014)."

**Practice** — the strongest, and under-used:
> "We assume that the ad agency's bid b for a viewer is placed on an ad exchange with a first-price
> auction, which is common in many ad exchanges today."

**Scope, with a forward pointer** — state the restriction and say where it is lifted:
> "We assume that Dₜ are independent nonnegative random variables with finite support D (in Section 6,
> we show our results hold if the demands are correlated and follow a Markov-modulated process)."

**Honest limitation** — when you are not going to relax it, say so:
> "We assume that all nodes in eⱼ contribute equally to this threshold, though, in practice,
> contributions may be unequal. We can extend our model to this setting, but the notation and
> analysis become more complex, so we leave this to future research."

**Normalization** is its own move and needs only a clause:
> "Without loss of generality, we fix the utility of the outside option to zero."
> "The market size is normalized to one."

Two rules. The parenthetical forward pointer (third move) is the highest-value sentence in this
whole section: it converts a vulnerability into evidence of thoroughness at the cost of eight words.
And a *stationarity* or *independence* assumption in an optimization paper is almost always
substantive — it is buying you a tractable expectation — so it gets the third or fourth move, never
the first.

---

## 7. Naming the formulation

Only 4% of sections explicitly label the problem, and that is a missed opportunity: a named
formulation is what lets sections 4, 5 and 6 refer back without restating. The convention is a
parenthesized acronym introduced immediately before the display:

> "Therefore, the company solves the following cardinality-constrained set function minimization
> problem: **(CP)**: min_{S⊆N, |S|≤K} f(S), where |S| refers to the number of products in S."

Then every later reference is "(CP)", "the relaxation of (CP)", "(CP) with the capacity constraint
removed". Corpus tags in use: (P), (DP), (RO), (CP), (MDP), (MIP). Keep them short, keep them
distinct, and define each once.

Give a name to: the main formulation, each variant you compare against (nominal, robust, benchmark),
and each relaxation. If a variant is never referred to again, it did not need a name — or it did not
need to exist.

---

## 8. The narrative spine

An optimization paper is a chain in which **each section's first sentence collects the previous
section's deliverable**:

```
Problem definition  → gives the reader a decision and an objective
Formulation         → turns it into an object;  ends by naming the OBSTACLE
Obstacle sentence   → "…is NP-hard", "the state space grows exponentially",
                       "the number of scenarios is exponential in T"
Solution section    → opens by answering the obstacle: which structural property
                       is exploited, and why that beats the obvious approach
Guarantee           → what the structure buys: a bound, a ratio, a regret rate,
                       a policy form
Experiments         → opens with a purpose clause tied to what the guarantee does
                       NOT cover (finite instances, real data, the practitioner's
                       benchmark)
Conclusion          → the decision maker, and what changes
```

The single most common break in this chain is a solution section that opens with the algorithm
instead of with the obstacle. If §4 begins "We now present a branch-and-price algorithm", the reader
has to reconstruct why. If it begins "The exponential number of columns in (CP) makes direct
solution impossible; however, the pricing subproblem decomposes by vehicle, which we exploit as
follows", the paper has an argument.

---

## 9. Template and checklist

**Problem definition, to fill in (~64 words):**

```
⟨Setting sentence: the decider and the decision, world-first or paper-first⟩
⟨One clause naming what makes it non-trivial: the uncertainty, the coupling,
 the scarcity, or the twist⟩
We study the problem of ⟨gerund⟩ ⟨object⟩ ⟨scope qualifier⟩,
  to ⟨objective, in the decision maker's units⟩.
```

```
[ ] 44–94 words, 2–4 sentences
[ ] The decision is named in the first sentence
[ ] The objective is the last thing, not the first
[ ] No method named (16% do; you probably should not)
[ ] Slot 2 names the one thing that makes this not a textbook problem
[ ] Verb is "study" or "consider"
[ ] The problem object is a gerund, not a label
[ ] Model section: prose setting → sets → assumptions woven in → parameters and
    variables → objective → formulation → constraint walkthrough
[ ] 1–5 "we assume" sentences, each on the right move (precedent / practice /
    scope-with-pointer / honest limitation)
[ ] At least one assumption carries a forward pointer to where it is relaxed
[ ] The formulation has a short tag, and every variant that recurs has one too
[ ] The formulation section ends by naming the obstacle
[ ] The solution section opens on the obstacle, not on the algorithm
```
