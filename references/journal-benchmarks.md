# Journal Benchmarks: OR / MS / MSOM

Empirical norms measured from full text of **2,322 published articles** (Operations
Research n=96, Management Science n=1,268, M&SOM n=778; ~70% published 2022–2026).
Use these as *targets to hit*, not as rules to cite. Numbers are medians unless noted.
See `../CORPUS-NOTES.md` for how they were computed and their limitations.

This file is the quantitative companion to `journal-profiles.md` (which covers *ethos* and
includes Transportation Science and adjacent venues). **Transportation Science is not in this
corpus** — nothing on this page should be applied to a TS submission without checking.
For the sentence-level patterns behind these structures, see `phrase-bank.md`.

---

## 1. Length envelope (main text, excluding online appendix)

| | **OR** | **MS** | **MSOM** |
|---|---|---|---|
| Total words | **18,900** | **16,100** | **14,800** |
| Interquartile range | 14,600 – 24,600 | 14,400 – 18,000 | 13,400 – 16,000 |
| Top-level sections | 6 | 6 | 6 |
| Abstract words | 185 | 211 | **285** (structured) |
| Introduction words | **2,000** | 1,630 | 1,510 |
| Conclusion words | 1,290 | 1,360 | 1,310 |
| Figures | 5 | 5 | 5 |
| Tables | 4 | 4 | 4 |
| Numbered results (Prop./Thm./Lem./Cor.) | **6** | 5 | 5 |

**How to use it.** MSOM is the tightest of the three — a 20,000-word MSOM draft is a
revision problem, not a formatting problem. OR tolerates length only when the extra words
are theorems and proofs; its IQR is wide because methodological papers run long. MS sits in
a narrow band (14.4k–18k covers half of all papers), so treat 16k as the design target.

Modern practice is to push proofs and secondary experiments to the online appendix: **0%**
of sampled papers carry a printed "Appendix" as a top-level main-text section.

---

## 2. Word budget by section position

Median share of main-text words, by section number:

| Section # | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 |
|---|---|---|---|---|---|---|---|---|
| **OR** | 10% | 8% | 12% | 14% | 14% | 13% | 13% | 11% |
| **MS** | 11% | 9% | 13% | 17% | 16% | 15% | 14% | 14% |
| **MSOM** | 11% | 8% | **15%** | **19%** | 16% | 14% | 13% | 13% |

Two invariants across all three journals:

1. **The Introduction is ~10–11% of the paper.** Not 20%. A 16,000-word MS paper gets a
   1,600–1,800-word Introduction. Longer than that reads as a paper that has not decided
   what its contribution is.
2. **The Literature Review is the smallest section (8–9%).** It is a positioning device,
   not a survey. In a 15,000-word MSOM paper that is ~1,200 words — roughly three streams
   at 350–400 words each.

The mass sits in sections 3–5 (model + analysis + results): **43% in MS, 50% in MSOM.**

---

## 3. Section architecture

Percent of papers containing a top-level section of each kind:

| Section | **OR** | **MS** | **MSOM** |
|---|---|---|---|
| Introduction | 98% | 98% | 98% |
| Standalone Literature Review | **30%** | 44% | **63%** |
| Model / Problem Formulation | 35% | 43% | **56%** |
| Numerical / Computational / Case study | 51% | 41% | 35% |
| Data | 5% | 23% | 22% |
| Discussion | 12% | **33%** | 26% |
| Extensions | 14% | 12% | 17% |
| Robustness checks | 3% | 6% | 5% |
| Conclusion | 74% | 78% | 81% |

### Where the literature review goes

| | Standalone §2 | Subsection inside §1 | No standalone section |
|---|---|---|---|
| **OR** | 29% | 35% | **70%** |
| **MS** | 41% | 20% | 56% |
| **MSOM** | **61%** | 15% | 37% |

This is the single sharpest structural difference between the journals.

- **OR**: the default is *no* standalone review. Positioning happens in a `1.x Literature
  Review` subsection (35%) or is woven into the motivation. Reviewers want the model early.
- **MSOM**: the default *is* a standalone §2 Literature Review (61%), usually organized as
  two or three named streams.
- **MS**: split roughly evenly; follow the norm of the sub-area you are submitting to.

### Introduction subsections

| | Median 1.x subsections | Most common |
|---|---|---|
| **OR** | **2** | `1.1 Literature Review` (16%), `1.x Contributions` (~20% across variants), `Notation`, `Outline` |
| **MS** | **0** | `Related Literature` (8%), `Literature Review` (5%), `Contributions` (3%) |
| **MSOM** | **0** | `Literature Review` (6%), `Related Literature` (5%), `Contributions` (5%) |

OR introductions are *structured*; MS and MSOM introductions are usually **continuous
prose** with no subsection headers. Do not add `1.1 Motivation / 1.2 Contributions /
1.3 Organization` to an MS or MSOM submission by default — the majority of published papers
do not.

### Introduction shape

| | Paragraphs | First-paragraph words |
|---|---|---|
| **OR** | **7** | 157 |
| **MS** | 5 | 158 |
| **MSOM** | 5 | **127** |

Two rhetorical devices are **minority practice** and should be used deliberately, not by reflex:

- Enumerated contributions ("First, … Second, …" or a bulleted list): OR 13%, MS 13%, **MSOM 17%**
- "The remainder of this paper is organized as follows": OR 27%, MS 21%, MSOM 26%

Roughly three quarters of published papers omit the roadmap sentence. Keep it only if the
paper has an unusual structure that a reader would otherwise mis-navigate.

---

## 4. The MSOM structured abstract

M&SOM requires labeled abstract sections. Observed label frequencies (share of MSOM papers):

| Label | Frequency |
|---|---|
| `Managerial implications:` | **82%** |
| `Results:` | 48% |
| `Problem definition:` | 46% |
| `Methodology:` | 42% |
| `Methodology/results:` | 38% |
| `Academic/practical relevance:` | 37% |

Two live conventions exist: the four-part form
(`Problem definition / Academic-practical relevance / Methodology / Results / Managerial implications`)
and the compressed three-part form (`Problem definition / Methodology-results / Managerial
implications`). Both are current; the compressed form is more common in recent issues.
**`Managerial implications` is effectively mandatory** — it appears in 82% of papers and its
absence is the most visible way to look like a mis-targeted submission.

OR and MS abstracts are **unstructured single paragraphs**: 185 and 211 words respectively.
Do not import MSOM labels into an OR or MS abstract.

---

## 5. Quick self-check before submission

```
[ ] Main text within the journal's IQR (OR 14.6–24.6k / MS 14.4–18k / MSOM 13.4–16k)
[ ] Introduction ≤ 11% of total words
[ ] Literature review ≤ 9% of total words
[ ] Sections 3–5 carry 43–50% of the words
[ ] Abstract format matches the journal (MSOM: labeled, with Managerial implications)
[ ] Literature review placed per journal norm (OR: inside §1 or absent; MSOM: standalone §2)
[ ] MS/MSOM introduction has no 1.x subsection headers unless there is a reason
[ ] 4–6 numbered theoretical results, 5 figures, 4 tables as an order-of-magnitude check
[ ] Proofs and secondary experiments in the online appendix, not the main text
```
