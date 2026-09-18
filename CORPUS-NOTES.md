# Corpus Notes — how the benchmark numbers were produced

The quantitative claims in `references/journal-benchmarks.md` and `references/phrase-bank.md` —
and the measured blocks added to `references/journal-profiles.md`, `references/introduction.md`,
`references/literature-review.md` and `references/numerical-experiments.md` — are grounded in a
measured corpus rather than in recollection. This file records what was measured, how, and where
the numbers are weak, so that future updates can extend it rather than guess at it.

## Corpus

| Journal | PDFs available | Parsed into the analysis |
|---|---|---|
| Operations Research | 158 | 96 |
| Management Science | 1,358 | 1,268 |
| Manufacturing & Service Operations Management | 806 | 778 |
| **Total** | **2,322** | **2,142** |

Roughly 70% of parsed papers were published 2022–2026 (MS 981 of 1,268; MSOM 579 of 778;
OR 54 of 96). Papers were drawn from a local library organized by journal and research
field, so field coverage reflects that library's emphases (operations, sustainability,
transportation/logistics, optimization, platforms, healthcare) rather than a random draw
from each journal.

A separate IJAA collection (463 PDFs) was excluded — different field, different conventions.

## Method

1. Text extracted with `pdftotext -nopgbrk` (Poppler), run in parallel over the local library.
2. Section spine detected by matching numbered top-level headings (`^\s*(\d{1,2})\.\s+Title$`)
   and keeping only a monotone sequence 1, 2, 3, …; level-2 headings (`1.1`, `4.2`) captured
   separately. Papers with fewer than 3 or 4 recovered sections were dropped from structural
   statistics.
3. Per-paper measurements: total words, words per section, figure/table/theorem counts from
   caption references, abstract, introduction and conclusion text.
4. Phrase frequencies: normalized 3–6-grams counted at the **document level** (share of
   papers containing the phrase at least once, not raw occurrence counts), restricted to
   sentences matching the rhetorical move being studied, and pruned so that a short phrase is
   dropped when a longer phrase containing it has ≥70% of its count.
5. **Argument-chain analysis** (the four `logic-*.md` references): every sentence of every
   introduction, literature-review section, model section and numerical section was tagged with
   the rhetorical move it performs, using ordered keyword rules (first matching rule wins), and
   each move's position recorded as a fraction of the section. Reported quantities are the
   median position of a move's first occurrence, its density by decile/fifth, and
   sentence-to-sentence transition probabilities between marked moves.
6. **Methodological typing**: papers were classified as analytical/game, optimization/algorithm,
   empirical/econometric or simulation by counting type-specific vocabulary across the whole
   body; a paper with ≥8 hits in a category carries that label, and may carry two.

## Known limitations — read the numbers with these in mind

- **OR is thin.** 96 papers, of which 54 are recent. OR percentages carry roughly ±10
  percentage points of noise; treat OR/MS/MSOM *ordering* as reliable and OR point estimates
  as indicative. MS and MSOM samples are large enough for the point estimates to be stable.
- **Field skew.** The library over-represents operations, sustainability and optimization
  relative to, say, finance or accounting within MS. Sub-area conventions differ, especially
  around literature-review placement.
- **PDF extraction noise.** Two-column INFORMS layouts interleave running headers, footnotes
  and margin text into the extracted stream. Journal boilerplate ("Management Science, vol.,
  no., pp., © INFORMS") survives in some phrase counts and was filtered where noticed; a few
  residual artifacts remain and were excluded by hand from the reference files.
- **Word counts include** running headers and reference lists that could not be cleanly
  separated in every paper, so absolute lengths are modest over-estimates. Relative shares by
  section position are unaffected.
- **Reference counts were not usable** — the extraction heuristic failed on INFORMS
  reference formatting and produced implausible values. No claim in the reference files
  depends on them.
- **The evidence-register table in `references/numerical-experiments.md`** was computed over
  abstract + introduction + conclusion + the opening ~1,200 characters of each section, not full
  body text. Those figures are lower bounds and are labeled as such.
- **Transportation Science is not in this corpus.** The TS and adjacent-venue profiles in
  `references/journal-profiles.md` remain qualitative; do not apply OR/MS/M&SOM numbers to them.
- **Section-presence percentages** depend on heading detection: a paper whose numerical work
  lives inside "4. Analysis" is not counted as having a numerical section. Sums therefore
  under-count.
- **Move tagging is keyword-based and single-label.** Each sentence gets the first matching
  rule, so a sentence doing two jobs is counted once, and a move phrased without its usual
  vocabulary is missed. About 75% of introduction sentences match no rule at all and are
  counted as expository. Consequently the *levels* in the `logic-*.md` files are lower bounds
  and should not be quoted as "X% of sentences are gap sentences" in any absolute sense; the
  **ordering, shape and transition structure** are what the analysis supports.
- **Paragraph structure could not be recovered reliably.** Two-column INFORMS PDFs interleave
  columns and break paragraphs unpredictably under text extraction (a block-based PyMuPDF pass
  was tried and was not reliable either). All argument-chain analysis is therefore at the
  *sentence* level, positioned within the section, rather than paragraph-by-paragraph.
- **"Assumption justified nearby" (~20%)** looks only at the two sentences following an
  assumption sentence. Justification offered in a separate later discussion is not counted, so
  the true rate of justified assumptions is higher than the figure reported.
- **"Result followed by intuition" (~29%)** searches ~900 characters after a numbered result
  statement for explanation cues. Cross-references to a result elsewhere in the paper can be
  matched as statements, so this figure is noisy in both directions.
- **Body text was truncated at 30,000 characters per section** in the pass used for the
  methodology analysis, so counts over very long sections are slight under-estimates.
- **Negative examples in the `logic-*.md` files are constructed**, not quoted. No published
  paper in the corpus is held up as an example of bad writing; the contrast cases were written
  to illustrate the failure mode the measurements describe.

## Regenerating or extending

The pipeline is three short scripts (extract → structural statistics → phrase mining) run
directly against the PDF library; nothing is stored beyond a JSONL of per-paper extractions.
To extend the corpus, add PDFs to the library and re-run — extraction is idempotent and skips
files already processed.

Worth adding in a future pass:

- More Operations Research papers, to bring that arm to parity.
- A pass restricted to 2024–2026 only, to detect drift in conventions (e.g. whether the
  compressed MSOM abstract is displacing the four-part form).
- Desk-reject and revise-and-resubmit language from editorial statements, which this corpus
  does not contain.
- Per-sub-area breakdowns within MS, where the literature-review norm is likely bimodal.

### Added pass: optimization problem statements

`references/optimization-problem-definition.md` is built on two sub-corpora drawn from the 346
papers typed as optimization/algorithmic: the **114 M&SOM papers carrying an explicit
`Problem definition:` abstract label** (segmented by regular expression between that label and the
next one), and the **213 optimization papers with a recoverable model or problem-statement
section**. Element positions are the median, over papers, of the index of the first sentence
matching that element's keyword rule, normalized by the number of sentences in the block. Verb
counts are raw occurrences, not document frequencies. The same keyword caveats apply: an element
phrased without its usual vocabulary is missed, so presence percentages are lower bounds while the
*ordering* is the finding.

Measured September 2026.
