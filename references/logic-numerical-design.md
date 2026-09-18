# The Logic of Numerical Experiment Design

`numerical-experiments.md` covers how to report experiments. This file covers how to **design**
them — which experiments a paper needs, in what order, and what each one is for.

Method: sentence-level tagging of numerical / computational / case-study sections in the corpus
(OR n=45, MS n=531, M&SOM n=265, sections of ≥25 sentences). Keyword-based; read the shape as
the finding.

---

## 1. What the experiments are for

Not "to validate the model." An experiment section answers questions the analysis could not,
and there are only four reasons a published experiment exists:

1. **Existence** — the method runs on instances of realistic size. (Optimization papers.)
2. **Advantage** — it beats what a practitioner would otherwise do, by a stated margin.
3. **Boundary** — the regime where the advantage appears, and the regime where it disappears.
4. **Magnitude** — the size of the effect in the units a decision maker cares about.

Reasons 3 and 4 are where managerial insight comes from, and they are the ones most drafts skip.
An experiment that only establishes 1 and 2 is a benchmark table, and reviewers read it as one.

---

## 2. What is actually in a published experiments section

Share of papers whose experiments section contains each element at all:

| Element | **OR** | **MS** | **M&SOM** |
|---|---|---|---|
| RESULT — a number, table or figure read out | 100% | 98% | 100% |
| SETUP — instances, parameters, data, solver | 98% | 89% | 97% |
| **MECHANISM — why the numbers come out that way** | 84% | 84% | **90%** |
| BENCHMARK — comparison against alternatives | 84% | 82% | 89% |
| PURPOSE — an explicit statement of what the section is for | 87% | 73% | 83% |
| **LIMIT — a case where the method loses, or a caveat** | **24%** | **27%** | **28%** |
| MANAGERIAL — addressed to managers/practitioners | 11% | 19% | **26%** |

Two things stand out.

**Mechanism is near-universal (84–90%).** Explaining *why* is not an optional flourish; it is
what nearly every published experiments section does. A results section that reports numbers
without attributing them to a cause is outside the norm.

**Honest limits are rare (24–28%) — and that is the cheapest available differentiator.** Three
quarters of published papers never show a case where their method loses. A paper that does,
and explains it, buys credibility that referees respond to directly, because the alternative
reading of a clean sweep is that the benchmarks were weak.

---

## 3. The density profile

Share of sentences carrying each move, by fifth of the section:

**M&SOM**

| fifth | 0–20 | 20–40 | 40–60 | 60–80 | 80–100 |
|---|---|---|---|---|---|
| PURPOSE | 4% | 2% | 1% | 1% | 1% |
| SETUP | **12%** | 11% | 7% | 7% | 6% |
| BENCHMARK | 4% | 4% | 5% | 5% | 6% |
| RESULT | 10% | 17% | 21% | 21% | **23%** |
| MECHANISM | 3% | 3% | 4% | 4% | 4% |

MS is the same shape with a lower SETUP level (8%→6%) and RESULT rising 10%→19%.

**OR is different**: SETUP stays high throughout (23% → 18%) while RESULT rises only 6% → 13%.
OR sections interleave — new test bed, new results, new test bed — because the argument is
about performance across instance families. MS and M&SOM front-load the setup once and then
spend the section reading out results.

**The opening move:**

| Opens with… | OR | MS | M&SOM |
|---|---|---|---|
| PURPOSE | **58%** | 39% | 47% |
| SETUP | 20% | 20% | 18% |
| RESULT | 13% | 23% | 18% |
| BENCHMARK | 7% | 9% | 9% |

And how the purpose is phrased: "In this section, we…" opens 55% (OR) / 43% (M&SOM) / 33% (MS)
of sections, but a real **purpose clause** ("to evaluate / to quantify / to understand …")
appears in the first 700 characters of only **17% (OR) / 20% (MS) / 24% (M&SOM)**. Most
sections announce that they exist without saying what they are for. Writing the purpose clause
puts a draft in the top quarter at no cost.

Only **14% (MS, M&SOM)** and **0% (OR)** enumerate their experiments ("our experiments consist
of four parts"). Worth doing when there are three or more distinct studies — it doubles as a
roadmap for the section.

---

## 4. The experiment ladder

The sequence that published sections converge on, and what each rung is for:

```
0. PURPOSE      One sentence naming what the experiments must establish.
                Best form: a question. "How much of the gain survives when demand is
                correlated across stations?"

1. DESIGN       Instances or data, with provenance. Parameter ranges and where they
                come from. What is held fixed. For MS/M&SOM: why the parameters are
                credible (calibration source). For OR: why this test bed is standard,
                or why a new one was needed.

2. BENCHMARKS   Named alternatives, including the policy a practitioner uses today.
                A comparison only against your own ablations is weak.

3. HEADLINE     The main result, quantified against the benchmark that matters.

4. BOUNDARY     Where the advantage grows, shrinks, and vanishes. This is the
                comparative-statics experiment, and it is the one that generates
                managerial insight. Run every parameter; look for a sign flip or a
                non-monotonicity — in M&SOM that is the paper's headline (see
                journal-profiles.md).

5. MECHANISM    Why. Tie to a specific proposition, a structural property, or a named
                economic force. 84–90% of published sections do this.

6. STRESS       The case where it loses, or the assumption whose violation matters.
                Only 24–28% of papers include this; include it.

7. MAGNITUDE    Translate into the decision maker's units — dollars, %, service level,
                hours. M&SOM: 26% of sections address practitioners directly; this is
                where that happens.
```

Rungs 0, 4, 6 and 7 are the ones drafts omit, and they are exactly the four that separate a
results section from a benchmark table.

**Real purpose statements from the corpus**, showing the range:

> "Our computational experiments have two goals: (i) to examine the computational efficacy of
> the branch-cut-and-price approach and (ii) to evaluate the benefit and provide managerial
> insights for the driver-aide problem." — *M&SOM 2024*

> "In order to quantify the impacts of transaction errors, we compute the optimal restocking
> policy for three separate cases." — *M&SOM 2025*

> "We conduct four sets of numerical studies: a pilot study to assess the performance of the
> optimization-inspired benchmark, a large instance study covering a wide range of parameter
> values, and two focused studies covering specific testing settings." — *M&SOM 2025*

Each names the *purpose*, not the activity, and the third enumerates the ladder explicitly.

---

## 5. Choosing parameters, credibly

The parameter choice is where most experiment sections quietly lose the referee. Three
defensible sources, in descending order of strength:

1. **Calibration to a real system** — a partner's data, a public data set, published industry
   figures. State the source and the mapping ("we calibrate our model using real-life data
   from Massachusetts"). Industry-partner data appears in 7% of M&SOM papers and is the
   strongest available warrant.
2. **Values used in prior work on the same problem**, cited. Weak on its own but it makes the
   results comparable, which is worth something.
3. **A range, swept.** If a parameter cannot be pinned down, do not pick a value — sweep it and
   report how the conclusion varies. A conclusion that holds across the sweep is stronger than
   one computed at a defensible point estimate.

What does not work: a table of round numbers with no provenance. Reviewers read unsourced
parameters as tuned, and once that suspicion is live every result in the section is discounted.

---

## 6. Worked contrast

Negative constructed; positive rebuilt on the same material.

### ✗ The benchmark table

> **6. Numerical Experiments**
> In this section, we present numerical experiments. We set a = 100, b = 2, k = 5, θ = 0.3,
> and c = 10. Figure 5 shows the equilibrium investment levels under the three contracts.
> Table 3 reports profits. As can be seen, the risk-sharing contract achieves the highest
> profit in all cases. Figure 6 shows the effect of θ. Figure 7 shows the effect of k. The
> results demonstrate the effectiveness of the proposed contract.

Diagnosis: no purpose clause (norm: the top quarter has one); parameters with no provenance;
"the three contracts" are the paper's own variants, so there is no practitioner benchmark;
"as can be seen" leaves the reading to the reader; the θ and k figures are presented as
existence rather than as boundary-finding — nothing is said about *where* the advantage
changes; no mechanism (84–90% of published sections have one); no case where the contract
loses (the 24–28% move); and no magnitude in decision units. Six figures, one claim.

### ✓ The same experiments, designed

> **6. Numerical Experiments**
> **[PURPOSE]** The analysis in Section 4 establishes that the risk-sharing contract can
> stabilize joint investment, but leaves two questions open: how much of the gain survives
> when the two parties' disruption exposures differ, and whether the contract is still worth
> offering when the supplier's bargaining weight is high. This section answers both, and
> quantifies the gain in emissions and expected disruption cost.
>
> **[DESIGN]** We calibrate the demand and cost parameters to the 2019–2023 panel of
> [source]; disruption frequencies come from [source]. Table 2 reports the ranges and their
> provenance. Parameters we cannot pin down — the comparison-sensitivity θ — are swept over
> [0, 1] rather than fixed.
>
> **[BENCHMARKS]** We compare against three alternatives: the centralized first-best
> (Section 4.1), a fixed cost-sharing contract with no risk sharing, and the wholesale-price
> contract that describes current practice in the industry.
>
> **[HEADLINE]** Relative to the wholesale-price contract used today, the risk-sharing
> contract raises expected chain profit by 8.4% and cuts expected disruption loss by 19%,
> recovering 71% of the centralized first-best.
>
> **[BOUNDARY]** The advantage is not monotone in θ. It peaks at θ ≈ 0.35 and *reverses* for
> θ > 0.62, where the contract lowers chain profit relative to a plain wholesale-price
> contract — Figure 6.
>
> **[MECHANISM]** This is the numerical counterpart of Proposition 5: a higher θ raises the
> manufacturer's marginal return to investment, which the supplier anticipates and extracts
> through the wholesale price. Beyond θ̂, the extraction dominates the coordination gain.
>
> **[STRESS]** The reversal is robust to the functional forms (Appendix D) but disappears if
> investment is unobservable, the case we study in Section 6.2 — so the result depends on
> disclosure, not on risk sharing alone.
>
> **[MAGNITUDE]** For a chain of the size in our calibration, the 8.4% corresponds to roughly
> $X million annually, and the reversal region covers the comparison sensitivities observed in
> [source] — so the contract should not be offered indiscriminately.

Same figures, same model. The difference is that every exhibit now answers a stated question,
the boundary is hunted rather than illustrated, the mechanism ties back to a proposition, and
the paper names the condition under which its own recommendation is wrong.

---

## 7. Diagnostic questions

- Does the section open with a purpose clause — what the experiments must establish, ideally
  as a question?
- Can every parameter's value be traced to a source, prior work, or a sweep?
- Is one of the benchmarks the policy a practitioner uses today?
- Has the comparative-statics sweep been run looking for a *sign flip*, not just a trend?
- Is there a mechanism paragraph tying the numbers to a specific proposition or force?
- Is there a case where the method loses, and is it explained? (Only ~25% of papers have one.)
- Is the headline translated into the decision maker's units?
- Does every figure and table answer a question the section stated it would answer? If not, it
  belongs in the e-companion — the main-text budget is ~5 figures and ~4 tables.
