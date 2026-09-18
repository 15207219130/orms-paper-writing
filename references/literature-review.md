# Literature Review / Related Work

The literature review does one job above all: **establish the gap your paper fills, precisely enough
that the gap and your contributions are mirror images of each other.** A reviewer reading it should
finish thinking "yes, nobody has done exactly this, and this paper says it will." It is not a
survey for its own sake — every cited work is there because it helps locate your contribution.

Read this together with `citations-and-coherence.md`, which covers citation *correctness* (never
fabricate; verify each claim-about-a-paper with `research-lookup`) and the gap↔contribution mapping
check.

## Placement: separate section vs. folded into the introduction

This is **genre- and journal-dependent**, and both are correct — match the target:

- **Folded into the introduction** (classic *Operations Research* theory papers, and shorter
  papers). The review is a narrative paragraph or two inside the intro, with author-prominent
  citations, ending in the "we depart by…" positioning. Examples in the corpus: Talluri & van Ryzin
  1998 ("Related Literature" as a labeled subsection of the intro), Mahajan & van Ryzin, Hosseini &
  Turner.
- **A separate numbered section** "2. Literature Review" / "2. Related Work" (common in newer
  manuscripts, application papers, and many *Management Science* / M&SOM / Transportation Science
  submissions). Examples: the meal-delivery, shared-mobility, hub-location, and dispatching papers.
- **The body itself** (survey papers only) — organized as a taxonomy with a classification table and
  a critique paragraph per surveyed work.

When unsure, a separate section is the safer default for a substantial modern submission; fold it in
only if the paper is short or very theory-forward. Ask the user if it matters.

## Organize by research stream, and announce the streams

The dominant structure is **two to four named streams**, announced in a single opening sentence, then
taken in turn (often as numbered subsections):

> "We review three streams of related literature: region partitioning in logistics, stochastic and
> dynamic vehicle routing, and on-time delivery operations." — *Carlsson et al.*

> "We review major streams of related literature: location planning under uncertainty, multi-stage
> robust optimization, residual-based DRO approach, and distribution-free stochastic process. We
> also discuss the research gap between our work and the most relevant existing studies." —
> *Hu, Chen & Wang*

Streams are usually organized by **problem class or methodology**, occasionally chronologically
within a stream to show a lineage ("dates back to Rothstein (1971) … Littlewood (1972) … Belobaba
(1987) …"). Each stream should build toward *your* corner of the field — order them so the last
stream is the closest to your work.

## Close every stream with an explicit positioning sentence

This is the most important mechanical habit. After summarizing a stream, state in one or two
sentences what that work does *not* do that your paper does. The corpus does this relentlessly, with
a recognizable set of templates:

- **Closest-work contrast:** "The closest to our setting … is Boada-Collado and Martínez-de Albéniz
  (2020) … However, unlike their multi-product retail problem, the inventory levels across stations
  … are connected through network flows, which requires distinct formulations and solution
  techniques."
- **Credit-then-critique-then-claim** (a clean three-beat): "Simpson and Williamson's work had a
  significant impact on the practice of revenue management. However, they do not provide a rigorous
  analysis … Our work puts this important practical development on a sound theoretical footing."
- **Single-axis differentiation:** isolate the *one* dimension on which you differ — "Our paper
  differs from the existing OLP literature in the right-hand-side assumption, i.e., the constraint
  capacity." Single-axis claims are sharp and easy for a reviewer to accept.
- **Enumerated differences** when there are several: "However, there are a few major differences.
  First, the customers … do not arrive sequentially … Second, … do not consume a single unit … Third,
  since delivery costs are not uniform …"
- **First-of-its-kind:** "To the best of our knowledge, this is the first result that shows the
  necessity of dependence on the dimension m …" Use sparingly and only when you have actually
  checked (verify via `research-lookup`).

Avoid the failure mode of a "bibliography in prose" — a list of who-did-what with no positioning. If
a cited paper does not help locate your gap, it probably belongs in a parenthetical cluster, not a
sentence of its own.

## Weaving citations: narrative vs. parenthetical

Two registers, used deliberately (this is the INFORMS author-date house style):

- **Narrative / author-prominent** — "Kabra et al. (2020) analyze …", "Mahajan and van Ryzin (2001)
  show …". Use this for the works that **carry your argument**: the closest prior work, the result
  you build on, the paper you are contrasting against. The author becomes the grammatical subject,
  which foregrounds *what they did*.
- **Parenthetical clusters** — "(Kleinberg 2005, Arlotto and Gurvich 2019, Bray 2019)". Use this for
  **breadth of support** — establishing that a stream exists or that a claim is widely held — without
  dwelling on any single paper. Also the "(See X for a survey/overview)" pointer for handing the
  reader off.

A good review alternates: parenthetical clusters to sketch the landscape, narrative citations to
zoom in on the works that matter for positioning.

## Honesty and tone

- A **"selective review" disclaimer** is acceptable and common when a field is large: "Here, we
  provide a selective literature review highlighting key relevant studies, while a comprehensive
  overview can be found in Heger and Klein (2024)."
- Give genuine credit before critiquing. "While quite innovative and intuitively appealing, … the
  deterministic mathematical programming models … are clearly oversimplified" reads as fair; a flat
  dismissal reads as arrogant and invites a hostile referee.
- Do not manufacture a gap that isn't there, and do not claim "first" without checking. If the user
  hasn't supplied the prior work, find it with `research-lookup` rather than inventing plausible-
  sounding citations.

## Per-journal notes

- **Management Science:** the gap should connect to a *managerial / decision-relevant* question, not
  only a technical one. Position against both the methodological stream and the application stream.
- **Operations Research / Mathematical Programming:** technical positioning dominates — what model
  class, what assumptions, what solution guarantee distinguishes you. Folding the review into the
  intro is common and accepted.
- **Transportation Science / M&SOM:** balance application-stream and method-stream; reviewers expect
  to see both the domain literature and the OR-methods literature represented.

See `journal-profiles.md` for more.

## Self-check

- Are the streams announced up front and ordered toward your contribution?
- Does each stream end with an explicit "they do A, we do B" sentence?
- Does the union of gaps equal the set of contributions claimed in the intro? (→ `citations-and-coherence.md`)
- Is every citation real and correctly attributed? Is every "first to" claim actually checked?
- Narrative citations for the load-bearing works, parenthetical clusters for breadth?
