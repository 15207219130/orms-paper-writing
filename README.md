# orms-paper-writing

A Claude skill for writing, drafting, revising, and polishing manuscripts for top
operations-research / management-science / transportation journals (Operations Research,
Management Science, M&SOM, Transportation Science, POMS, and other INFORMS journals).

The conventions encoded here come from two sources. The section references are distilled from a
corpus of flagship papers spanning revenue management, online optimization, transportation &
logistics, assortment, inventory, location, and ML-for-optimization — with real exemplars quoted
throughout. On top of that, `references/journal-benchmarks.md` and `references/phrase-bank.md`
carry **measured** norms from full-text analysis of 2,322 articles in *Operations Research*,
*Management Science* and *M&SOM* (~70% published 2022–2026): lengths, section architecture, word
budgets, abstract formats, and how often each rhetorical move actually appears in print. The four
`logic-*.md` references go further and reconstruct the **argument chain** of each section — the
order the moves run in, the adjacency rules between them, and the measured practice around
assumptions, benchmarks, result ladders and experiment design — each with a worked
positive/negative contrast. See `CORPUS-NOTES.md` for the method and its limits.

## Contents

```
SKILL.md                              # skill entry point: triggers, workflow, house style
CORPUS-NOTES.md                       # how the measured norms were produced, and their limits
references/
  introduction.md                     # intro & contributions structure
  literature-review.md                # positioning and the "gap" move
  model-formulation.md                # notation, assumptions, formulation conventions
  solution-method.md                  # algorithm sections, theory, proofs
  numerical-experiments.md            # computational study design and reporting
  optimization-problem-definition.md  # house style for optimization papers: the problem
                                      #   definition, model-section build order, assumption
                                      #   prose, formulation naming, the narrative spine
  citations-and-coherence.md          # citation style, cross-section consistency
  journal-profiles.md                 # per-journal expectations; converting between venues
  journal-benchmarks.md               # measured length / structure / abstract norms
  phrase-bank.md                      # rhetorical moves, with frequencies and exemplars
  style-mechanics.md                  # sentence-level mechanics
  logic-introduction.md               # the argument chain of an introduction, and its order
  logic-literature-review.md          # what a review proves; stream-internal logic
  logic-methodology.md                # what a model/analysis section must establish, by paper type
  logic-numerical-design.md           # designing experiments: the ladder, parameter credibility
evals/
  evals.json                          # eval suite for the skill
  inputs/                             # sample inputs used by the evals
```

## Usage

Place the folder in your Claude skills directory (e.g. `~/.claude/skills/orms-paper-writing`)
and Claude will load it when you ask for help with an OR/MS paper or any of its sections.
Requests in English and Chinese both trigger it.

## License

MIT
