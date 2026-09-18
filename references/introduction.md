# Framing: Abstract, Introduction, and Conclusion

The abstract, introduction, and conclusion are written as one coherent unit — they bookend the paper
and **must agree with each other and with the body**. In the corpus, the conclusion mirrors the
abstract's contribution list, and the abstract is essentially a compressed version of the
introduction's arc. Draft them so a reader could read only these three and come away with an
accurate picture of what the paper proves and why it matters. This file covers all three because
getting them to correspond is the whole point.

Read this together with `citations-and-coherence.md` (the contribution↔section mapping lives there)
and `journal-profiles.md` (MS wants the managerial "so what" foregrounded; OR tolerates a
result-first, more technical framing). `journal-benchmarks.md` carries the measured length and
structure budgets; `phrase-bank.md` carries the sentence-level frames for each move below, with
how often each actually appears in print.

---

## Measured budget (OR / MS / M&SOM, 2,322 papers)

| | **OR** | **MS** | **M&SOM** |
|---|---|---|---|
| Abstract words | 185 | 211 | 285 (structured) |
| Introduction words | ~2,000 | ~1,630 | ~1,510 |
| Introduction paragraphs | 7 | 5 | 5 |
| First-paragraph words | 157 | 158 | **127** |
| Numbered `1.x` subsections | **2** | 0 | 0 |
| Conclusion words | ~1,290 | ~1,360 | ~1,310 |

**The introduction is ~10–11% of the paper in all three journals.** A 16,000-word MS paper gets a
1,600–1,800-word introduction. Longer than that usually means the paper has not yet decided what
its contribution is.

**MS and M&SOM introductions are continuous prose.** The median number of `1.x` subsections in
both is zero. Do not add `1.1 Motivation / 1.2 Contributions / 1.3 Organization` to an MS or
M&SOM draft by default — the majority of published papers do not have them. OR is the exception
and is genuinely structured (median 2, typically `Literature Review` and `Contributions`).

---

## The Abstract

**One paragraph, present tense, fixed arc:** *context / phenomenon → gap → "In this paper, we
[show / prove / propose / study] …" → main result(s) → (illustration or implication).* Every corpus
paper follows this. Do not use a bulleted or multi-paragraph abstract unless the journal uses
structured abstracts (see below).

**How much to quantify depends on the paper type.** Structural-theory papers state results
*qualitatively* — they describe the *shape* of the answer in words rather than giving numbers:

> "We show that the optimal policy for this problem has a quite simple form. Namely, it consists of
> identifying an ordered family of 'efficient' subsets S₁…Sₘ, and at each point in time opening one
> of these sets Sₖ …" — *Talluri & van Ryzin 2004, Mgmt Sci*

> "We show that the base-stock level is first increasing and then decreasing in the current purchase
> price." — *Berling & Martínez-de-Albéniz 2011, Oper Res*

Algorithmic / empirical papers, by contrast, **put numbers or complexity classes in the abstract**:

> "We prove the problem is APX-hard while its special cases … are NP-hard. … Our results suggest …
> a positive and significant improvement in the platform's profit (at the 10% significance level)."
> — *Lagzi et al. (meal delivery)*

> "The algorithm achieves O(m√n) expected regret under the stochastic input model …" — *Li, Sun &
> Ye 2023, Math Prog*

**Name your central concept in the abstract and reuse it as a brand** throughout the paper —
"deepest cuts," "bid-price control," "efficient sets," "single-unit decomposition," "Independent
Randomized Rounding." A named object gives the reader a handle and signals a contribution.

**Structured abstracts.** *Transportation Science* / M&SOM and some INFORMS journals use bold
labels — **Problem definition / Methodology and results / Managerial implications**. When the target
journal uses these (check `journal-profiles.md`), adopt them, and make the *Implications* sentence
genuinely managerial.

For M&SOM this is not optional: measured across 778 papers, `Managerial implications:` appears in
**82%**, `Problem definition:` in 46%. Both the four-part form and the compressed three-part form
(`Problem definition / Methodology-results / Managerial implications`) are current. Conversely, OR
and MS abstracts are **unstructured single paragraphs** (185 and 211 words) — importing M&SOM
labels into them is a visible mis-targeting signal.

> "**Implications:** … the proposed partially flexible delivery system demonstrates significant
> potential to improve operational efficiencies while reducing the … hassle of operating a fully
> flexible system." — *Value of Dispatching Flexibility (Transportation Science format)*

Some *Management Science* / Operations Research papers signpost the abstract with discipline-lens
adverbs instead — "Statistically, … Operationally, … Computationally, …" — to telegraph
multi-faceted contributions.

---

## The Introduction

### Opening move — earn the reader's attention in the first two sentences

Two openings dominate, chosen by paper type:

**(a) Practical / industry hook** — used by application and most MS papers. Open with a real-world
problem, often with named firms, market statistics, or a concrete operational decision:

> "Modern airlines must decide thousands of times per day whether or not to accept discount seat
> booking requests or refuse them in the hope of later, higher-fare bookings." — *van Ryzin & McGill
> 2000, Mgmt Sci*

> "The catering services market is projected to reach over $103 billion globally by 2027 …" —
> *Lagzi et al.*

> "Consider, for example, a chemicals manufacturer such as BASF; its cost structure is completely
> dependent on the price of crude oil …, in the $30 per barrel range in 2003, up to over $130 … in
> 2008, and back to $50 in 2009." — *Berling & Martínez-de-Albéniz 2011*

**(b) Field-trend / methodological motivation** — used by theory and methodology papers. Open with
the state of a research area or the pedigree of a method, then narrow to the open problem:

> "Online optimization is attracting increasingly wide attention in the computer science, operations
> research, and management science communities. … For example, in online revenue management
> problems, consumers arrive sequentially …" — *Agrawal, Wang & Ye 2014, Oper Res*

> "Since Benders (1962) originally proposed a procedure …, Benders Decomposition has increasingly
> attracted the attention of researchers in the last five decades." — *Hosseini & Turner*

Application papers frequently strengthen the hook with **a data observation or a real failure**: a
figure of empirical evidence that motivates the research question (e.g. plotting platform data and
noting "28.2% of couriers exclusively delivered orders within a single zone … the late delivery
ratio for couriers serving a single zone is the lowest"), or a cited disaster ("the bankruptcy of
the waste recycling company, IUT-Global"). Motivation in this genre is empirical, not merely
conceptual.

### The hinge: from background to contribution

After the hook, pivot to the gap with a **concessive signal**, then claim the contribution with **"In
this paper, we …"**. This two-beat is nearly universal:

> "Yet the theory underlying bid-price controls is scant." → "In this paper, we propose a general
> model … and analyze it via dynamic programming." — *Talluri & van Ryzin 1998*

> "Yet most revenue management methodologies ignore this phenomenon—or at best approximate it in a
> heuristic way." → "In this paper, we provide an exact and quite general analysis of this problem."
> — *Talluri & van Ryzin 2004*

The gap is most often framed as **theory lagging practice** (a method is used but not understood; a
phenomenon matters but is ignored) or as an **explicit list of reasons / open questions**:

> "However, the problem … is uniquely complex for two reasons. First, the decision space is
> exponential … Second, the platform must simultaneously account for firm preferences, delivery
> costs, restaurant capacities, and menu rotation …" — *Lagzi et al.*

> "two major open questions were: (i) Does the set of LP optimal dual prices … converge …, and (ii)
> Could the results be extended to general LP problems …" — *Li & Ye 2021*

A graceful move when others have noticed the same gap: **concede it before claiming your fix.**
"We lay no claim to uncovering this deficiency. Indeed, many researchers have tried to address …" —
this disarms the reviewer and sharpens what is actually new.

### Stating contributions

**Prose is the majority format.** Only **13% (OR, MS) to 17% (M&SOM)** of published papers use an
explicitly enumerated contribution list. Enumerate when the contributions are genuinely separable
(a formulation, a theorem, an algorithm, an experiment); use prose when there is one idea with
consequences. Do not reach for a numbered list by reflex.

When you do enumerate, the items should **descend a ladder** — object introduced → theoretical
guarantee → computational or empirical evidence → managerial consequence — rather than repeat four
claims of the same kind.

Format varies with venue maturity; all are acceptable, so match the target journal and the user's
preference:

- **Prose contributions** (classic Operations Research): woven into an "In this paper, we …"
  paragraph — "we show … we also show … we also develop …". Often paired with a **question cascade**
  ("Does the profit function possess … structural properties? How can a retailer efficiently
  optimize …? … These are some of the questions we address.").
- **Numbered list** (i)–(iv), each item ending in a sharp claim, often **"To the best of our
  knowledge, we are the first to …"**. Measured: the priority phrase appears in only 2–4% of
  papers, and always with qualifiers that bound it. Write "the first to derive *closed-form*
  optimal mechanisms *under distributional ambiguity*", never "the first to study X" — an
  unbounded priority claim is the easiest thing in a paper for a referee to break.
- **Bulleted list**, one bullet per contribution paragraph, each ending in a "first to" or a
  quantified claim ("can yield more than 4% improvement in profit for practical-size networks").
- **Bold run-in headers**: a short subsection (e.g. "1.1 Key Results and Main Contributions") with
  each contribution introduced by a **bold lead-in phrase** ("**Dual convergence of online linear
  programs.** We establish …").

Whatever the format: every contribution must be something a later section actually delivers (the
coherence pass checks this), and theory papers often **preview the main result as a numbered theorem
right in the introduction**, immediately followed by a pointer to where it is proved ("We prove
Theorem 1 in §3") and a one-line plain-language restatement ("An alternative way to state Theorem 1
is that our algorithm has a competitive ratio of 1 − O(√(m log n)/B)").

### Roadmap — optional, and a minority practice

"The remainder of this paper is organized as follows" appears in only **21% (MS) to 27% (OR)** of
published papers. Roughly three quarters omit it. Treat it as a device, not a required closing
move: include it when the structure is genuinely non-obvious (analysis split across two asymptotic
regimes; theory and experiments interleaved), and otherwise give those words to the contribution.

When you do include one, keep the classic form — "Section 2 reviews … Section 3 introduces …
Section 6 concludes." In methodology-heavy papers the roadmap can double as the contribution list
(each section pointer states what is proved there). Many corpus papers fold notation conventions
into this same paragraph ("All proofs are relegated to the appendix. We use boldface lowercase
letters for vectors …").

**Length:** median introductions run 5 paragraphs in MS and M&SOM, 7 in OR — shorter than the
6–12 that reads as natural when drafting. Application papers run longer (they spend more on the
hook and the data motivation); terse theory papers can be shorter. The hinge and the contributions
are non-negotiable; the roadmap is not.

---

## The Conclusion

The conclusion is a **stable template**: recap contributions (mirroring the abstract) → a
practitioner-facing verdict → limitations → an enumerated menu of future work, often closing on a
broadening move.

**Measured** — share of conclusions containing each element (OR n=70, MS n=953, M&SOM n=607):

| | **OR** | **MS** | **M&SOM** |
|---|---|---|---|
| Future work | 49% | 62% | **64%** |
| States limitations | 26% | **56%** | 49% |
| Practitioner-facing verdict | 21% | **55%** | **60%** |
| Carries a number (%, $) | 23% | **51%** | 45% |
| Enumerated menu ("First… Second…") | 13% | 24% | 25% |
| Opens with a recap ("We study / we proposed…") | 30% | 19% | 23% |

Read this as a journal signal: in MS and M&SOM a conclusion without a practitioner verdict
(~57%) or without a quantified claim (~48%) is below the norm; in OR neither is expected, and
the section is mostly recap plus future work. Note also that only about a fifth of conclusions
*open* with the recap — most open on the phenomenon or the verdict and place the recap second.

- **Recap + practitioner verdict.** Restate what was shown, then turn explicitly to the practical
  audience: "This result should be reassuring to the many users in the airline, hotel and
  broadcasting industries." Be honest in the verdict — when the result is mixed, say so: "our
  preliminary numerical studies indicate that the method has mixed performance—underperforming …
  when demand is not highly censored but outperforming … when demand is heavily censored."
- **Limitations.** State them plainly. Application papers in the corpus frequently raise
  **fairness/equity** as a limitation ("spatial unbiasedness may not always lead to fair outcomes";
  "partial flexibility … may introduce fairness concerns among couriers").
- **Future work as an enumerated menu**, each item introduced "First / Second / Third …" — often the
  relaxations of assumptions made in the model, listed in the same order they were introduced.
  `for future research` appears in 10% (OR), 19% (MS), 23% (M&SOM) of papers. **Every future-work
  sentence must name the assumption being relaxed**, and ideally why it is hard: "this would
  require different methods in analyzing the regret, especially the loss of nonstationarity."
  "This is a promising direction for future research" occurs in the corpus and carries no
  information — do not write it.
- Theory papers sometimes organize the conclusion **by perspective** ("From a theoretical
  perspective … From a practical perspective …") and end on a crisp one-line takeaway.

The conclusion should not introduce new results, and it should not contradict the hedging used in the
body — if the experiments section called a result "suggestive," the conclusion cannot call it
"demonstrated."

---

## Self-check before handing back

- Abstract arc present (context → gap → "in this paper we…" → result → implication)?
- Does the abstract's claimed result match what the body actually proves, at the right confidence
  level (qualitative for theory, quantified for empirical)?
- Does every contribution in the intro have a home in a later section? (→ `citations-and-coherence.md`)
- Does the conclusion's recap match the abstract's contributions, and does it add limitations +
  future work without overclaiming?
- Is the central concept named and reused consistently across all three?
