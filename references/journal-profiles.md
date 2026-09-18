# Journal Profiles: MS vs OR vs Transportation Science vs M&SOM

The core writing conventions in the other reference files are shared across these journals — they are
all INFORMS-family, author-date, "we"-active, prose-heavy venues. But the *framing* differs, and
matching the target journal's ethos is part of writing well. This file is a quick orientation; the
section references carry per-journal notes inline. When the user names a target, read its profile
here and let it shape emphasis (especially in the abstract, introduction, and the managerial framing
of the experiments). When they don't name one, ask, or default to a neutral "top OR/MS" framing and
say so.

The single most useful question to keep asking: **what does this journal's reader want to take away?**

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
