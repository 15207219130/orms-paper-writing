# Model / Formulation

The model section converts a real problem into mathematics that the rest of the paper can reason
about. The corpus papers share a strong discipline here: **prose before symbols, every object
motivated before it is used, every assumption justified, and a structure clean enough that the
solution section can later point back to specific equations by number.** A reader should be able to
follow the *story* of the model even while skimming the equations.

## The cardinal rule: verbal setup before math

Never open with a display equation. Open with a plain-language description of the setting — "Consider
…", "We consider the following setting that is common in …" — and only then introduce notation and
formulas.

> "We consider the following general setting that is common in many last-mile delivery service
> systems. A service provider operates in the depot x₀ of a service region ℛ, which is a compact and
> convex Euclidean plane." — *Carlsson et al.*

> "We begin by formulating a general statement of the network RM problem under customer choice
> behavior. The network has m legs and provides n products (a product is defined by an itinerary and
> fare class combination)." — *Liu & van Ryzin*

This grounds the math in the problem and lets a reader build intuition before being asked to parse
symbols.

## Establish notation conventions up front

A short conventions paragraph before the model proper saves the reader from constant confusion. The
corpus states things like the direction of time, vector/scalar typography, and reusable symbols
explicitly:

> "We use superscripts to denote components of a vector and subscripts to denote time. … Time is
> counted backwards …" — *Talluri & van Ryzin 1998*

> "Throughout this paper, we use bold symbols to denote vectors/matrices and normal symbols for
> scalars." — *Li & Ye 2021*

For notation-heavy papers, a dedicated **"Notation" subsection** (sometimes a bulleted symbol
glossary, or a notation table) is welcome. The aim is that any symbol the reader meets later has been
introduced once, in an obvious place.

## Order of presentation

The reliable order is **sets / primitives → parameters → decision variables → objective →
constraints**, each introduced in prose as it appears:

> "Consider I potential hubs (indexed by i ∈ [I]), K commodities (indexed by k ∈ [K]), and a
> planning horizon with T periods (indexed by t ∈ [T]). Let uₖₜ be the demand of commodity k at
> period t …" — *Hu, Chen & Wang*

After the formulation block is displayed, **walk through the non-obvious constraints one at a time**:

> "The objective function (menuOPT) maximizes the total expected profit … Constraint (1) enforces the
> firm-specific menu size requirements. Constraint (2) ensures that the total expected demand for
> each restaurant j … does not exceed its capacity cⱼ." — *Lagzi et al.*

This constraint-by-constraint gloss is what makes a formulation readable rather than a wall of
symbols, and it is exactly where many drafts fall short.

## State assumptions — and justify every one

Assumptions are never bare in the corpus. Each is stated and then immediately justified, typically in
one of three ways: tied to the application, defended as standard, or flagged as a tractability
simplification with a note on relaxation.

> "While it is simplest to imagine that each origin-destination itinerary requires only one unit of
> capacity …, we do not impose this restriction. Indeed, the model can accommodate group requests
> (e.g. a family booking four seats together)." — *Talluri & van Ryzin 1998* (assumption motivated
> by a concrete example)

> "While it is not difficult to allow these arrival probabilities to depend on time t, to simplify
> the exposition we assume the arrival probability is constant over time." — *Liu & van Ryzin*
> (tractability simplification + costless-relaxation note)

> "Assumption 2 (a) is mild in that the matrix E[aaᵀ] is positive semi-definite by definition; the
> positive definiteness holds as long as the constraint matrix A … has full row rank, which is a
> typical assumption for solving linear programs." — *Li & Ye 2021* (defended as standard)

Three reusable justification moves:
- **Tie to the application:** "In a grocery delivery context (e.g., Whole Foods), the on-site service
  time represents the time to handover the grocery basket …"
- **"For tractability, we focus on…"** then a forward pointer to where it is validated ("we use this
  linear approximation for tractability and validate its reasonableness in Section 5").
- **Scope what is deliberately excluded:** "The only real limitation is that we assume choices are
  only a function of the set S of open fares … In particular, we do not model … strategic behavior …
  or history-dependent choice behavior." Honest scoping pre-empts a reviewer's objection.

If the user gives you an assumption with no justification, do not invent a false one — ask them why
it holds, or flag it as "needs justification" in your report.

## Readability devices the corpus relies on

- **A running example, introduced early and reused throughout.** Several corpus papers ("Running
  Example. An airline network consists of three cities and three flights …") thread one concrete
  instance through the model, the solution, and sometimes the experiments. It makes abstract
  quantities tangible and is worth proposing to the user.
- **Italicize key constructs on first definition** (*fully flexible delivery system*, *efficient
  set*), then use the term consistently — never introduce a synonym later.
- **Name and label sub-problems** with brackets or short tags ([PSP], [DSP], menuOPT, BDO) and refer
  to them as objects thereafter. This pays off enormously in the solution section.
- **Solve a simpler special case first.** A powerful pedagogical move: present a deterministic or
  one-dimensional version, build intuition, then generalize ("Let us start by looking at a simpler
  version of the problem, where the price is changing at a constant rate and there is no volatility
  …"). The classical-method recap ("We begin with a brief outline of the classical BD algorithm")
  serves the same purpose for method papers.
- **Attribute borrowed results in the statement itself** — "Theorem 2 (Bertsimas and Van Ryzin
  1993b)", "Theorem 1 (Sakasegawa 1977)" — so the reader knows instantly what is yours and what is
  inherited.

## Prose-to-math balance and length

These sections are **prose-heavy**: equations are punctuation within an argument, not the argument
itself. Every display should be introduced by a clause ("To be precise, we consider the following
linear program:") and, if not self-evident, interpreted after. A formulation section that is mostly
symbols with little connective prose reads as unfinished by top-journal standards.

Length is governed by what the solution section needs, not by a fixed target. Include exactly the
objects later sections reference, and push purely technical preliminaries (measure-theoretic
caveats, regularity conditions used only in proofs) to where they are needed or to an appendix. A
model can also be **built up in layered subsections** ("User Choice Model" → "Embedded Queueing
Network" → "Optimization") when that staging aids comprehension.

## A model-justification proposition (optional but strong)

When a modeling choice is itself a contribution (e.g. a functional form chosen to capture a named
real-world effect), the corpus sometimes uses a small proposition or worked derivation to show the
model *can represent the intended phenomena* — e.g. demonstrating the utility function captures both
"agglomeration" and "cannibalization" effects. This pre-empts "why this form?" objections.

## Per-journal notes

- **Operations Research / Math Programming:** generality and rigor are valued; state the model at its
  natural level of generality and be explicit about the assumption set. Notation discipline matters.
- **Management Science:** keep the managerial meaning of variables and constraints visible; a reader
  should see the decision being made, not just the symbols.
- **Transportation Science / M&SOM / application papers:** anchor the model in the real system,
  justify stylizations ("the circular city setup is widely utilized …, we adopt a variation"), and
  cite precedent for modeling choices.

## Self-check

- Does prose introduce every object before its symbol appears?
- Are notation conventions stated once, up front?
- Is every assumption justified (application / standard / tractability-with-relaxation), and is
  excluded scope stated honestly?
- Are constraints walked through after the block?
- Are sub-problems named/labeled so the solution section can refer back by number? (→ `solution-method.md`, `citations-and-coherence.md`)
- Is the math surrounded by enough connective prose to read as an argument?
