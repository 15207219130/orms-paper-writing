# Numerical Experiments / Computational Study / Case Study

The experiments section answers the questions the introduction raised, using evidence. The corpus
papers share a tight logic — **purpose / research questions → setup (instances, parameters,
benchmarks, with provenance and reproducibility) → results, each introduced and interpreted →
takeaways tied back to theory and to managerial meaning** — and a conspicuous *epistemic honesty*
that is, by reviewer standards, non-negotiable. A results section that dumps tables without
interpretation, or that overclaims what the experiments establish, is a classic referee target.

## Lead with purpose / research questions

Open by stating *why these experiments exist* — what questions they answer — before any setup. Two
common forms:

**Stated objectives:**

> "There are several reasons to engage in numerical analysis. The first … is to understand the
> performance of the proposed optimization algorithm. However, the sample path gradient algorithm …
> is perhaps best viewed as a tool to help assess the impact of substitution behavior …" — *Mahajan
> & van Ryzin*

> "In this section, we provide a numerical study with two main objectives. First, we investigate how
> the different model parameters influence the threshold prices … Second, we compare the performance
> of the optimal inventory policy against … policies where price fluctuations are not fully
> considered." — *Berling & Martínez-de-Albéniz*

**Research-question subheadings**, sometimes phrased as actual questions — a vivid, reader-friendly
device that several corpus papers use:

> "**Algorithm Performance Evaluation: How Much Efficiency Improvement Can We Gain?**" — *Zhang et
> al.*

A four-part experiment plan can be previewed as a numbered list ("Our experiments consist of four
parts: (i) … (ii) … (iii) … (iv) …"), which doubles as a roadmap.

## Describe the setup with provenance and reproducibility

State the instances, parameters, and benchmarks precisely, and **where they come from**:

- **Instances / data:** name real datasets and their source (Citi Bike + NYC Open Data + NCDC
  weather; Meituan delivery data with exact dates and city; the CAB dataset "originated from O'Kelly
  (1987)"). For synthetic instances, give the generating distributions, ideally in a small table.
- **Benchmarks / baselines:** introduce them as a labeled list with a rationale for each, and design
  them to be **fair**: "We next propose two policies that are meant to mimic the types of heuristic
  decision rules used in practice."
- **Reproducibility, stated up front:** solver and version, hardware, and code availability —
  "All optimization problems are solved with Gurobi 10.0.1 on an Intel Core 3.60 GHz processor with
  64 GB memory. The data and source code … can be found in the electronic companion."
- **Aggregation method**, when non-obvious: "We used shifted geometric mean (SGM) for aggregating the
  performance results, where … s = 1 for gaps and ratios, and s = 10 for times …".

## Frame what the experiments can and cannot establish

This honesty is a hallmark of the corpus and protects the paper from reviewers. State the epistemic
status of the study, and design benchmarks fairly rather than as straw men:

> "The examples are constructed primarily to illustrate the behavior of the bid prices … rather than
> to mimic real data." — *Talluri & van Ryzin 1998*

> "These comparisons are based on simulated data in an idealized stationary setting. While the
> examples are useful for illustrating … operating characteristics …, they cannot lead to final
> conclusions about relative merits. Such conclusions can only come from trials in practice." — *van
> Ryzin & McGill*

> "Again, we emphasize that this overall forecasting-EMSR scheme is not constructed to be the most
> sophisticated one possible. Rather, it is intended to be representative of a basic yield management
> system." — *van Ryzin & McGill* (fair-benchmark framing)

For empirical/causal studies, be explicit about identification limits: "given the non-random
geographic assignment, the single treated market, and treatment-control imbalance, we need to
interpret the results as suggestive rather than definitive causal evidence."

## Introduce and interpret every table and figure — never leave them to the reader

The rhythm is **locate → read → interpret**: a sentence pointing the reader to the exhibit, the key
number(s), then what it means.

> "Figure 1 shows the bid prices produced by each approximation method for Example 1. … Note that all
> three approximation methods underestimate the optimal bid price when the remaining capacity is less
> than the mean total demand of 6." — *Talluri & van Ryzin 1998*

> "Note that the DCOMP heuristic produces consistent revenue gains over the CDLP policy, especially
> in the tightly constrained … cases. The gains … are on the order of 1%–5%, which is quite
> significant." — *Liu & van Ryzin*

"Note that …" and "performs badly … because …" are the workhorse connectives — each exhibit gets a
takeaway, and a *mechanism* when behavior is surprising. Quantify takeaways ("reduces … by 8.5% and
26.4%", "achieving 99.6% … of the profits"), and contextualize the magnitude against field norms
("a 12% improvement … very large when compared to the typical 1%–2% differences … when comparing
optimization methods").

Because the body text carries this locate→read→interpret work, **keep the caption itself short.** A
caption names the exhibit and the minimum key to read it (columns/axes, instance, units); it is not
the place for the analysis, the takeaway, the mechanism, or a full worked example. A caption that has
swollen into a paragraph of argument is a symptom that the interpretation landed in the wrong place —
move it into the text and leave a one- or two-sentence caption.

## Tie results back to theory and to managerial meaning

Two backward links make the section land:

- **To the theory:** attribute observed behavior to a specific proved term or result — "This aligns
  with the analysis in Proposition 2"; "consistent with the O(m) term in the regret bound"; "the
  advantage … can be explained by the fact that the dual convergence rate is of order √(m/n)";
  "confirms our theoretical insights based on Propositions 4 and 5." This is the explicit
  theory↔experiment bridge reviewers look for.
- **To management/practice:** end with guidance, often a *trade-off* or *context-dependent* lesson
  rather than a blanket winner — "system design should be context-dependent rather than
  'one-size-fits-all'"; "cautions an extra price of controlling the fluctuation in cost flow as the
  trade-off." Application papers sometimes add an explicit "Practical Guidelines" subsection turning
  findings into an action sequence.

## Report negative and anomalous results honestly

Do not bury cases where the method loses — explain them. The corpus treats this as a strength:

> "As noted, our DCOMP approach does worse than the CDLP method in some extreme cases … This is due
> to the existence of multiple dual solutions to the CDLP." — *Liu & van Ryzin* (a whole subsection
> devoted to the negative cases)

> "The third experiment … presents a negative result on all three algorithms. … The phenomenon is
> consistent with the previous analysis that the algorithm regret is positively affected by the upper
> bound … The empirical finding suggests that a light-tail distribution is probably necessary." —
> *Li, Sun & Ye*

Include **robustness checks and sensitivity analyses** (alternative instruments, parameter sweeps)
where the result's credibility depends on them.

## Per-journal notes

- **Management Science:** the managerial insight is the payoff — foreground "what should a manager do
  differently," quantified, with the trade-off named. Behavioral/mechanism explanations of *why* the
  policy wins are valued.
- **Operations Research / Mathematical Programming:** computational rigor — instance breadth, fair
  benchmarks, runtime/scaling tables, performance profiles, and tight links back to the proved
  bounds. (Some purely structural OR papers have only small illustrative examples, or defer
  experiments entirely; match the paper's nature.)
- **Transportation Science / M&SOM / application papers:** a real case study with named data is
  expected; reproducibility and data provenance are scrutinized; managerial guidelines are welcome.

## Self-check

- Does the section open with its purpose / research questions?
- Are instances, parameters, and benchmarks given with provenance, and is reproducibility (solver,
  hardware, code) stated?
- Is the epistemic status framed honestly, and are benchmarks fair rather than straw men?
- Does every table/figure get a locate→read→interpret treatment with a quantified takeaway?
- Is each caption short (exhibit + reading key), with the analysis and any worked example in the body
  rather than packed into the caption?
- Is each main result tied back to a specific theoretical result *and* to a managerial implication?
- Are negative/anomalous results explained rather than hidden, with robustness checks where needed?
- Do the experiments actually answer the questions the introduction raised? (→ `citations-and-coherence.md`)
