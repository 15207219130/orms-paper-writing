# Journal Profiles: MS vs OR vs Transportation Science vs M&SOM

The core writing conventions in the other reference files are shared across these journals — they are
all INFORMS-family, author-date, "we"-active, prose-heavy venues. But the *framing* differs, and
matching the target journal's ethos is part of writing well. This file is a quick orientation; the
section references carry per-journal notes inline. When the user names a target, read its profile
here and let it shape emphasis (especially in the abstract, introduction, and the managerial framing
of the experiments). When they don't name one, ask, or default to a neutral "top OR/MS" framing and
say so.

The single most useful question to keep asking: **what does this journal's reader want to take away?**

For the *numbers* behind the OR / MS / M&SOM profiles below — lengths, section architecture,
word budgets, abstract formats — see `journal-benchmarks.md`. Those figures come from full-text
analysis of 2,322 published articles (see `../CORPUS-NOTES.md`). Transportation Science and the
adjacent venues in this file were **not** measured; treat their profiles as qualitative.

---

## The discriminator, in one table

| | **Operations Research** | **Management Science** | **M&SOM** |
|---|---|---|---|
| Unit of contribution | A **method or theorem** not previously available | A **finding about a system** (market, firm, platform, behavior) | A **decision an operations manager faces** |
| Sentence the abstract must earn | "We prove / we can now solve X." | "We show that A affects B, through mechanism C." | "Managers should do X rather than Y, under conditions Z." |
| Median main text | **18.9k** words | 16.1k | **14.8k** |
| Abstract | 185 w, single paragraph | 211 w, single paragraph | 285 w, **structured** |
| Standalone literature review | **30%** | 44% | **63%** |
| Model / formulation section | 35% | 43% | **56%** |
| Data section | 5% | **23%** | 22% |
| Numbered results (median) | **6** | 5 | 5 |
| Evidence register | Gaps, CPU times, benchmark instances | Robustness checks, counterfactuals | Calibrated case study + implications |

**Blunt heuristic.** If removing the proofs destroys the paper → OR. If removing the empirical
identification destroys it → MS. If removing the managerial implication destroys it → MSOM.

Three invariants hold across all three: the introduction is ~10–11% of total words (not 20%);
the literature review is the *smallest* section at 8–9%; sections 3–5 carry 43–50% of the words.

---

## Management Science (MS)

- **Ethos:** a managerial / decision science journal. The reader wants to know *what this means for
  decisions* — the insight, not just the theorem. Even highly technical MS papers foreground a
  managerial "so what."
- **Framing:** lead the abstract and intro with the phenomenon and its decision relevance; motivate
  with real stakes (often quantified industry impact). Position against both a methods stream and an
  application/managerial stream.
- **Model:** keep the managerial meaning of variables/constraints visible; the decision being made
  should be legible.
- **Results section:** the payoff is the **managerial insight** — "managers should stock relatively
  more of popular variants and relatively less of unpopular variants than a traditional newsboy
  analysis indicates." Quantify it; name the trade-off.
- **Conclusion:** practitioner-facing verdict is expected.
- Breadth of audience is wide (operations, but also finance/marketing/info-systems readers), so avoid
  assuming the reader knows your subfield's jargon.
- **Measured:** introductions are continuous prose — median **0** numbered subsections, 5
  paragraphs, ~1,630 words. `we find that` appears in **38%** of MS papers; `contributes to
  the (literature)` in ~21%. MS wants you to name the conversation you are joining:
  contributions are phrased as claims on a literature, not as capability claims.
  Discussion section: 33% (highest of the three). Robustness checks: 11%.

## Operations Research (OR)

- **Ethos:** the flagship methodological OR journal. Technical depth, rigorous analysis, and provable
  guarantees are the contribution. The reader is an OR methodologist.
- **Framing:** a result-first, more technical framing is accepted; the gap is usually "theory lags
  practice" or a precise methodological lacuna. Literature review is frequently **folded into the
  introduction** as narrative positioning.
- **Model:** state at its natural level of generality; be explicit and disciplined about the
  assumption set and notation.
- **Solution:** the technical core is the paper. Full rigor expected, but keep the main text
  navigable (roadmaps, intuition beside theorems, proofs to the appendix/e-companion).
- **Results section:** computational rigor — instance breadth, fair benchmarks, runtime/scaling,
  performance profiles, and explicit links back to the proved bounds. Some structural OR papers carry
  only small illustrative examples, which is acceptable when the contribution is theory.
- **Conclusion:** often organized "From a theoretical perspective… From a practical perspective…".
- **Measured:** the "folded-in review" is not a stylistic option, it is the norm — **70%** of OR
  papers have no standalone literature-review section; 35% carry it as a `1.x` subsection of the
  introduction. OR introductions are the only *structured* ones of the three (median **2**
  numbered subsections, typically `1.x Literature Review` and `1.x Contributions`) and the
  longest (~2,000 words, 7 paragraphs). Contribution statements are capability claims —
  grammatical subject *the paper / the contribution*, verbs *prove, derive, characterize,
  develop a formulation*. CPU/solution time discussed in 16% of papers and optimality gaps in
  11% — roughly five times the MS/MSOM rate. Caution: the OR arm of the corpus is only 96
  papers, so its point estimates carry roughly ±10 percentage points (see `../CORPUS-NOTES.md`).

## Transportation Science (TS)

- **Ethos:** application-meets-method in transportation, logistics, and mobility. Reviewers expect
  both a credible real-world transportation problem *and* a methodological contribution.
- **Framing:** open with a transportation/industry hook, often with real data or a data observation
  that motivates the research question. Uses **structured abstracts** (Problem definition /
  Methodology and results / Implications) in some tracks.
- **Literature review:** a separate section is common; represent **both** the domain (transportation)
  literature and the OR-methods literature, each with explicit positioning.
- **Model:** anchor in the real system and justify stylizations with precedent ("the circular city
  setup is widely utilized…").
- **Results section:** a real **case study with named data** is expected; provenance and
  reproducibility are scrutinized; managerial/operational guidelines are welcome.
- **Conclusion:** managerial implications + limitations; fairness/equity is a recurring concern in
  this genre.

## Manufacturing & Service Operations Management (M&SOM)

- **Ethos:** operations management with a service/manufacturing and often empirical or
  analytical-meets-empirical flavor. Between MS (managerial) and OR (methodological), leaning toward
  operational decision insight.
- **Framing:** managerial relevance plus methodological soundness; **structured abstracts** are
  standard. Practical implementability is valued ("appears to be a viable practical method for…").
- **Model & solution:** rigorous but readable; running examples and clear intuition are appreciated.
- **Results section:** honest about what simulation/empirics establish; candid anomaly discussion is
  a positive signal (the corpus M&SOM paper devotes a subsection to explaining when its heuristic
  loses).
- **Measured — the structured abstract is effectively mandatory.** Label frequencies across 778
  M&SOM papers: `Managerial implications:` **82%**, `Results:` 48%, `Problem definition:` 46%,
  `Methodology:` 42%, `Methodology/results:` 38%, `Academic/practical relevance:` 37%. Two live
  forms coexist — the four-part (`Problem definition / Academic-practical relevance /
  Methodology / Results / Managerial implications`) and the compressed three-part
  (`Problem definition / Methodology-results / Managerial implications`), the latter more common
  recently. An M&SOM abstract without a managerial-implications block is the most visible way to
  look mis-targeted.
- **Measured — the review goes in §2.** 61% of M&SOM papers carry a standalone literature-review
  section, usually organized as two or three named streams; only 15% fold it into §1.
- **Measured — introductions are the shortest and most concrete** of the three: 5 paragraphs,
  ~1,510 words, first paragraph only **127 words**. Explicit research questions are an M&SOM
  signature (`what is the` appears in 10% of introductions, twice the MS rate).

### The managerial reversal — M&SOM's highest-value move

The move with no real counterpart in OR or MS: the paper exists because **the intuitive policy
fails**. Published examples:

> "We show that guided delegation does not always yield its expected results of lower supply chain
> risk and greater buyer profit."

> "Initially, it might be assumed that Southwest's decision to start nonstop service to some
> destinations but not to others would explain these variations. However, our findings show that
> this decision alone does not sufficiently explain the observed heterogeneity."

> "Although it may seem counterintuitive to delay the start of an available task, we identify
> situations where … it is indeed worthwhile to do so."

If a draft's punchline is "the optimal policy is monotone in cost", it is not yet an M&SOM paper.
If it is "the firm should audit *less* when auditing gets cheaper, because of the wholesale-price
response", it is. Note the discipline in all three examples: the reversal is stated **with its
scope condition**. "X is bad" over-claims; "X backfires when the wholesale price responds" is a
finding. When drafting for M&SOM, run the comparative statics across every parameter and look for
a sign flip or non-monotonicity — that is the headline.

---

## Converting a draft between journals

Reformatting the bibliography is not the work. These are the edits that matter:

**M&SOM → OR**
- Move the review out of §2; fold it into §1 or into the motivation (70% of OR papers have no standalone review).
- Add 1–2 numbered results; OR's median is 6 against M&SOM's 5, and OR is judged on what is proved.
- Replace the structured abstract with a single ~185-word paragraph; drop the labels, keep one sentence of implication in prose.
- Budget ~4,000 more words, spent on the model, proof architecture, and computational experiments.
- Rewrite contributions from "managers should" to "we prove / we can now compute".

**OR → M&SOM**
- Cut ~4,000 words; first casualties are main-text proof sketches (to the e-companion) and technical positioning.
- Promote the application: name the setting, the decision maker, and the lever inside the first ~127 words.
- Add a standalone §2 organized into named streams.
- Build the structured abstract and write `Managerial implications:` *first*. If it cannot be filled, the paper is not ready for M&SOM.
- Find the reversal.

**MS ↔ M&SOM** — the closest pair; the discriminator is *whose decision is at stake*. MS tolerates a
conclusion about how a market behaves; M&SOM wants a conclusion about what an operations manager
does on Monday. Practically: MS keeps the Discussion section and the empirical apparatus, M&SOM
keeps the Model section and the managerial-implications block.

## Signals that a submission is mis-targeted

| Symptom | Likely misfit |
|---|---|
| Structured abstract with `Problem definition:` sent to OR or MS | M&SOM habit |
| 24,000-word main text sent to M&SOM | OR habit |
| Standalone 2,500-word literature survey sent to OR | M&SOM/MS habit |
| `1.1 Motivation / 1.2 Contributions / 1.3 Organization` in an MS submission | OR habit (MS median is 0 subsections) |
| No `we find that` / `our results suggest` sentence anywhere in an MS or M&SOM paper | Under-claimed; both run ~38% |
| No managerial implication in an M&SOM paper | Desk-reject risk |
| "We are the first to model X", with no theorem and no data | Fits none of the three |

---

## Adjacent venues (brief)

- **Mathematical Programming:** the most theory-forward — the optimization contribution (bounds,
  reformulations, algorithmic guarantees) is the paper. Bracketed-numeric citations sometimes appear.
- **POMS / Production and Operations Management:** operations management, managerial framing similar
  to MS/M&SOM.
- **Operations Research Letters:** short-format; compressed versions of the same conventions.
- **Energy / interdisciplinary venues (Nature Energy, Applied Energy, etc.):** the corpus includes a
  few; their conventions differ more (shorter, broader audience, methods often in supplementary
  material). If the user targets one of these, flag that the OR/MS conventions here apply only
  loosely and lean on `scientific-writing` for the general structure.

## How to use this in practice

1. If the user named a journal, read its profile above and let it tune the **abstract format**
   (structured vs. single paragraph), the **opening hook** (managerial vs. methodological), the
   **lit-review placement**, and the **emphasis of the experiments** (managerial insight vs.
   computational rigor).
2. If they didn't, ask — or write to a neutral "top OR/MS" standard and state the assumption so they
   can redirect.
3. When in doubt about a specific journal's current format (structured abstract requirements, word
   limits, reference style), verify against the journal's author guidelines with `research-lookup`
   rather than guessing.
