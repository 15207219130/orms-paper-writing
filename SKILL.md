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
| Which journal? MS vs OR vs Transportation Science vs M&SOM differences | `references/journal-profiles.md` |

If the user is writing a whole paper or asks about overall structure, skim all of them; the section
references are short. The two cross-cutting references (`citations-and-coherence.md`,
`style-mechanics.md`) apply to *every* section and encode the user's top priorities (citation
correctness and cross-section correspondence), so do not skip them.

## Core workflow

1. **Clarify the job.** Confirm: target journal (or "top OR/MS, unspecified"), which section(s),
   whether this is draft / revise / critique, and what raw material exists (model equations, a
   contributions list, results tables, an existing draft, a `.bib`). If the target journal matters
   for framing and the user hasn't said, ask or state the assumption — `journal-profiles.md`
   explains why MS vs OR vs TS changes the framing.

2. **Read the relevant reference(s)** from the routing table, plus `style-mechanics.md`.

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

7. **Report back in the user's language**: what you wrote/changed and why, the citation checklist
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
