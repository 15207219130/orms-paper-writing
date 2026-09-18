# The Logic of the Introduction

`introduction.md` covers the *moves* an introduction makes and quotes exemplars.
This file covers the **order** they come in, and why that order is the one reviewers expect.

Method: every sentence in every introduction in the corpus (OR n=94, MS n=1,224, M&SOM n=749,
introductions of ≥15 sentences) was tagged with the rhetorical move it performs, and the
position of each move recorded as a fraction of the introduction. Detection is keyword-based,
so treat the percentages as indicative and the **ordering and shape** as the finding. About
**75% of sentences carry no move marker at all** — they are expository prose. The moves are
punctuation inside an argument, not the argument itself.

---

## 1. The argument chain

Median position of the **first** occurrence of each move, as a fraction of the introduction:

| Move | **OR** | **MS** | **M&SOM** |
|---|---|---|---|
| EVIDENCE — a sourced fact, number, or named firm | 0.15 | 0.11 | **0.07** |
| GAP — what is not known / does not hold | **0.19** | **0.15** | **0.17** |
| TENSION — why it is hard; the trade-off | 0.24 | 0.33 | 0.35 |
| RQ — an explicit question | 0.30 | 0.28 | 0.35 |
| LIT — positioning against a literature | 0.30 | 0.40 | 0.39 |
| METHOD — "we build / we use data on…" | 0.38 | 0.42 | 0.51 |
| CONTRIB — an explicit contribution claim | 0.52 | 0.50 | 0.53 |
| PREVIEW — "we find / we show that…" | 0.44 | 0.50 | 0.63 |
| ROADMAP | 0.90 | 0.91 | 0.91 |

**The single most transferable finding: the gap arrives in the first fifth of the
introduction — before the literature does.** Across all three journals the first gap sentence
lands at 15–19% of the introduction, while the first literature-positioning sentence lands at
30–40%. Published papers do not review the field and then discover a hole. They assert the
hole early, from the phenomenon, and then bring the literature in to *substantiate* it.

The common draft failure is the reverse order — three paragraphs of "X has been studied by A,
B and C; however, none of them consider Y" — which delays the gap to the halfway point and
makes the paper read as literature-driven rather than problem-driven.

**Second finding: OR states the method and previews results before claiming contributions
(METHOD 0.38 → PREVIEW 0.44 → CONTRIB 0.52). M&SOM does the reverse (CONTRIB 0.53 → PREVIEW
0.63).** An OR introduction earns the right to claim by showing what was proved; an M&SOM
introduction declares the contribution and then unpacks the findings underneath it.

---

## 2. The shape, in ten slices

Share of introduction sentences carrying each move, by decile of the introduction:

**M&SOM**

| decile | 0–10 | 10–20 | 20–30 | 30–40 | 40–50 | 50–60 | 60–70 | 70–80 | 80–90 | 90–100 |
|---|---|---|---|---|---|---|---|---|---|---|
| EVIDENCE | **14%** | 10% | 8% | 6% | 5% | 5% | 4% | 4% | 4% | 2% |
| GAP | 5% | 6% | 5% | 5% | 4% | 4% | 4% | 4% | 4% | 2% |
| RQ | 2% | 2% | 3% | **4%** | **4%** | **4%** | 2% | 2% | 1% | 1% |
| LIT | 2% | 2% | 2% | 3% | 4% | 3% | 3% | 3% | **5%** | **5%** |
| CONTRIB | 1% | 2% | 2% | 2% | 2% | 2% | 3% | 3% | **4%** | 3% |
| PREVIEW | 0% | 1% | 1% | 3% | 4% | 5% | **8%** | **8%** | **8%** | 5% |
| ROADMAP | 0% | 0% | 0% | 0% | 0% | 0% | 0% | 0% | 4% | **9%** |

MS and OR have the same shape with flatter amplitudes (MS EVIDENCE 9%→2%, OR 6%→2%).

Three structural facts fall out of this table:

1. **Concreteness decays monotonically.** Sourced facts and numbers are front-loaded and
   thin out steadily. An introduction whose only statistic appears in paragraph four has its
   concreteness in the wrong place.
2. **The gap is flat, not a single beat.** GAP sits at 3–6% in *every* decile. Published
   introductions re-open a small gap each time they introduce a new element: the phenomenon
   has a gap, the existing method has a gap, the closest paper has a gap. Drafts that spend
   one paragraph on "the research gap" and never return to it are doing 10% of this work.
3. **Findings crest in the final third and the roadmap is the last beat.** PREVIEW peaks in
   deciles 6–8, not at the end; the last decile belongs to the roadmap (when there is one —
   only 21–27% of papers have one, see `introduction.md`).

---

## 3. The adjacency rules

Strongest sentence-to-sentence transitions between marked moves (the probability that the
next marked sentence carries move B, given the current one carries A):

| Transition | OR | MS | M&SOM | What it encodes |
|---|---|---|---|---|
| **METHOD → PREVIEW** | 35% | 34% | 32% | "We build X. We show Y." The method sentence is never left standing alone. |
| **RQ → RQ** | 76% | 70% | 75% | Questions come in blocks of two or three, never singly. |
| **EVIDENCE → GAP** | 26% | 17% | 23% | A fact, then immediately what is not known about it. |
| **GAP → EVIDENCE** | 27% | 25% | 26% | And the reverse: a gap, then the fact that makes it matter. |
| **PREVIEW → PREVIEW** | 53% | 40% | 40% | Findings are stated in runs. |
| **CONTRIB → CONTRIB** | 26% | 39% | 25% | So are contributions. |

The `EVIDENCE ↔ GAP` pair running in both directions is the engine of these introductions:
concrete fact and missing knowledge alternate, tightly, all the way through. This is what
makes a published introduction feel dense — not longer sentences, but a shorter cycle between
"here is something true about the world" and "here is what we cannot currently say about it."

**Never leave a METHOD sentence as the last word of a paragraph.** In every journal the
strongest forward transition is into a finding. "We develop a Stackelberg model of green
investment" is not a claim; "…and show that a higher subsidy can lower total investment" is.

---

## 4. A skeleton that matches the measured shape

For a 5-paragraph MS/M&SOM introduction (~1,500–1,650 words). Percentages are where each
element should fall.

```
¶1  (0–20%)   EVIDENCE-dense. The setting, with one or two sourced numbers or named
              firms. Close the paragraph on the first GAP sentence — not on a preview
              of the paper.
¶2  (20–40%)  The specific decision/mechanism, with TENSION: why the obvious answer is
              not obviously right. End with the RQ block: two or three questions.
¶3  (40–60%)  METHOD, then immediately PREVIEW. What we build, what data, what we find.
              LIT enters here — positioning against the streams whose gap ¶1 asserted.
¶4  (60–85%)  CONTRIB and the rest of the PREVIEW. Contributions in prose unless they
              are genuinely separable; each one attached to the finding that delivers it.
¶5  (85–100%) The managerial payoff (M&SOM: mandatory) — and ROADMAP only if the
              structure is non-obvious.
```

For OR (~2,000 words, 7 paragraphs, and structured with `1.x` subsections): the same chain,
but with TENSION arriving earlier (0.24), the technical positioning enlarged, PREVIEW before
CONTRIB, and typically a `1.x Contributions` subsection carrying ¶4–5.

---

## 5. Worked contrast

The positive example below is a real published arc (Ahuja, Alan & Arıkan, *M&SOM* 2025, on
airline route-level decisions); the negative is **constructed** to show the corresponding
failure — it is not quoted from any paper.

### ✗ What a first draft usually does

> Supply chain resilience has attracted considerable attention in recent years. Many scholars
> have studied resilience investment. Smith (2019) studied supplier diversification. Lee and
> Zhang (2020) studied inventory buffering. Kumar et al. (2021) studied multi-sourcing.
> However, none of these papers consider green investment simultaneously. Therefore, this
> paper studies the joint green-resilience investment problem. We build an evolutionary game
> model. The rest of this paper is organized as follows.

Diagnosis against the measured norms: no EVIDENCE at all (published ¶1 runs at 14%); the first
GAP arrives at ~0.6 of the introduction instead of 0.17, and arrives *out of* the literature
rather than out of the phenomenon; the gap is a conjunction ("nobody did A and B together"),
which is the weakest form because it is satisfiable by anyone; no TENSION, so the reader never
learns why the joint problem is hard; METHOD is left as the last word with no PREVIEW after it;
and the roadmap does the work a contribution should do.

### ✓ What the published arc does

> **[EVIDENCE, ¶1]** The FAA estimates the aviation industry contributes more than $500
> billion to U.S. GDP; operational disruptions cost airlines and passengers billions every
> year, and the hourly value of travel-time savings is $36.10 for personal travel and $63.20
> for business travel.
> **[GAP, ¶1 close]** Studies of travel times and delays typically use public flight-level
> on-time data. However, those data lack passenger-level details such as itineraries and
> layover times, which makes capturing passengers' actual travel experience difficult.
> **[METHOD]** We overcome this limitation using a proprietary passenger-level data set from
> Southwest Airlines covering roughly 20 million passenger itineraries.
> **[TENSION → PREVIEW]** … the repeal's impact varies widely across destinations; the
> decision to start nonstop service alone does not explain the heterogeneity.
> **[CONTRIB]** Our contributions are threefold. First, we leverage the Wright Amendment
> repeal to quantify … Second, we develop two route-level metrics …

The gap here is a *capability* gap in the evidence, asserted in the first paragraph, from the
phenomenon — and the method sentence that follows is the direct answer to it. That is the
chain the measurements describe: EVIDENCE → GAP → METHOD → PREVIEW → CONTRIB, with the
literature arriving later to confirm rather than to motivate.

---

## 6. Diagnostic questions for a draft introduction

- Where does the first gap sentence sit? If past 25% of the introduction, the paper is being
  motivated by the literature instead of by the problem.
- Does the gap come from the phenomenon, or only from a list of papers? "Nobody has combined
  A and B" is the weakest gap form in the corpus and the easiest for a referee to dismiss.
- Is there a sourced number in the first paragraph?
- Does every METHOD sentence have a finding attached within a sentence or two?
- Do the questions come as a block of two or three, or as one lonely question?
- Does the concreteness decay (facts early, claims late), or is it inverted?
- Does each new element open its own small gap, or is there a single "research gap" paragraph
  that is never revisited?
