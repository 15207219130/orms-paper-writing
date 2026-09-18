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

Measured September 2026.
