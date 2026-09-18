---
name: orms-paper-writing
description: >-
  Write, draft, revise, or polish manuscripts and individual sections for top operations-research /
  management-science / transportation journals (Operations Research, Management Science, M&SOM,
  Transportation Science, POMS, and other INFORMS journals). Use this skill whenever the user is
  working on an academic OR/MS/optimization paper — its introduction, literature review,
  model/formulation, solution/algorithm, numerical experiments / computational study, abstract,
  contributions, or conclusion — or asks to make writing "read like a top-journal paper," check
  narrative coherence across sections, verify that the solution section matches the model, or fix
  citations. Trigger for English requests ("write the model section for an OR submission", "draft my
  intro and contributions", "revise this literature review", "design the numerical experiments
  section", "make this paper publication-ready for Management Science") and for Chinese ones
  ("写论文 / 投稿 / 引言 / 文献综述 / 模型部分 / 求解部分 / 数值实验", "润色成顶刊风格",
  "Management Science / Operations Research / Transportation Science 风格", "帮我写方法论/数值实验/贡献点").
  Also use when deciding which of Operations Research, Management Science or M&SOM a paper should
  target, when checking a draft against measured length / structure / abstract norms for those
  journals, or when converting a draft from one of them to another ("这篇投 OR 还是 MSOM",
  "改投 Management Science 要改什么", "篇幅结构符合顶刊规范吗").
  Trigger even when the user does not say the word "skill" and even when they name only a single
  section. Do NOT use for non-OR empirical social-science papers, wet-lab / natural-science
  manuscripts, or generic essays — for those, prefer the scientific-writing skill.
---

# Writing for OR / MS / Transportation Journals

This skill helps you write and revise papers in the house style of the top operations-research,
management-science, and transportation journals. It is distilled from a corpus of flagship papers
(Operations Research, Management Science, M&SOM, Transportation Science, Mathematical Programming,
and strong working papers) spanning revenue management, online optimization, transportation &
logistics, assortment, inventory, location, and ML-for-optimization. The conventions below are not
invented — they are the recurring patterns those papers actually share, with real exemplars quoted
in the reference files.

The goal is not to mechanically pattern-match. These journals reward writing that is *logically
tight*: an introduction that promises exactly what later sections deliver, a model that is set up so
the solution section can refer back to it cleanly, experiments that answer the questions the
introduction raised, and citations that genuinely support the claims attached to them. The skill is
organized so you can work on one section at a time while keeping the whole paper coherent.

## What the user usually wants

Most requests are one of: (a) **draft** a section from rough materials (a model spec, a list of
contributions, experimental results); (b) **revise/polish** an existing draft into top-journal
style; (c) **critique** a draft for narrative logic, coherence, or citation problems. Always
establish which of these it is, and which section(s), before writing.

## Output language

Produce the paper prose in **English** academic style (target journals are English-language).
**Report your decisions, open questions, and the verification checklist to the user in the language
they are writing to you in** (default: Chinese if they wrote in Chinese). Never silently switch the
paper itself to Chinese.

## Routing — which reference to read

Read `references/style-mechanics.md` on essentially every task (it governs tense, voice, hedging,
and prose discipline that apply everywhere). Then load the section-specific reference(s):

| User is working on… | Read |
|---|---|
| Abstract, introduction, contributions, conclusion, "the framing" | `references/introduction.md` |
| Literature review / related work / positioning against prior work | `references/literature-review.md` |
| Model, formulation, problem statement, assumptions, notation | `references/model-formulation.md` |
| Solution method, algorithm, theorems/proofs, structural analysis | `references/solution-method.md` |
| Numerical experiments, computational study, case study, managerial insights | `references/numerical-experiments.md` |
| Citations, cross-references, checking intro↔body / model↔solution coherence | `references/citations-and-coherence.md` |
| Which journal? MS vs OR vs Transportation Science vs M&SOM differences; converting between them | `references/journal-profiles.md` |
| Length, section architecture, word budgets, abstract format — "is this draft within norms?" | `references/journal-benchmarks.md` |
| Sentence-level frames for a specific move (hook, gap, RQ, contribution, positioning, insight, future work) | `references/phrase-bank.md` |

If the user is writing a whole paper or asks about overall structure, skim all of them; the section
references are short. The two cross-cutting references (`citations-and-coherence.md`,
`style-mechanics.md`) apply to *every* section and encode the user's top priorities (citation
correctness and cross-section correspondence), so do not skip them.

## Corpus-grounded norms

Two kinds of guidance live in this skill. The section references distil *how flagship papers
argue* — read qualitatively, from exemplars. `references/journal-benchmarks.md` and
`references/phrase-bank.md` add something different: **measured norms** from full-text analysis of
**2,322 articles** in Operations Research, Management Science and M&SOM (~70% published 2022–2026).
Frequencies there are the share of published papers exhibiting a feature. `CORPUS-NOTES.md` records
the method and the limits — the OR arm is only 96 papers (±10 percentage points), and Transportation
Science is **not** in the corpus, so none of those numbers transfer to a TS submission.

Use the numbers as the distribution a submission is judged against, not as rules to cite in prose.
But a draft sitting outside the interquartile range on length, or wearing another journal's abstract
format, is making an avoidable first impression.

**Journal fit, in one screen:**

| | **OR** | **MS** | **M&SOM** |
|---|---|---|---|
| Unit of contribution | A method or theorem | A finding about a system | A managerial decision |
| Abstract must earn | "We can now solve X." | "A affects B via C." | "Do X, not Y, when Z." |
| Median main text | 18.9k words | 16.1k | 14.8k |
| Abstract | 185 w, unstructured | 211 w, unstructured | 285 w, **structured** |
| Standalone literature review | 30% | 44% | 63% |
| Evidence register | Gaps, runtimes, benchmarks | Robustness, counterfactuals | Calibrated case + implications |

If removing the proofs kills the paper → OR. If removing the identification kills it → MS. If
removing the managerial implication kills it → M&SOM.

Three invariants hold across all three: the introduction is **~10–11%** of total words (not 20%);
the literature review is the **smallest** section (8–9%) and is positioning, not survey; sections
3–5 carry **43–50%** of the words.

### Defaults that differ from the natural drafting instinct

Each of these contradicts something an LLM (or a careful human) reaches for by reflex, and each is
backed by the corpus:

- **No roadmap paragraph by default.** "The remainder of this paper is organized as follows"
  appears in only 21–27% of published papers. Include it only when the structure is non-obvious.
- **No enumerated contribution list by default.** Only 13–17% of papers enumerate. Use a list when
  the contributions are separable (formulation / theorem / algorithm / experiment); use prose when
  there is one idea with consequences. If enumerating, the items should descend a ladder — object
  introduced → guarantee → evidence → managerial consequence — not repeat one kind of claim.
- **No `1.1 / 1.2 / 1.3` subsections in MS or M&SOM introductions.** Median in both is 0; OR is the
  exception at 2.
- **Do not default to a standalone literature-review section.** OR: 70% have none. M&SOM: 61% do.
  Let the target journal decide.
- **Bound every priority claim.** "To the best of our knowledge" appears in 2–4% of papers, always
  qualified. Never "the first to study X".
- **Never print an appendix in the main text** — 0% of sampled papers do.
- **Every future-work sentence names the assumption being relaxed.** "This is a promising direction
  for future research" carries no information.
- **Quantify every headline claim against a named baseline** — a percentage, a dollar figure, or a
  threshold condition.

## Core workflow

1. **Clarify the job.** Confirm: target journal (or "top OR/MS, unspecified"), which section(s),
   whether this is draft / revise / critique, and what raw material exists (model equations, a
   contributions list, results tables, an existing draft, a `.bib`). If the target journal matters
   for framing and the user hasn't said, ask or state the assumption — `journal-profiles.md`
   explains why MS vs OR vs TS changes the framing.

2. **Read the relevant reference(s)** from the routing table, plus `style-mechanics.md`. When the
   target journal is known and the job involves structure or length, also read
   `journal-benchmarks.md` and state the word/section budget you are writing to *before* drafting —
   it is far cheaper than cutting 4,000 words later.

3. **Draft or revise in English prose**, following the section's conventions. Write in flowing
   paragraphs, not bullet lists, unless the convention explicitly calls for an enumerated structure
   (e.g. a numbered contributions list or a constraint-by-constraint walkthrough). Keep the *why*
   in mind: every structural choice in these papers serves reader comprehension or reviewer
   scrutiny.

4. **Citation integrity pass** (see `citations-and-coherence.md`). This is a hard requirement the
   user cares about: **never fabricate a reference, a year, a venue, or a claim-about-a-paper.**
   When the draft needs to cite prior work, use `research-lookup` (or the `citation-management`
   skill) to find *real* papers and verify that each citation actually supports the sentence it is
   attached to. Anything you could not verify goes into an explicit "claims to verify" checklist for
   the user rather than into the prose as if confirmed.

5. **Coherence pass** (see `citations-and-coherence.md`). Check the correspondences the user
   emphasized: each contribution promised in the intro maps to a section that delivers it; the
   literature gap maps to the contributions; the solution section refers back to specific model
   objects (equations, assumptions, structures) by number; the experiments answer the questions the
   intro raised; forward/backward references point to the right places.

6. **Self-containment + style pass** (see `style-mechanics.md`). First, run the **self-containment
   check** — the paper must be fully intelligible to a reader who has only the PDF and never sees your
   code. This matters most precisely because you are often drafting inside the user's repository with
   the implementation open in context: do not let code identifiers, file/script names, config keys,
   raw hard-coded constants, or implementation-transcript algorithms leak into the prose; translate
   every one into the paper's defined notation and concepts. Then fix tense/voice/hedging so the verb
   register matches the claim type (hard verbs for proven results, hedged verbs for empirical ones),
   and strip AI-writing tells. For a dedicated de-AI polish, the `humanizer` skill can help.

7. **Norms pass** (see `journal-benchmarks.md`). For a whole-paper or structural job, check the
   draft against the target journal's measured distribution: total words inside the IQR;
   introduction ≤ 11% and literature review ≤ 9% of total words; sections 3–5 carrying 43–50%;
   abstract format correct for the journal (M&SOM: labeled, with `Managerial implications`);
   literature review placed per the journal's norm; ~5 figures / ~4 tables in the main text; no
   printed appendix. Report deviations as observations with the norm attached, not as errors —
   a paper can justifiably sit outside the range, but it should do so on purpose.

8. **Report back in the user's language**: what you wrote/changed and why, the citation checklist
   (verified vs. needs-checking), any coherence gaps you found, and open questions. Be honest about
   what is a placeholder versus what is confirmed.

For a multi-section or whole-paper job, work section by section but keep a running list of the
promises the intro/abstract make, so the later sections can be checked against them.

## Collaborator skills

- **`research-lookup`** and **`citation-management`** — find and verify *real* references; convert
  DOIs to BibTeX. Use these instead of writing citations from memory.
- **`humanizer`** — remove AI-writing tells when polishing prose.
- **`scientific-writing`** — general IMRAD scaffolding; fall back to it only for papers outside the
  OR/MS/transportation genre.

## A note on honesty

These journals are read by skeptical reviewers. The corpus papers are conspicuously honest: they
disclaim what simulations can't prove, flag assumptions as restrictive, explain negative results
instead of hiding them, and concede when a method has "mixed performance." Imitate that. Overclaiming
is the fastest way to lose a referee, and it is also the easiest thing for an LLM to do by accident.
When you are unsure whether a claim is supported, hedge it or flag it — do not inflate it.

## A note on writing alongside code

You will usually be invoked inside the user's project, with the model code, experiment scripts, config
files, and data in context. This is a trap for paper-writing: it is dangerously easy to write prose
that quietly depends on the code to make sense — referring to functions, variables, files, config
keys, data columns, or hard-coded constants as if the reader could see them. The reader cannot; they
have only the paper. Content that is unintelligible without the repository is one of the most common
and most damaging defects in machine-drafted papers. Treat the paper as a closed world: everything it
mentions must be defined inside it, in mathematical and conceptual terms, never as a pointer into the
codebase. `style-mechanics.md` gives the concrete failure modes and the translation rules; the
self-containment check in step 6 enforces it.
