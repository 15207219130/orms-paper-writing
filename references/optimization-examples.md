# Annotated Specimens: optimization papers

Worked examples for `optimization-problem-definition.md`. Everything here is a short excerpt from a
published paper in the corpus, cited by journal and year, used as a style specimen. Annotations in
**[BRACKETS]** are mine, keyed to the four slots and the build order in that file.

Slot key: **[1]** setting + decider + decision · **[2]** what makes it non-trivial · **[3]** the
problem sentence · **[4]** the objective.

---

## 1. Problem definitions, by pattern

### 1a. Minimal — paper-first, three slots, 45 words

> **[1+3]** We study the problem of managing uncertain capacities for revenue optimization over a
> network of resources. **[2]** The uncertainty could be due to (i) the need to reallocate initial
> capacities among resources or (ii) the random availability of physical capacities by the time of
> service execution. — *M&SOM 2022, transportation/fulfillment*

The shortest viable form. Slot 2 is doing all the work: it says *which* uncertainty, enumerated,
and the enumeration is what distinguishes this from generic network revenue management. No stakes,
no method, no statistic.

### 1b. Paper-first with the modeling scope as slot 2

> **[1+3]** We study the robust formulation of an inventory model with positive fixed ordering costs,
> **[2]** where the unfulfilled demand is either backlogged or lost, the lead time is allowed to be
> positive, the demand is potentially intertemporally correlated, and the information about the
> demand distribution is limited. — *M&SOM 2023, inventory*

Here slot 2 is a list of four generalizations. This works only because each one is a known hard
case in that literature — the reader recognizes "positive lead time" and "intertemporally
correlated" as things that break existing results. In a less canonical setting the same sentence
would read as attribute stacking.

### 1c. World-first, with the practice named

> **[1]** Given the variety of urgency levels in highly utilized operating rooms, capacity allocation
> decisions can have a major impact on how wait times are rationed. **[3]** We examine a longer-term
> sequential capacity planning problem in which a hospital allocates operating room time to
> different surgical specialties. **[4]** We seek to minimize an urgency-weighted wait-time metric.
> — *M&SOM 2021, inventory & capacity*

The textbook shape: condition → problem sentence → objective, in three sentences, objective last.
Note "urgency-weighted wait-time metric" — the objective is named in the decision maker's units,
not as "the objective function".

### 1d. The observed-practice opening

> **[1+3]** We consider a surgery sequencing and scheduling problem with uncertain durations of
> surgeries in the context of an operating theater. **[2]** From real data collected from a hospital,
> we observe the common practice, namely, "to follow," in which surgeries are conducted sequentially
> and immediately one after another, according to a specific schedule.
> — *M&SOM 2024, healthcare*

Slot 2 is a named practice observed in data. This is the strongest version of slot 2 available:
it tells the referee the paper is about something real, gives the benchmark for free ("to-follow"),
and implies the gap without asserting one.

### 1e. Coining a concept

> **[3]** We introduce and formalize a concept termed **conditional lead-time flexibility (CLF)**,
> **[1]** which refers to the industry practice where a manufacturer requests that its upstream
> suppliers dynamically adjust the pipeline orders' remaining lead times. Over a finite horizon, an
> assemble-to-order manufacturer makes joint decisions on inventory replenishment and lead-time
> adjustment **[4]** to minimize the total discounted expected cost. — *M&SOM 2024, supply chain*

The naming move: a practice gets a name and an acronym in the first clause, and the rest of the
paper can then refer to it. Worth doing when the practice is real and currently unnamed in the
literature — that is source (a)/(c) in the `orms-model-design` taste file.

### 1f. Question-form ending

> **[1]** Many cities worldwide are embracing electric vehicle (EV) sharing as a flexible and
> sustainable means of urban transit. **[2]** However, it remains challenging for the operators to
> charge the fleet because of limited or costly access to charging facilities. **[3+4]** In this
> paper, we focus on answering the core question — how to charge the fleet to make EV sharing viable
> and profitable. — *M&SOM 2021, sustainability*

World → trouble → question. The objective ("viable and profitable") is folded into the question
rather than stated as a minimand.

### 1g. Assumption-as-scope (limited information)

> **[2]** Traditional monopoly pricing assumes sellers have full information about consumer
> valuations. **[1+3]** We consider monopoly pricing under limited information when a seller only
> knows the mean, variance, and support of the valuation distribution. **[4]** The objective is to
> maximize expected revenue by selecting the optimal fixed price. — *M&SOM 2026, pricing*

Slot 2 comes *first* here and is stated as the assumption the literature makes. That is the
cleanest way to write a robust/DRO problem definition: name the informational assumption you are
dropping, then say what the decider actually knows.

### 1h. Method-class problem, motivated by an application

> **[1]** Multistage stochastic programs involving mixed-integer state variables and continuous local
> variables (MSILPs) present a challenging class of optimization problems with limited techniques
> available to obtain high-quality solutions efficiently. **[2]** These problems arise in many
> practical applications, including disaster relief logistics planning for natural disasters such as
> hurricanes, which is increasingly important due to its significant societal impacts.
> — *M&SOM 2026, transportation*

When the contribution is methodological, the problem *class* takes slot 1 and the application takes
slot 2 — the reverse of every other specimen here. Compare with *M&SOM 2025*: "A wide range of
decision problems can be formulated as bilevel programs with independent followers… These problems
are notoriously difficult to solve, especially when a large number of followers are present.
Motivated by a real-world cycling infrastructure planning application, we present a general approach
to solving such problems." Same shape: class → difficulty → "motivated by ⟨real application⟩".

---

## 2. Model-section openings, annotated by build step

### 2a. Setting → normalization → assumption, in two sentences

> **[SETTING]** We consider a multistore assortment planning problem where a single seller operates
> *m* stores and sells *n* substitute products to infinitesimal customers. **[NORMALIZATION +
> ASSUMPTION]** The market size is normalized to one, and we assume that a fraction λᵢ of customers
> visit store *i* ∈ {1,…,m}, where λᵢ ≥ 0 and Σλᵢ = 1. **[SETS]** We use N = {1,…,n} to denote the
> full set of products. The revenue for each product k ∈ N is denoted by rₖ. **[WLOG]** Without loss
> of generality, we assume r₁ > r₂ > … — *M&SOM 2025*

This is the measured order in miniature: prose setting (position 0.03) → assumption (0.14) → sets
and parameters (0.06/0.22). The assumption arrives *inside* the setup, not in a block afterwards.

### 2b. Primitive → constraint → the practical reason for the constraint

> **[PRIMITIVE]** Consider an electric vehicle whose state at any time *t* is characterized by the
> amount of energy y(t) stored in its battery and the instantaneous power consumption for driving
> d(t). **[CONSTRAINT]** We require that y(t) is never smaller than y̲ and never larger than ȳ.
> **[WHY]** To mitigate battery degradation, we set these limits to 20% and 80% of the nominal
> battery capacity, respectively. — *M&SOM 2024*

The third sentence is the one to copy. A bare bound is a modeling choice; a bound with its
engineering reason and a number is a modeling *argument*, and it costs eleven words.

### 2c. Roadmap opening (19% of model sections)

> **[ROADMAP]** In this section, we introduce the model that we study for the dynamic project
> expediting problem. To this end, we first provide a high-level description of the problem and
> introduce a network structure to characterize the project's activities. We then formalize the
> problem as a Markov decision process, describing its states, controls, probabilities, and costs.
> **[SETTING]** We consider a discrete-time horizon over which a decision maker is in charge of a
> project with clearly defined activities of finite time length, some sequential and others parallel,
> all of which are required for the completion of the project. — *MS 2024*

Use this when the model section has genuinely distinct sub-parts (a description, then an MDP
formalization). Note the roadmap names *what will be described* — states, controls, probabilities,
costs — which doubles as a promise the subsection headings then keep.

### 2d. Base model announced as a stepping stone, then notation conventions

> **[SCOPE]** We first consider a base model where the only decision that needs to be considered is
> product framing under inventory constraints. The base model will be used in addressing the joint
> framing and fulfillment problem in Section 5. **[NOTATION CONVENTIONS]** We will use [N] to denote
> the set {1,…,N} for any N ∈ ℕ₊, and 1 to denote a column vector of ones with a proper dimension.
> Unless otherwise noted, all vectors are to be treated as column vectors. — *M&SOM 2022*

Two useful habits: the base model is introduced *with its purpose* ("will be used in Section 5"),
and the notation conventions are stated once, up front, rather than dribbled out.

---

## 3. Assumption specimens, by move

**Precedent** — for a conventional choice, one sentence, with a citation:
> "We assume that at most one customer arrives in each period and each customer purchases at most
> one product. This is a standard assumption in the literature (see Jasin 2014)." — *M&SOM 2022*

**Practice** — the strongest and most under-used:
> "We assume that the ad agency's bid *b* for a viewer is placed on an ad exchange with a
> first-price auction, which is common in many ad exchanges today." — *M&SOM 2025*

**Scope with a forward pointer** — the highest value-per-word sentence in a model section:
> "We assume that Dₜ are independent nonnegative random variables with finite support D (in Section
> 6, we show our results hold if the demands are correlated and follow a Markov-modulated process).
> Unmet demands are lost." — *M&SOM 2022*

**Honest limitation** — when you will not relax it:
> "We assume that all nodes in eⱼ contribute equally to this threshold, though, in practice,
> contributions may be unequal. We can extend our model to this setting, but the notation and
> analysis become more complex, so we leave this to future research." — *MS 2025*

**Normalization** — a clause, not a sentence:
> "Without loss of generality, we fix the utility of the outside option to zero." — *MS 2026*

Note the pattern across all five: **the assumption and its warrant are in the same breath.** None of
them defers the justification to a later discussion, and none states an assumption bare.

---

## 4. Obstacle sentences — the bridge out of the formulation

These are the sentences that end a formulation section and license everything that follows.

> "However, it is computationally intractable when the number of products is large because of the
> curse of dimensionality." — *M&SOM 2022*

> "Observe that the operators T̃ᵢ[·] and T̂ᵢ[·] given in (5) and (9) involve the upgrade acceptance
> probability qᵢ; it is mathematically intractable to prove functional properties of these operators
> directly." — *M&SOM 2022*

> "Problem (12) is an MILP with an exponential number of constraints, as the constraint (12b) is
> enforced over Bᴶ." — *MS 2025*

> "Its adaptive nature, however, makes (P_Adapt(U)) computationally intractable." — *MS 2025*

> "Optimizing the fraction τ could be viewed as a strategy to maximize profit, but adding this level
> of complexity appears to make our formulation intractable." — *M&SOM 2025*

Two things they share. **Each names the specific cause** — the curse of dimensionality, an
exponential constraint set, an operator whose properties cannot be established, adaptivity — rather
than saying the problem is hard. And **each refers to a labelled object** — (12), (P_Adapt(U)),
(5) and (9) — which is why the naming convention in `optimization-problem-definition.md` §7 pays
off: you cannot write a crisp obstacle sentence about an unnamed formulation.

The last one is worth noting separately: it is an *honest* obstacle. The authors say they tried a
richer model and it did not work. That sentence simultaneously scopes the paper and pre-empts
"why didn't you also optimize τ?"

---

## 5. Two ways to open a solution section

**Obstacle-first** — the reader knows why the section exists before the algorithm appears:

> "In general, max-rev lacks any useful structure that can be leveraged to solve it to optimality
> efficiently. For example, the revenue function Π is, in general, not (quasi)concave in prices and
> possibly multimodal (see Figure 1…)." — *MS 2022*

> "In principle, the solution method in Theorem 1 can be used to jointly optimize the total expected
> profit for any number of different campaign types managed by an ad agency. However, this problem
> has a very large state space because the decision variables depend on all the queue lengths…"
> — *M&SOM 2025*

> "Instead of attempting to solve CAUSALIP over the complete set of edges E_c, we develop an
> iterative solution algorithm that efficiently constructs a set of candidate edges Ẽ ⊂ E_c."
> — *MS 2025*

The third is the compressed form: "Instead of ⟨the obvious approach⟩, we ⟨what we do⟩" puts the
obstacle and the answer in one sentence.

**Announcement-first** — the algorithm arrives before the reason:

> "In this section, we present our policy, called DUal Structure Algorithm (DUSA); see Algorithm 1."
> — *MS 2024*

Both are published and neither is wrong. But the obstacle-first opening does work the
announcement-first one leaves to the reader, and in a draft the announcement form is usually a
symptom that the obstacle was never written down at all. If you find yourself opening §4 with "we
now present", check that the obstacle sentence exists somewhere in §3.

---

## 6. "Key idea" sentences

The one-sentence statement of what makes the method work. Worth writing explicitly — it is the
sentence a reader repeats when describing your paper to someone else.

> "The key idea is to decompose the problem into a relaxed master problem and a series of subproblems
> indexed by i ∈ I_K." — *MS 2026*

> "The key idea in deriving these lower bounds is a cost accounting that incorporates weighted costs
> across multiple periods, allowing us to balance current and future costs to obtain tighter bounds."
> — *MS 2025*

> "A key observation here is that, to compute V^ℓ(·) for 1 ≤ ℓ ≤ L, we need to simultaneously
> optimize the revenue-ordered assortments in two groups." — *M&SOM 2024*

> "Hence, the crux of the problem is to determine the seller's expected revenue over the entire
> season under different upgrade policies." — *M&SOM 2022*

Each names a *mechanism*, not a method label. "The key idea is to use Benders decomposition" is a
method name; "the key idea is to decompose into a relaxed master problem and subproblems indexed by
i" says what is decomposed and along which index.

---

## 7. The chain, assembled

The five sentences that carry an optimization paper. This is assembled from the patterns above as an
illustration, not quoted from one paper.

```
PROBLEM        "We study the problem of ⟨gerund⟩ ⟨object⟩ under ⟨the friction⟩,
                to ⟨objective in the decider's units⟩."

FORMULATION    "⟨Problem⟩ can be written as (P): min … s.t. …"

OBSTACLE       "However, (P) has ⟨exponentially many columns / a state space that
                grows as …⟩, so it cannot be solved directly for instances of
                practical size."

KEY IDEA       "The key observation is that ⟨structural property⟩, which allows
                (P) to be decomposed along ⟨index⟩."

GUARANTEE      "This yields ⟨bound / ratio / regret rate / policy form⟩, which we
                show is tight / achieves X% of the optimum on real instances."
```

Test for a draft: can you find all five sentences, in order, each referring to a named object? If
the obstacle sentence is missing, the solution section has no motivation. If the key-idea sentence
is missing, the algorithm looks like engineering. If the guarantee sentence is missing, the paper is
a computational study rather than a methodological contribution — which is fine, but it changes
which journal it fits (see `journal-profiles.md`).
