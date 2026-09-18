# The Logic of the Literature Review

`literature-review.md` covers placement, stream organization and the positioning templates.
This file covers the **internal argument**: what a review is actually proving, where the
positioning work sits, and why most drafts get the direction of the argument backwards.

Method: sentence-level tagging of every standalone literature-review section in the corpus
(OR n=26, MS n=533, M&SOM n=469, sections of ≥12 sentences), plus the introduction-level
timing from `logic-introduction.md`. Keyword-based; read the ordering as the finding.

---

## 1. What the section is proving

A literature review in these journals is a **claim of necessity**, not a map of a field. The
proposition it must establish is:

> Given everything already known, the question this paper asks still cannot be answered.

Everything follows from that. A stream is included because, without it, a referee could say
"this is already solved." A stream that does not close off a possible objection is padding —
and padding is expensive here, because the review is the smallest section in the paper (8–9%
of total words; see `journal-benchmarks.md`).

**The direction matters and drafts usually reverse it.** Measured in the introduction, the
first gap sentence lands at 15–19% of the introduction but the first literature-positioning
sentence at 30–40%. Published papers assert the gap *from the phenomenon*, then recruit the
literature to show the gap is real. Drafts commonly do the opposite — survey first, derive a
gap from the survey — which produces a gap of the form "nobody has combined A and B," the
form referees dismiss most easily because anyone can satisfy it.

---

## 2. Where the positioning work sits

| | **OR** | **MS** | **M&SOM** |
|---|---|---|---|
| Announces its streams within the first 6 sentences | 23% | 32% | **41%** |
| Share of review sentences that are positioning sentences | 4.6% | 7.4% | **7.9%** |
| Has a positioning sentence in the final quarter of the section | 50% | 57% | **62%** |
| Median position of positioning sentences | 0.68 | 0.55 | 0.59 |

Two things to read off this:

1. **Positioning is distributed, not terminal.** Roughly **one sentence in thirteen** is a
   positioning sentence in MS and M&SOM, and their median position sits mid-section. The work
   is done continuously — at the close of each stream — not saved for a summary paragraph.
   Only about 60% of papers additionally land one in the final quarter.
2. **Announcing the streams up front is the M&SOM habit** (41%) more than the OR one (23%),
   consistent with M&SOM's 61% standalone-section norm. If you write a standalone section,
   announce the streams in its first two or three sentences.

A practical target for a three-stream, ~1,200-word M&SOM review: an announcing sentence, then
~350–400 words per stream, each closing on its own positioning sentence, with roughly 6–8
positioning sentences in the section as a whole.

---

## 3. The internal shape of one stream

The published pattern, repeated per stream:

```
1. NAME      "Our paper is related to the literature on <stream>."
2. ESTABLISH What this stream has settled — the result a referee would cite against you.
             Parenthetical citation clusters do this work.
3. NARROW    The two or three papers closest to yours, cited author-prominently, with what
             each actually does.
4. POSITION  One sentence: the axis on which you differ. This sentence is non-negotiable.
```

Step 2 is the step drafts skip, and skipping it is what makes a review read as defensive.
You have to state what the stream *has* achieved before saying what it has not; a reader who
is told only what prior work fails to do concludes the author has not read it.

Real positioning sentences from the corpus, showing the range of axes:

> "Departing from these studies, our paper focuses on platform competition and its effect on
> participating players within a sharing economy." — *MS 2022* (axis: object of study)

> "All of the aforementioned papers analyze settings that feature consumer data-based price
> discrimination. In contrast, our model is designed to study the interplay between the upside
> data utilization…" — *MS 2025* (axis: mechanism)

> "In contrast, we argue that SUD treatment allocation in the United States requires a
> different framework." — *M&SOM 2025* (axis: the framework itself is wrong for this setting)

> "Unlike prior methods, the present filtering procedure does not result in data loss."
> — *M&SOM 2026* (axis: a concrete property of the method)

Note how narrow each is. **Single-axis differentiation is the strongest form** — one dimension,
stated plainly, easy for a referee to accept. Multi-axis differentiation ("we differ in the
model, the objective, the solution method and the application") reads as an admission that no
single difference is load-bearing.

---

## 4. Ordering the streams

Order them so that the **last stream is the closest to your paper**. The review should
converge: the earliest stream establishes that the problem class matters, the last one
establishes that the specific question is open. The final positioning sentence of the last
stream should be one restatement away from your first contribution.

The mirror test, which `citations-and-coherence.md` enforces: **the union of the gaps closing
each stream should equal the set of contributions claimed in the introduction.** If a stream
closes on a gap that no contribution fills, cut the stream. If a contribution has no gap
behind it, the review is incomplete — a referee will ask what made that contribution necessary.

---

## 5. Worked contrast

The negative example is **constructed** to show the failure mode; the positive is rebuilt in
the same content area using the published pattern.

### ✗ Bibliography-in-prose (constructed)

> Green supply chain investment has been widely studied. Smith (2018) studies a manufacturer's
> green investment under carbon tax. Lee and Zhang (2019) extend this to a two-echelon chain.
> Kumar et al. (2020) consider consumer environmental awareness. Wang (2021) adds a
> cost-sharing contract. Chen and Liu (2022) study resilience investment under disruption.
> Zhao et al. (2023) consider a risk-sharing contract. However, none of these papers consider
> green and resilience investment together under an evolutionary game framework.

Every sentence has the same grammatical shape (Author + verb + object), so the paragraph has
no argument — it has a sequence. Nothing is established, nothing is narrowed, and the single
positioning sentence is a conjunction gap that any of the six cited authors could close in
their next paper. There are zero positioning sentences before the last one, against a corpus
norm of one in thirteen.

### ✓ The same material, argued

> **[NAME]** Our work is related to two streams: green investment in supply chains, and
> operational resilience to disruption.
> **[ESTABLISH]** The first stream has established that a manufacturer's green investment is
> increasing in consumer environmental awareness and that cost-sharing contracts can restore
> the centralized investment level (Smith 2018, Lee and Zhang 2019, Wang 2021). That result
> rests on treating the investment's return as deterministic.
> **[NARROW]** Closest to our setting, Kumar et al. (2020) allow a stochastic green return but
> retain a single decision period, so the firms' investment shares cannot adjust to what the
> other party did.
> **[POSITION]** We depart on that one axis: our investment shares evolve, so the equilibrium
> is a rest point of the adjustment process rather than a one-shot best response — which is
> what allows a cost-sharing contract to stabilize an investment level that no single-period
> analysis would sustain.
> **[NAME, stream 2]** The second stream …

The gap is now a *property* gap (deterministic return, one-shot adjustment) rather than a
conjunction gap, the axis is single, and the positioning sentence already contains the shape
of the paper's contribution.

---

## 6. Diagnostic questions

- Does each stream close with a positioning sentence, or only the section as a whole?
- Is the review's overall gap a *conjunction* ("nobody did A and B") or a *property* ("prior
  work assumes X; we relax X")? The first is weak; rewrite it as the second.
- Is what each stream has established stated before what it lacks?
- Is the differentiation single-axis?
- Is the last stream the closest one?
- Do the gaps and the contributions form a bijection?
- Is the section within 8–9% of total words? A review longer than that is a survey the paper
  did not need.
