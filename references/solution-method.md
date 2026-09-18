# Solution / Algorithm / Structural Analysis

This is the section that most often reads as a wall of theorems to outsiders and as elegant to
insiders — the difference is almost entirely *connective writing*. The corpus papers keep
proof-dense material readable through a small set of habits: name the obstacle that motivates the
work, give a roadmap before the lemma chain, put intuition next to every formal result, refer back to
the model by number, and control redundancy. The user specifically cares about **correspondence with
the model** and **readability** — both live here.

## Open by naming the obstacle in the model

The solution section should begin by pointing at the *specific* thing in the model that makes the
problem hard, referencing the model's own equations. This both motivates the section and creates the
correspondence the user wants:

> "The main challenge in solving Problem (6) arises from the nonlinear integer constraint … [which]
> contains fractional terms involving exponential functions. Unlike existing choice-based
> optimization models … our setting introduces both a general functional form φ(n) and an additional
> fractional component, thereby creating … substantial computational challenges." — *Zhang et al.
> (shared mobility)*

Naming the obstacle (by equation number) tells the reader exactly what the machinery that follows is
*for*.

## Give a roadmap of the section, then a roadmap of each proof

Two levels of signposting keep a reader oriented in dense material.

**Section roadmap** — one sentence laying out the plan:

> "we first identify special cases for which an MILP reformulation is available, then propose MIECP
> formulations …, and finally develop a cutting-plane method and a provably good second-order cone
> (SOC) approximation." — *Zhang et al.*

**Proof roadmap** — before a non-trivial proof, list the steps:

> "To prove its competitive ratio, we follow these steps. First, we show that if p* is the optimal
> dual solution …, then {xₜ(p*)} is close to the primal optimal solution x*. … We then show that p̂
> is a good substitute for p*: (1) with high probability …; (2) the expected value … is close to the
> optimal offline value." — *Agrawal, Wang & Ye*

> "We complete the proof in three steps: Step 1. … Step 2. … Step 3. …" — *Li & Ye*

A reader who knows the shape of the argument can follow (or skip) the algebra without getting lost.

## Put intuition next to every formal result

The signature rhythm is **formal statement → immediate plain-language restatement / interpretation →
(worked illustration).** Intuition can come just before or just after the theorem, but it must be
adjacent. Devices the corpus uses:

- **Restate the theorem in words:** "Proposition 1 says that an optimal policy for accepting requests
  is of the form: accept fare rʲ … if and only if … This reflects the rather intuitive notion that
  we accept a fare … only when it exceeds the opportunity cost …"
- **"Intuitively, …" gloss** on a hard object: "Intuitively, the optimal dual prices π provide an
  estimate of the marginal value of capacity on each leg …"; "Intuitively, the lemma can be viewed as
  a second-order Taylor expansion …"
- **"This characterization is significant for several reasons. First, … Moreover, …"** — an
  interpretive paragraph after a main theorem, spelling out why it matters.
- **"Implications of Theorem 1 are two-fold."** — state the takeaway *before* the reader has to infer
  it.
- **Cross-field analogy** for a definition: "an efficient set is a point on the 'efficient frontier'
  … a concept that should be natural to those readers familiar with mean-variance portfolio theory or
  data envelopment analysis (DEA)."
- **Walk the result through the running example:** "applying Theorem 1 to Example 1, we see that the
  efficient sets S₁ = {Y}, S₂ = {Y, K} … would be used as follows …"

A theorem with no surrounding intuition is the most common readability failure in drafts; fix it by
adding the restatement-and-meaning sentence.

## The result-chain rhythm: don't drop theorems cold

A section can be *formally complete* — Definition, Lemma, Proposition, Proof, repeated — and still read
as a wall, because the formal **blocks** are present but the **argument that connects them** is not.
This is a failure mode distinct from missing rigor, and it is the easy over-correction when a draft
that was too prose-heavy gets fixed: you add the propositions and proofs, then leave them stacked with
no connective tissue, and a reader sees correct mathematics with no thread. (Both extremes are wrong —
a model/analysis section is neither a wall of symbols nor a chain of naked theorem blocks; the target
is formal results *threaded by argument*.) The corpus never stacks results cold; every formal result
sits inside a four-beat rhythm, and the beat most often missing in drafts is the last one.

1. **Lead-in — what the result is for.** One sentence *before* the statement naming the question it
   answers or the obstacle it clears, so the reader knows why it is coming. *"The following result
   shows that the mean battery deficit increases linearly in [the lead time]. In other words, reducing
   [it] has a constant marginal effect …"* — Qi, Zhang & Zhang (2023, Mgmt Sci), introducing a result.
2. **Statement.** The Lemma / Proposition / Theorem itself.
3. **In-words restatement — what it says and why it matters.** Immediately after: *"Lemma 1 shows that
   Var(QX) exceeds Var(Z) by a margin … The insight here is that consolidating orders into batches of
   Q > 1 creates extra operational uncertainty …"* — same paper. Use "In words, Proposition X says …",
   "The insight is …", or "Implications are two-fold …".
4. **Transition — why this is not yet enough, or what it now enables.** A sentence that hands off to the
   next result by naming the gap it leaves or the door it opens: *"However, the expression in Lemma 1
   is inconvenient for further analysis because [these moments admit no closed form] …"* — which
   motivates the next lemma. **This beat is what turns a list of results into a chain, and it is the one
   most often absent.**

The same rhythm scales up to the whole section: open by naming the obstacle, then let the lead-ins and
transitions carry one narrative arc through the entire chain — *primitives needed → formulation made
exact → structure characterized → structure exploited by the algorithm* — so a reader can follow the
*story* while skimming the proofs. A blunt test: if you can delete a result and the surrounding prose
still flows unbroken, that result was dropped cold; the lead-in and transition should make each one
read as load-bearing.

## Ordering of formal results

The standard chain is **Definition → Lemma → Proposition → Theorem → Corollary**, sequenced so each
result feeds the next, and introduced by *what it accomplishes* rather than dropped in cold:

> "We start with Lemma 2, which shows that with high probability, the primal solution xₜ(p̂) … is
> feasible." — *Agrawal, Wang & Ye*

When a main bound or structural result is reused, **prove a 'master' result once and instantiate it**
("The upper bound consists of three components: (i) … (ii) … (iii) …", then applied to each
algorithm). This avoids re-deriving and keeps the section short. Use **explicit redundancy control**
when proofs repeat: "The proof of Lemma 7 is exactly the same as the proof for Lemma 4; thus, we omit
its proof"; "The proof follows mostly the proof of Theorem 1 … We only highlight the difference
here."

Negative results are stated forthrightly and their significance explained: "Our main result here is a
negative one. Namely, we demonstrate that … the sample path profit function is not quasiconcave …
The significance of this result is that …".

## Presenting algorithms

- Give the **idea in prose before the pseudocode float**: "This algorithm, which we term Independent
  Randomized Rounding, samples an assortment for each firm independently … without any sequential
  capacity checks." Then the numbered `Algorithm` block.
- **Name the algorithm** and refer to it as an object thereafter (OLA, DLA, GPA, Bisection Search).
- **Derive the key step right after the block** when it is non-obvious: "The key of the algorithm is
  the updating formula for pₜ … the subgradient of the t-th term … is … The dual updating rule indeed
  implements stochastic subgradient descent in the dual space."
- **Present a simple version before the strong one** — an *algorithm ladder*. "To keep the discussion
  clear and easy to follow, we start in §2 with a simpler one-time learning algorithm" — the simple
  version teaches the proof technique before the harder one reuses it. Each rung is justified against
  the previous ("The key difference between this simplified algorithm and the dynamic learning
  algorithm in … is that we get rid of the shrinkage term").

## Maintain correspondence with the model

This is a top user priority. The solution section must continually point back to the model:

- Refer to model objects **by their number/label** — "Problem (6)", "constraint (7)", "Assumption 2",
  "the feasible set 𝓕" — not by vague paraphrase. This is what lets a reviewer check the work.
- When you reformulate, say what maps to what: "Theorem 2. The nonlinear integer constraint (7) is
  equivalent to the following mixed-integer exponential constraints …".
- Tie new quantities back to familiar ones from the model or the field: "this approximation
  effectively … replac[es] each product revenue rⱼ by the pseudorevenue … This is precisely how DAVN
  and DP approximations are formed in traditional RM."

If a draft's solution section introduces objects that don't trace back to the model, that is a
coherence defect — see `citations-and-coherence.md` for the model↔solution check.

## Proof placement

Match the venue. Short, illuminating proofs can sit inline; long or technical proofs go to an
appendix or electronic companion with a pointer ("All proofs are relegated to the appendix"), often
leaving a **prose sketch** in the body: "The proof of Proposition 2, included in the Appendix, is
rather involved, and we provide a brief sketch here. We first consider the dual of …". The main text
should remain readable end-to-end without the appendix.

## Per-journal notes

- **Operations Research / Mathematical Programming:** the technical core is the contribution; full
  rigor expected, but keep the main text navigable via roadmaps, intuition, and appendixed proofs.
- **Management Science:** lead with the structural insight and its meaning; a reader should grasp
  *what the optimal policy looks like and why* even if they skip the proofs.
- **Transportation Science / M&SOM / application papers:** intuition and the link back to the
  operational problem matter as much as the math; algorithms are often the centerpiece, so present
  them especially clearly.

## Self-check

- Does the section open by naming the model-specific obstacle (by equation number)?
- Is there a section roadmap, and a step roadmap before each non-trivial proof?
- Does every theorem/proposition have adjacent intuition (restatement, "implications", analogy, or
  worked example)?
- Does each formal result carry a **lead-in** (what it is for) and a **transition** (what it enables or
  why it is not yet enough), so the results form a chain rather than a cold stack of blocks? (the
  transition is the beat most often missing)
- Are model objects referenced by number, so correspondence is auditable?
- Are algorithms named, motivated in prose, and (where helpful) laddered simple→strong?
- Is redundancy controlled ("similar to …, omitted") and are long proofs cleanly deferred?
- Is the *certif-* family (certificate/certified/certify) avoided? It reads as non-OR register even
  in exact-algorithm sections; use *prove … optimal*, *optimality guarantee*, *valid bound*,
  *guaranteed gap* instead (see `style-mechanics.md`).
