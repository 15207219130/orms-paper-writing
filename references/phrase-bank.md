# Phrase Bank: Rhetorical Moves in OR / MS / MSOM

Frequencies are the **share of papers in which a phrase appears at least once**, measured
over 2,322 OR/MS/MSOM articles (see `../CORPUS-NOTES.md`). Example sentences are
single-sentence excerpts from published articles in the corpus, included as style models.

Use this bank to *choose* a move, then write the sentence in your own words with your own
content. Copying a frame is fine; copying a sentence is not. This file complements
`introduction.md` (which covers the arc and the exemplar quotes), `literature-review.md`
(positioning mechanics) and `journal-benchmarks.md` (how often each move appears, and the
structural budget it has to fit inside).

Transportation Science is not in the corpus; these frequencies are OR / MS / M&SOM only.

---

## Move A — Opening hook (Introduction, paragraph 1)

The first paragraph is 127–158 words. It establishes that the setting is real and
consequential, usually with one sourced number.

**Frames**
- `In <year>, <quantity> of <thing> were <verb> <where> (<source> <year>).`
- `According to <agency>, <sector> contributes more than $<N> billion to <outcome>.`
- `<Firm> <did specific thing> (<source>), and <second firm> <did related thing> (<source>).`
- `<Practice>, a practice in which <actors> <do X>, is a common approach to <problem>.`

**Models**

| Journal | Example |
|---|---|
| OR | "In 2018, more than 10 billion tons of cargo were handled by seaports around the world, and the volume is still growing (UNCTAD 2019)." |
| MS | "The number of mobile apps grew rapidly from 15,000 in 2009 to more than 5.09 million in 2019." |
| MS | "In 2017, donors in the United States donated $410B, or 2.1% of the total GDP, … to philanthropic causes (Giving USA 2018)." |
| MSOM | "From 2000 to 2014, the United States' textiles and clothing waste increased 70%, to 16 million tonnes (Environmental Protection Agency 2014)." |
| MSOM | "SBs accounted for 18% of the entire sales in U.S. supermarkets in 2017 … and reached 31.4% of the value share in Europe in 2016." |

**Note.** OR permits a technical opening instead ("The nonlinearities of the SC-AC-OPF
problem involve products and trigonometric functions…"); MS and MSOM almost never do.

---

## Move B — The gap

The gap sentence is what licenses the paper. Three grammatical shapes cover nearly all of them.

**Frames**
- *Concessive*: `Despite <established importance>, <specific thing> remains <understudied / unclear>.`
- *Adversative*: `However, <the standard assumption / the existing approach> <fails / does not hold> when <condition>.`
- *Absence*: `To date, little is known about <X>.` / `<X> has not been studied in <setting>.`

`has not been` appears in ~5% of papers across all three journals; `despite` and `however`
carry most of the load.

**Models**
- OR: "Motivated by the multiplicative mechanism which is used by several internet auction markets, we set out to study the details of the associated static game, which has not been the subject of a prior methodical study."
- OR: "In reality, however, it is often difficult to justify the precise knowledge of such a distribution."
- MS: "Despite the many theoretical contributions studying social influences in demand, there is little empirical evidence measuring their importance in practice and the related implications for firm strategy and consumer welfare."
- MSOM: "Despite the prominence of subcontracting in project teams, its effect on project performance remains understudied."
- MSOM: "However, very little is known about the supply-side impacts of online reviews."

**Anti-pattern.** "No one has studied X" is a claim reviewers test and usually break. Prefer
"X has been studied under assumption A; we relax A" or "the empirical evidence on X is
limited to setting S".

---

## Move C — Research questions

Explicit interrogatives are a **MSOM signature**: `what is the` appears in 10% of MSOM
introductions vs. 5% in MS. Questions usually come in a block of two or three, immediately
after the gap.

**Frames**
- `How does <lever> affect <outcome>?`
- `How should <decision maker> <decide> when <friction>?`
- `What are the <consequences> of <practice> for <stakeholder>?`
- `Can <simple policy> <achieve outcome>?` / `Does <intervention> help or hurt <outcome>?`

**Models**
- OR: "Can a chaining system effectively mitigate such disruption?"
- MS: "How should the retailer use these past data collected in contexts different from the one in which it is currently operating?"
- MS: "Does joint control help or hurt collaboration?"
- MSOM: "How do the two commonly observed incentive schemes (fixed payment and logistics reimbursement) perform relative to the optimal incentive scheme and to each other?"
- MSOM: "Can a simple policy switch to subsidize charging be effective enough to stimulate EV adoptions?"

---

## Move D — Contribution statement

Only **13% (OR, MS) to 17% (MSOM)** of papers use an explicitly enumerated contribution
list. The majority integrate contributions into prose. Choose deliberately: enumerate when
the contributions are genuinely separable (a formulation, a theorem, an algorithm, an
experiment); use prose when there is one idea with consequences.

### D1 — Capability claim (OR register)
- `This paper contributes <result type> for <object> in <regime>.`
- `Our main contribution is to show that <property> holds when <condition>.`
- `We develop a <model class> whose optimal solution yields <object>.`

> "This paper contributes asymptotic optimality results for the projected inventory level policy in two asymptotic regimes."
> "One of our main contributions is to develop a mixed-integer programming (MIP) problem whose optimal solution yields a clearing vector in this model."

### D2 — Literature claim (MS register)
- `This paper contributes to the literature on <topic> by showing that <finding>.`
- `First, we contribute to a rapidly expanding literature studying <topic> (for recent reviews, see …).`

> "This paper contributes to the literature on peer effects, social interactions, and autonomy by showing that self-selection of peers can directly affect behavioral outcomes and performance."

### D3 — Enumerated list (all three; most common in MSOM)
- `In summary, we make the following contributions. 1. We introduce … 2. We provide the first … 3. We prove that … 4. We demonstrate numerically that …`

> "In summary, we make the following key contributions: • We show that the magnitude of the congestion spillover is substantial in our study hospital, implying that …"

A well-formed enumerated list moves down a ladder: **object introduced → theoretical
guarantee → computational/empirical evidence → managerial consequence.** Items should not
all be the same kind of claim.

### D4 — Priority claim — use sparingly
`to the best of our knowledge` appears in 2–4% of papers. It is a real move, but it invites
a reviewer to find the counterexample.

- `To the best of our knowledge, this is the first <study/model> to <specific, bounded claim>.`
- `To our knowledge, our work is the first to <verb> <narrow object> under <condition>.`

> "To the best of our knowledge, we are the first to propose transfer learning for demand forecasting with a pooling mechanism."

**Rule:** bound the claim with enough qualifiers that it is defensible ("the first to derive
*closed-form* optimal mechanisms *under distributional ambiguity*"), never "the first to
study X".

---

## Move E — Literature positioning

`is related to` (11%), `the literature on` (11%), `streams of literature` (9%) — all peak in
MSOM, consistent with its 63% standalone-review norm. The dominant organizing device is
**named streams**: 4.5% of MSOM papers literally write "three streams of", 4.4% "two
streams of".

**Frames**
- `Our paper is related to <N> streams of literature: (i) …, (ii) …, and (iii) ….`
- `Our work is closely related to the <topic> literature, which <does X>. We depart from it by <doing Y>.`
- `We build on <author> (<year>) by <specific extension>.`
- `In contrast to <paper>, which assumes <A>, we allow <B>.`

**Models**
- MSOM: "Our paper is closely related to three streams of literature: (i) design of innovation contests, (ii) research and development (R&D) co-opetition, and (iii) economics of data."
- MSOM: "This paper builds on the supplier encroachment literature, which shows that supplier encroachment can mitigate the double marginalization problem…"
- MS: "We build on their work by introducing the option for informed players to disclose their private information and examining how the timing of disclosure affects who discloses…"

**Rule for each stream paragraph:** name the stream → one sentence on what it establishes →
cite 3–6 representative papers → **one sentence that says precisely how this paper differs.**
A stream paragraph without that last sentence is a survey, not positioning.

---

## Move F — Introducing numerical work

`in this section we` appears in 31% of OR numerical sections, 14–15% in MS/MSOM — OR is the
most formulaic here, and that is acceptable.

**Frames**
- `In this section, we <conduct numerical experiments / evaluate the performance of our algorithm> to <purpose>.`
- `We benchmark the performance of <our policy> against <named alternatives> on <test bed>.`
- `We calibrate our model using <real data source> (details in Section <X> of the online appendix).`
- `This section presents computational results that demonstrate <claim> on real-world industrial instances.`

**Models**
- OR: "In this section, we present the computational experiments we have carried out to evaluate the empirical performance of the proposed methodology."
- OR: "We compare two approaches for scheduling power system operations: (i) AC-OPF … and (ii) SC-AC-OPF …"
- MSOM: "To further highlight how our results relate to practice, we calibrate our model using real-life data from Massachusetts."

**The purpose clause matters.** MS/MSOM numerical sections state *what the experiment is
for* ("to generate managerial insights into service systems with CR"), not just that it
exists. OR sections may state performance alone.

---

## Move G — Findings and managerial insight

`we find that` appears in **38% of MS and 38% of MSOM** papers — it is the standard verb of
result in both. MSOM adds the labeled `Managerial implications` block (82% of papers).

**Frames — findings**
- `We find that <effect>, especially when <condition>.`
- `Our results suggest that <interpretation>.` / `Our findings indicate that <consequence>.`
- `Although <expected effect>, our results indicate that <qualification>.`

**Frames — the reversal (MSOM's highest-value move)**
- `<Practice> does not always yield its expected result of <benefit>.`
- `It might be assumed that <obvious explanation>. However, our findings show that <it does not suffice>.`
- `This seemingly counterintuitive result stems from <the competing force>.`
- `Although it may seem counterintuitive to <action>, we identify situations where it is worthwhile to do so.`

**Frames — implications**
- `Our paper offers the following <N>-step guideline for practitioners facing <problem>.`
- `Our findings on <trade-off> offer important implications for <policy makers / platform designers>.`
- `Assuming <nominal parameter>, our findings indicate <quantified dollar consequence>.`

**Models**
- MS: "Although BOPS may increase sales from existing customers, our results indicate that a nontrivial part of the growth comes at the expense of competitors."
- MS: "Assuming a nominal commission for each successful delivery, our findings indicate the LMD firm faces million-dollar annual losses due to productivity spillovers resulting from fake remarks."
- MSOM: "Our results suggest dynamic routing is more beneficial than dynamic dispatching, especially when the fleet size is not so large."
- OR: "Our paper offers the following three-step guideline for practitioners faced with a data-driven decision problem."

**Quantify the implication.** The strongest insight sentences carry a magnitude (a %, a
dollar figure, a threshold condition). "Our policy performs better" is not an insight.

---

## Move H — Limitations and future research

`for future research` appears in 10% (OR), 19% (MS), **23% (MSOM)** of papers. The pattern
is a short closing paragraph of two to four concrete directions, each naming a specific
relaxation rather than a general aspiration.

**Frames**
- `We leave <specific extension> for future research.`
- `Future research could <verb> <specific setting or relaxation> — for example, <instance>.`
- `A natural next question is how to <extend> when <assumption> is relaxed; this would require <different technique>.`
- `Another important research avenue is to embed <our object> in <downstream problem>.`

**Models**
- MS: "Future research could investigate other data-delivery options, incentives, interface design features, and use of data analytics to design personalized data plans — for example, with app-specific usage limits."
- MS: "Another important research avenue is to embed our neural network–based choice model in assortment optimization and pricing decision problems."
- OR: "However, this would require different methods in analyzing the regret, especially the loss of nonstationarity, which we shall leave for future research."

**Anti-pattern.** "This is a promising direction for future research" and "there are other
interesting related topics worth exploring" both occur in the corpus, but they carry no
information. Every future-work sentence should name the assumption being relaxed and,
ideally, why it is hard.

---

## Move I — The roadmap sentence

`The remainder of this paper is organized as follows` appears in 21–27% of papers — i.e.
roughly three quarters omit it. Include it only when the structure is non-obvious
(e.g., a paper whose analysis is split across two asymptotic regimes, or one that
interleaves theory and experiments). Otherwise cut it and give the words to the contribution.
