# Citation Integrity & Cross-Section Coherence

This reference encodes the two things the user emphasized most: **citations must be correct**, and
**the introduction/literature review must correspond to the rest of the paper** (and the solution
must correspond to the model). Apply it on essentially every writing or revision task — these are
integrity checks, not optional polish. They are also the two places where an LLM most easily goes
wrong: inventing plausible-but-fake references, and writing sections that drift out of agreement with
each other.

---

## Part 1 — Citation integrity

### The hard rule: never fabricate

Do not invent a reference, an author list, a year, a venue, a title, a DOI, or a claim about what a
paper says. A fabricated citation that a reviewer catches can sink a submission and damage the
author's credibility. This is the single most important constraint in the skill.

It is **always acceptable** to say "this needs a citation" and leave a flagged placeholder. It is
**never acceptable** to write `(Smith and Jones 2018)` for a paper you have not verified exists and
actually supports the sentence.

### Workflow: find and verify real references online

The user's chosen approach is online retrieval. When the draft needs to cite prior work:

1. **Find real papers** with the `research-lookup` skill (or `citation-management` for Google
   Scholar / BibTeX). Search for the specific claim or topic, not a guessed author name.
2. **Verify the claim↔source link.** A citation must support the *specific sentence* it is attached
   to. Confirm that the paper you found actually says what your sentence attributes to it — not just
   that it is on a related topic. Mis-attribution (citing a real paper for a claim it doesn't make)
   is as damaging as a fake citation.
3. **Capture correct metadata** — authors, year, exact title, venue — and, where the user wants
   BibTeX, generate it with `citation-management` from a DOI rather than by hand.
4. **Match the author's existing citation style** (author-date is the INFORMS norm: "Smith (2010)
   shows…" / "(Smith 2010)"). If the user has a `.bib`, reuse its keys; don't introduce a parallel
   scheme.

### When you cannot verify

If retrieval is unavailable, the claim is too specific to confirm, or the user hasn't supplied
sources, **do not guess**. Insert a clearly marked placeholder (`\cite{TODO: ...}` or
`[CITATION NEEDED: claim about X]`) and add the item to the verification checklist you return to the
user. Distinguish three states explicitly in your report:

- **Verified** — real paper found and confirmed to support the sentence.
- **Needs check** — a candidate exists but you could not confirm it supports the exact claim.
- **Unsupported** — the sentence asserts something you found no source for; consider softening or
  cutting it.

### The "claims to verify" checklist

End any task that touched citations with a short checklist the user can act on, e.g.:

```
Citations — status
✔ Verified:  (Talluri & van Ryzin 1998) supports the bid-price suboptimality claim — Mgmt Sci 44(11).
⚠ Needs check: the "first to combine MNL + queueing" novelty claim — searched, found nothing
   contradicting it, but please confirm before asserting "first".
✗ Unsupported: "delivery delays cost the industry $X annually" — no source located; I softened
   it to a qualitative statement. Provide a source or we cut the figure.
```

Be especially careful with **"to the best of our knowledge, we are the first to…"** claims: only keep
them if a genuine search turned up nothing prior, and tell the user you checked.

---

## Part 2 — Cross-section coherence

A top-journal paper is internally consistent: its promises and deliveries line up. Run these checks
whenever you write or revise more than a single isolated paragraph. They directly serve the user's
concern about "introduction/literature-review narrative logic and its correspondence with the rest of
the paper."

### Check 1 — Gap ↔ contributions

Every gap claimed in the literature review should be answered by a contribution, and every
contribution should close a stated gap. Build the mapping explicitly:

- For each "prior work does A but not B" in the lit review, find the contribution that provides B.
- For each contribution in the intro, find the gap it fills. A contribution with no corresponding
  gap is either under-motivated (add the gap) or not actually novel (reconsider the claim).

### Check 2 — Contributions ↔ sections (the promise-and-delivery map)

Every contribution promised in the abstract/introduction must be **delivered by an identifiable later
section**, and ideally the intro points there. Construct the table:

| Contribution (as stated in intro) | Delivered in | Pointer present? |
|---|---|---|
| "we characterize the optimal policy structure" | §3 (Thm 1) | "we prove Theorem 1 in §3" ✔ |
| "a decomposition heuristic that improves on the static LP" | §5 algorithm + §7 experiments | ✔ |
| "more than 4% profit improvement on real data" | §6 case study | missing pointer — add |

If a contribution has no home, either the section is missing (flag it) or the contribution is
overclaimed (flag it). If a major result appears in the body but was never promised in the intro, the
intro is underselling — surface it.

### Check 3 — Model ↔ solution correspondence

The solution section must refer back to the model's actual objects, by number. Verify:

- Every reformulation/algorithm targets a named model object — "Problem (6)", "constraint (7)",
  "Assumption 2" — not a vague paraphrase.
- Symbols and named sub-problems ([DSP], 𝓕, BDO) are used consistently with their model definitions;
  no symbol is reused with a different meaning, and no new object appears without tracing to the
  model.
- Claims in the solution don't rely on assumptions the model didn't state (or that were excluded).

### Check 4 — Experiments ↔ introduction's questions

The numerical section should answer the questions the introduction raised and substantiate the
contributions that are empirical. If the intro promised a 4% improvement or "scales to real-size
networks," the experiments must show it; if the experiments reveal something important, the intro and
abstract should mention it.

### Check 5 — Forward/backward references resolve

- Forward references ("in §5 we…") point to a section that exists and actually does that.
- Backward references ("by Proposition 1") point to the right, existing result.
- Section/equation/theorem numbers referenced in prose are consistent (a frequent breakage after
  edits).
- Terminology is stable end-to-end — the named concept from the abstract ("efficient sets," "deepest
  cuts") is used identically everywhere; no silent synonyms.

### Check 6 — Self-containment (no dependence on the code)

Because you are usually drafting inside the user's repository with the implementation in context, audit
that nothing in the paper depends on the code to be understood — the journal reader has only the PDF.
Scan for and translate any leak:

- No code identifiers (function/class/variable names), file or script names, paths, config keys, or
  library calls in the prose. (Defined mathematical symbols are fine; code variable names are not.)
- Every numerical constant traces to a parameter, value, or instance *defined in the paper* with units
  and rationale — no magic numbers copied from source.
- Algorithms are presented as method/pseudocode over defined symbols, not as transcriptions of loops
  and data structures.
- Every reported result rests on an experimental setup described in the paper (the code is a supplement
  in the online companion, never a prerequisite).

This is the same principle as `style-mechanics.md`'s self-containment section, applied as a final
integrity sweep. Anything that fails the "readable from the PDF alone?" test is rewritten or flagged.

### Reporting coherence findings

When you find a gap, report it concretely to the user in their language: which contribution lacks a
home, which citation is unverified, which solution object doesn't trace to the model. Offer the fix
(add a pointer, soften a claim, add a section) rather than only naming the problem.

---

## Quick combined checklist

- [ ] No fabricated references; every citation verified to exist **and** to support its sentence.
- [ ] "First to…" claims actually checked; unverifiable claims flagged, not asserted.
- [ ] Citation checklist (verified / needs-check / unsupported) returned to the user.
- [ ] Each gap ↔ a contribution; each contribution ↔ a gap.
- [ ] Each contribution ↔ a delivering section, with a pointer.
- [ ] Solution refers to model objects by number; symbols/assumptions consistent.
- [ ] Experiments answer the intro's questions and back the empirical contributions.
- [ ] All forward/backward references and numbers resolve; terminology stable throughout.
- [ ] Self-contained: no code identifiers / file names / config keys / untraced constants; every
  symbol, value, instance, and algorithm step is defined in the paper and readable from the PDF alone.
