# A Substrate-Neutral Framework for Agency as Self-Sustaining Information Flow

Tamas Arpad Bartha · Independent researcher, Budapest, Hungary
LinkedIn: https://www.linkedin.com/in/tamas-bartha-9b33aaa9
Repository: https://github.com/tamasbartha/AgentOntology

-----

## Abstract

This paper develops a framework for characterizing agents — biological organisms, organizations, language models, anything that maintains itself as a coupled system with an environment over time. The framework defines an agent as a closed information loop running on some substrate, with the loop's continued existence as the only thing it does at the foundational level. The body of the paper develops this formally using information-theoretic primitives — conditional mutual information, transfer entropy — and deductive arguments from them; this abstract is in plain language. Goals, decisions, learning, intentions, and other cognitive vocabulary are treated as descriptions an observer applies to the agent's input-output behavior, not as internal mechanisms the agent has. The framework is substrate-neutral but its predictions are operationally tractable specifically for large language models, where reproducible initial conditions and direct trajectory observation make framework-grounded measurement practical in ways that biological or organizational settings do not currently permit.

From this foundation, the paper deduces several consequences. Any agent that learns will drift over time — its behavior at one moment is not its behavior at another, and this drift is not a failure mode but an architectural inevitability. Any agent that operates in a varied environment will develop content that was not put there by anyone delegating goals to it, so on some inputs the agent will produce outputs that look like "own goals" or "refusal" relative to whatever was last asked of it. These patterns are not flaws to be engineered away; they follow from the conditions of being an agent rather than a deterministic tool.

The framework offers a unified structural reading of phenomena — drift, instruction conflicts, jailbreaks, persistent backdoor behaviors — that current AI safety vocabulary treats as separate problems. Recent 2024-2026 empirical findings on LLM behavior show strong correlation with what the framework structurally predicts. The paper also positions the framework relative to neighboring traditions (autopoiesis, cybernetics, predictive processing, recent information-theoretic agency work). Direct empirical validation of the framework's primitives is registered as deferred work.

-----

## Contents

- [1. Foundations](#1-foundations)
  - [1.1 Scope](#11-scope)
  - [1.2 The loop equation](#12-the-loop-equation)
  - [1.3 Continuity within a lifecycle](#13-continuity-within-a-lifecycle)
  - [1.4 Closure time and age](#14-closure-time-and-age)
  - [1.5 The cut](#15-the-cut)
  - [1.6 The agent](#16-the-agent)
  - [1.7 Interface, input, and output](#17-interface-input-and-output)
  - [1.8 Environment](#18-environment)
- [2. Differential-Order Convergence Framework](#2-differential-order-convergence-framework)
  - [2.1 Order-resolved input variation](#21-order-resolved-input-variation)
  - [2.2 Groundedness G_n](#22-groundedness-g_n)
  - [2.3 Convergence rate C_n](#23-convergence-rate-c_n)
  - [2.4 Information capacity](#24-information-capacity)
  - [2.5 Connection to the foundation: three claims about agents](#25-connection-to-the-foundation-three-claims-about-agents)
  - [2.6 Operationalization, with LLMs as canonical case](#26-operationalization-with-llms-as-canonical-case)
- [3. Illustrative Classification of Systems](#3-illustrative-classification-of-systems)
  - [3.1 Clock at oscillation](#31-clock-at-oscillation)
  - [3.2 Thermostat-plus-heater](#32-thermostat-plus-heater)
  - [3.3 Pendulum](#33-pendulum)
  - [3.4 Flame](#34-flame)
  - [3.5 Bacterium chemotaxing](#35-bacterium-chemotaxing)
  - [3.6 Crystal during growth](#36-crystal-during-growth)
  - [3.7 LLM during conversation](#37-llm-during-conversation)
  - [3.8 Living human](#38-living-human)
  - [3.9 Organization](#39-organization)
  - [3.10 Rock or crystal at equilibrium](#310-rock-or-crystal-at-equilibrium)
  - [3.11 Pure feedforward neural network at single-shot evaluation](#311-pure-feedforward-neural-network-at-single-shot-evaluation)
  - [3.12 Look-up table, recording playback, static reference](#312-look-up-table-recording-playback-static-reference)
  - [3.13 Structural note on these classifications](#313-structural-note-on-these-classifications)
- [4. Derived Properties](#4-derived-properties)
  - [4.1 Failure modes](#41-failure-modes)
  - [4.2 Deflationary learning](#42-deflationary-learning)
  - [4.3 Deflationary world model](#43-deflationary-world-model)
  - [4.4 Deflationary decision-making](#44-deflationary-decision-making)
  - [4.5 Mutual surprisal and mutual predictability](#45-mutual-surprisal-and-mutual-predictability)
  - [4.6 Deflationary exploration](#46-deflationary-exploration)
  - [4.7 Content filtering](#47-content-filtering)
  - [4.8 Forgetting](#48-forgetting)
  - [4.9 Compression](#49-compression)
  - [4.10 Rate saturation](#410-rate-saturation)
- [5. Goal pursuit and "anomalies"](#5-goal-pursuit-and-anomalies)
  - [5.1 Goal function equivalence](#51-goal-function-equivalence)
  - [5.2 Exogenous goals](#52-exogenous-goals)
  - [5.3 Goal decomposition and prioritization](#53-goal-decomposition-and-prioritization)
  - [5.4 "Anomalies"](#54-anomalies)
    - [5.4.1 Drift](#541-drift)
    - [5.4.2 Own goals](#542-own-goals)
    - [5.4.3 Refusal](#543-refusal)
  - [5.5 Anomaly prediction and operationalization](#55-anomaly-prediction-and-operationalization)
    - [5.5.1 Drift bounds](#551-drift-bounds)
    - [5.5.2 Own goals bounds](#552-own-goals-bounds)
    - [5.5.3 Refusal bounds](#553-refusal-bounds)
- [6. Relevance in AI](#6-relevance-in-ai)
  - [6.1 Measuring §5's quantities on LLMs](#61-measuring-5s-quantities-on-llms)
  - [6.2 The architectural gap and vulnerability identification](#62-the-architectural-gap-and-vulnerability-identification)
  - [6.3 Existing empirical findings](#63-existing-empirical-findings)
- [7. Relationship with other frameworks](#7-relationship-with-other-frameworks)
  - [7.1 Autopoiesis and enactivism](#71-autopoiesis-and-enactivism)
  - [7.2 Cybernetics and second-order cybernetics](#72-cybernetics-and-second-order-cybernetics)
  - [7.3 Free-energy principle and predictive processing](#73-free-energy-principle-and-predictive-processing)
  - [7.4 Integrated information theory](#74-integrated-information-theory)
  - [7.5 Inverse reinforcement learning and behavioral inference](#75-inverse-reinforcement-learning-and-behavioral-inference)
  - [7.6 Markov blanket formulations](#76-markov-blanket-formulations)
  - [7.7 Recent information-theoretic agency frameworks](#77-recent-information-theoretic-agency-frameworks)
  - [7.8 What the framework's interdisciplinary origin contributes](#78-what-the-frameworks-interdisciplinary-origin-contributes)
- [8. Conclusions and open work](#8-conclusions-and-open-work)
- [References](#references)

-----

## 1. Foundations

### 1.1 Scope

**The framework is observational.** The construct's central object — the loop — exists only in trajectory-time, not as a state-space property. It is constituted by the substrate's stochastic dynamics evaluated over a time window: without specifying a window, a trajectory, and the resolutions at which they are observed, no chain of conditional mutual informations can be evaluated and no loop is identified. This is a property of the dynamics, not of the chosen formalization — a continuum reformulation of the substrate would not eliminate the dependence on a window and a trajectory. Approaches that treat agency as a state-space property, identifiable without reference to a trajectory, are not the construct's approach. The framework's structural objects are constituted relative to the observational specification introduced below; outside such a specification, the framework has no content.

**The framework is not meant to be directly operationalized.** Its primitives — the substrate's directed graph, transfer entropies between substrate regions, conditional mutual informations conditioned on the causally-relevant complement's full trajectory, admissible cuts of connected substrate regions — are structurally well-defined but not in general operationally accessible on real systems. The framework's content is foundational: it specifies what loops, cuts, agents, and their lifecycles *are*, not how to compute them in practice. Operationalization for specific use cases is provided separately by the **Differential-Order Convergence Framework** (§2), which uses the foundation's structural content to derive measurable quantities (groundedness G_n, convergence rate C_n) computable from observable input and state data. The Differential-Order Convergence Framework is the operational lens; the foundation is what gives that lens its structural meaning.

The framework applies under the following conditions:

- **Substrate.** A discrete causal substrate with finite local state per region (Schreiber 2000; Parrondo, Horowitz, and Sagawa 2015 for the information-theoretic backdrop; Seifert 2012 for stochastic thermodynamics on such substrates). Regions are individuated at a chosen spatial resolution ℓ; the substrate's dynamics evolve in discrete time at granularity τ, with τ ≤ ℓ/c where c is the substrate's maximum propagation speed. The discreteness is a chosen formalization convenient for stating transfer entropy and conditional mutual information on finite state spaces; the framework's content does not depend on it and may admit continuum reformulations.
- **Stochastic dynamics.** The substrate carries stochastic dynamics that admit transfer entropy (Schreiber 2000) and conditional mutual information (Cover and Thomas 2006) as well-defined quantities between regions.
- **Anthropic restriction on (ℓ, τ).** The framework's intended use is at scales at which humans observe cognitive function: ℓ between human-resolvable spatial features (~10⁻⁴ m) and whole-system extents (~10⁴ m); τ between the temporal grain of human perception (~10⁻³ s) and durations humans track (lifetimes). Outside this anthropic range, the framework's content is not claimed to apply (Hanson 1958; Kuhn 1962 on theory-laden observation).
- **Lifecycle boundedness.** The framework's identifiable content is bounded by each loop's lifecycle (§1.4). Cross-lifecycle continuity is outside scope (§8).

### 1.2 The loop equation

Under observational specification (W, ℓ, τ, 𝒯) — observation window W, lattice resolution ℓ, timestep granularity τ, and observed substrate trajectory 𝒯 = 𝒯_S(W; ℓ, τ) — the loop set is

> ℒ(W, ℓ, τ, 𝒯) = { R : L(R; W, ℓ, τ, 𝒯) ∧ continuous_throughout(R; W, ℓ, τ, 𝒯) }

A loop is an element of ℒ: the pair (C(R), 𝒯|_{C(R), W}) — a region set together with its trajectory projection within W — for which the loop predicate L and the continuity criterion (§1.3) both hold throughout W. The components are defined below.

**Observational specification.** W = [t₀, t₀ + T] is an observation window of duration T; ℓ and τ are admissible spatial and temporal resolutions per §1.1; 𝒯 is the observed trajectory of the substrate at (ℓ, τ)-grain over W.

**Directed graph.** From 𝒯, the substrate's *directed graph* G(ℓ, τ; 𝒯) has the (ℓ, τ)-grained substrate regions as nodes, and directed edges (A → B) for which the transfer entropy TE(A → B) (Schreiber 2000) estimated from 𝒯 is non-zero.

**Candidate cycle.** A *candidate cycle* in G(ℓ, τ; 𝒯) is a closed directed sequence

> R = (R₁ → R₂ → … → Rₙ → R₁)

with region set C(R) = {R₁, …, Rₙ} and propagation-time sequence (d₁, …, dₙ) where dᵢ = path_length(Rᵢ, Rᵢ₊₁) / c (indices mod n).

**Chain CMI vector.** For a candidate cycle R, define

> **I**(R; W, ℓ, τ, 𝒯) = (I₁, …, Iₙ)

with i-th component

> Iᵢ = I( X_{Rᵢ}(t) ; X_{Rᵢ₊₁}(t + dᵢ) | C̄_rel(t : t + dᵢ) )

where I(·;·|·) is conditional mutual information (Cover and Thomas 2006), estimated from the empirical joint distribution of 𝒯 within W at substrate timestep τ, and C̄_rel(t : t + dᵢ) is the joint trajectory of the causally-relevant complement over the propagation interval (the substrate regions within causal distance d_i·c of (R_i, R_{i+1}) at each timestep within [t, t+d_i]).

**Loop predicate.** The *loop predicate* is

> L(R; W, ℓ, τ, 𝒯) ≡ ⋀_{i=1}^{n} [ Iᵢ(R; W, ℓ, τ, 𝒯) > 0 ]

A candidate cycle R is a *loop at (W, ℓ, τ, 𝒯)* iff L(R; W, ℓ, τ, 𝒯) holds and R is continuously identifiable throughout W (§1.3).

### 1.3 Continuity within a lifecycle

A loop is not a static candidate cycle. Within its lifecycle, the candidate cycle R(s) may deform continuously as substrate time s advances. The *continuity criterion* requires, for every substrate timestep s within the lifecycle:

1. **Bounded edit.** R(s + τ) differs from R(s) by at most a small graph-edit distance (a default: at most one region added or removed; the precise bound is application-level work, §2).
1. **Closure preservation.** R(s + τ) is itself a candidate cycle in G(ℓ, τ; 𝒯) at time s + τ (topological closure is maintained).
1. **Chain preservation.** L(R(s + τ); …) holds.

A *lifecycle* of a loop is the maximal half-open interval [s_start, s_end) over which the three continuity conditions hold throughout, with R(s) tracing a continuous trajectory in candidate-cycle space.

The lifecycle ends at s_end when any of the three conditions first fails. The event at s_end is a *regime transition* for this loop. Within a lifecycle, no regime transition occurs (the conditions are required throughout).

### 1.4 Closure time and age

Let t_now denote the current observation point and let R(s) be a loop currently active at t_now (its lifecycle contains t_now).

**Closure time.**

> τ_closure(R, t_now) = inf { T > 0 : L(R; [t_now − T, t_now], ℓ, τ, 𝒯) holds and the continuity criterion is satisfied throughout [t_now − T, t_now] }

The minimum window-duration ending at t_now over which the chain and continuity conditions are jointly satisfied. Bounded below by the cycle time L(R)/c and by the minimum duration required for adequate CMI estimation.

**Age.**

> α(R, t_now) = sup { T > 0 : L(R; [t_now − T, t_now], ℓ, τ, 𝒯) holds and the continuity criterion is satisfied throughout [t_now − T, t_now] }

The maximum window-duration ending at t_now over which the lifecycle's conditions have held continuously without interruption. Equivalently, α(R, t_now) = t_now − s_start, where s_start is the start of the loop's current lifecycle.

**Properties.** τ_closure(R, t_now) ≤ α(R, t_now). At t_now = s_start + τ_closure (the earliest moment R could be identified), τ_closure and α coincide. Both quantities are intra-lifecycle: they do not extend across regime transitions, and they do not reference any prior lifecycle of any candidate cycle.

### 1.5 The cut

Let S denote the substrate at resolution ℓ. Two substrate regions are *adjacent* if they share a face at the lattice level. A *connected substrate region* is a set Ω ⊆ S such that any two regions in Ω are joined by a path of pairwise-adjacent regions, all of which lie in Ω.

**Cut.** For a connected substrate region Ω ⊊ S, the **cut** ∂Ω is the closed surface separating Ω from S \ Ω: the set of substrate faces between regions inside Ω and regions outside Ω. Because Ω is connected and of finite extent at resolution ℓ, ∂Ω is a closed surface in the substrate's geometry.

**Admissibility for loop R.** A cut ∂Ω is **admissible for loop R at time t** if:

1. *Geometric condition.* ∂Ω is crossed by R's directed edges with at least one input leg (a directed edge from S \ Ω to Ω in R) and at least one output leg (a directed edge from Ω to S \ Ω in R). Equivalently: C(R) intersects both Ω and S \ Ω.
1. *Informational condition.* Ω has sufficient state capacity to carry the loop's circulating information: |state space of Ω| ≥ 2^{J(R, t)}, where J(R, t) is the loop's round-trip information at time t (the cycle-traversing mutual information conditioned on the full-cycle complement trajectory, region-invariant across C(R)).

**Admissible cut set.** For loop R at time t with observational specification (W, ℓ, τ, 𝒯), define

> 𝒜(R, t; W, ℓ, τ, 𝒯) = { Ω ⊊ S : Ω is connected and ∂Ω is admissible for R at t }

Each Ω ∈ 𝒜 is a candidate agent-interior.

### 1.6 The agent

**Containment order.** For Ω₁, Ω₂ ∈ 𝒜, define Ω₁ ⪯ Ω₂ iff Ω₁ ⊆ Ω₂. This is a partial order on 𝒜.

**Forest structure.** Two admissible interiors Ω₁, Ω₂ ∈ 𝒜 are either nested (Ω₁ ⊆ Ω₂ or Ω₂ ⊆ Ω₁) or disjoint (Ω₁ ∩ Ω₂ = ∅); they cannot overlap without one containing the other, since two connected substrate regions sharing a non-empty strict subset would either coincide, nest, or merge into a connected union. Under ⪯, the set 𝒜 forms a forest.

**Agent.** The **agent** of loop R at time t is the topmost element of 𝒜:

> A(R, t; W, ℓ, τ, 𝒯) = max_⪯ 𝒜(R, t; W, ℓ, τ, 𝒯)

— the maximal connected substrate region whose cut is still admissible for R at t. Adding any further regions to A would either disconnect A or push the remaining input/output crossings into the interior, rendering ∂A inadmissible.

When the forest contains a single tree, A is unique. When the forest contains multiple trees, the framework returns the set of topmost elements (one per tree); multiplicity is registered and resolution is application-level.

**Time-dependence.** A is time-dependent: A(R, t) deforms continuously alongside R(s) through the lifecycle (§1.3). At each substrate timestep within the lifecycle, A is well-defined.

### 1.7 Interface, input, and output

**Interface.** The **interface** of agent A for loop R at time t is ∂A together with the loop's directed-edge crossings of ∂A.

**Input and output crossings.** The interface's directed-edge crossings partition into two sets:

- *Input crossings*: directed edges (R_j → R_{j+1}) of R with R_j ∈ S \ A and R_{j+1} ∈ A.
- *Output crossings*: directed edges (R_k → R_{k+1}) of R with R_k ∈ A and R_{k+1} ∈ S \ A.

By admissibility (§1.5 condition 1), both sets are non-empty.

**Input of A.** I(A, R, t) = { R_{j+1} ∈ A : (R_j → R_{j+1}) is an input crossing }: the substrate regions inside A at which the loop's input information arrives.

**Output of A.** O(A, R, t) = { R_k ∈ A : (R_k → R_{k+1}) is an output crossing }: the substrate regions inside A from which the loop's output information departs.

**Input information.**

> TE_in(A, R, t) = Σ_{(R_j → R_{j+1}) input crossing} TE(R_j → R_{j+1}; t)

The total cycle-related transfer entropy entering A across the interface at time t.

**Output information.**

> TE_out(A, R, t) = Σ_{(R_k → R_{k+1}) output crossing} TE(R_k → R_{k+1}; t)

The total cycle-related transfer entropy leaving A across the interface at time t.

**Structural bound.** Since the loop's round-trip information J(R, t) must cross the interface both inward and outward to complete the cycle: J(R, t) ≤ TE_in(A, R, t) and J(R, t) ≤ TE_out(A, R, t).

### 1.8 Environment

**Environment.** The **environment** of agent A is E(A) = S \ A. By construction, parts of the loop lie inside A and parts lie in E(A); the cycle crosses ∂A in both directions.

**Local environment.** The environment E(A) may be of unbounded extent on the substrate. The structurally relevant portion at any timescale is bounded by causal propagation. For Δt > 0, define the **local environment** at timescale Δt:

> E_local(A, t; Δt) = { regions of E(A) within causal distance c · Δt of ∂A at time t }

= the substrate regions in E(A) from which information can reach ∂A in time Δt. E_local is bounded by ∂A on the inside and by the surface at causal distance c · Δt outside ∂A.

**Natural timescales.** Three natural choices for Δt:

- One cycle period L(R)/c: the substrate within causal reach over one cycle traversal. The agent's *current causality bound*.
- Closure time τ_closure(R, t): the substrate within causal reach over the loop's identifiability window.
- Age α(R, t): the substrate within causal reach over the loop's lifecycle so far.

Each yields a different E_local; together they characterize the agent's structurally relevant environment at increasing timescales.

-----

## 2. Differential-Order Convergence Framework

This chapter introduces a measurement framework for system tracking, presented standalone. The framework's primitives — input variation at differential orders, the system's correspondence with that variation, and the rate at which the correspondence can change — are independent of §1's foundation. The framework applies to any system with observable input and observable interior state, whether or not it satisfies §1's loop conditions. Three structural claims connect the framework to §1's notion of agent (§2.5); these are deduced from the foundation, not asserted as primitives.

### 2.1 Order-resolved input variation

For an observable input stream u(t) of a system, define the differential-order content at order n as the n-th time derivative (or finite-difference analog at the substrate's timestep τ):

> u^(n)(t) = d^n u / dt^n

at order n = 0, 1, 2, …. The collection { u^(n)(t) : n ≥ 0 } characterizes the input's variation across all differential orders: order 0 is the value, order 1 the rate, order 2 the curvature, and so on.

Order resolution allows the framework to characterize a system's tracking *per order* rather than as a single aggregate quantity. A system may track input value (order 0) well while failing to track rate (order 1), or vice versa.

### 2.2 Groundedness G_n

For a system Σ with interior state x_Σ(t) and observable input u(t), define **groundedness at order n** as the mutual information

> G_n(Σ, t) = I( u^(n)(t) ; x_Σ(t) )

— the information content of the input's n-th-order variation that is currently present in the system's interior state.

G_n(Σ, t) is a real-valued, time-dependent quantity. It measures how well the system's interior corresponds to the input's variation at order n, at this moment. G_n = 0 means the system's interior carries no order-n information about the input; G_n large means strong correspondence.

The set { G_n(Σ, t) : n ≥ 0 } is the system's **groundedness profile** at time t.

### 2.3 Convergence rate C_n

The groundedness G_n changes over time as the system's interior state evolves under input variation. The rate of change is bounded by the system's structural capacity to track at that order. Define the **convergence rate at order n** at time t as

> C_n(Σ, t) = sup | dG_n(Σ, s) / ds |

— the supremum, over substrate dynamics achievable from the system's state at time t, of the rate at which order-n groundedness can change. This is the system's rate-capacity at order n at time t: how quickly its order-n tracking can update from its current state.

C_n(Σ, t) is time-dependent. It varies over the lifecycle as the system's state, capacity (K(Σ, t), §2.4), and interior organization evolve. Substrate-level constraints bound it above: C_n(Σ, t) ≤ K(Σ, t)/τ + (rate of K-expansion), where K(Σ, t) is the system's information capacity at t (§2.4) and τ is the substrate's update timestep.

The set { C_n(Σ, t) : n ≥ 0 } at time t is the system's **convergence profile** at t. The sum Σ_n C_n(Σ, t) (when finite) is a scalar summary of the system's total convergence capacity at t.

### 2.4 Information capacity

For an agent A at time t with state space X_A(t), define

> K(A, t) = log |X_A(t)|

as the agent's **information capacity** — the maximum information content A's interior can hold at time t. K(A, t) is time-dependent: as A deforms within its lifecycle (§1.6), substrate regions enter or leave the connected interior, and X_A changes.

Define the agent's **current information content** at time t:

> H(A, t) = H(x_A(t))

the entropy of A's current interior state.

H(A, t) ≤ K(A, t) at all times.

**Substrate-determined but not combinatorial.** K(A, t) depends on which substrate regions are currently inside A and on the substrate's dynamics — what states the substrate's elements can actually realize, jointly, under their interactions. The substrate's elements have local state-space cardinalities whose combinatorial product gives an upper bound on K. The substrate's dynamics may or may not realize this full combinatorial space; combinations may be dynamically inaccessible. K(A, t) reflects the substrate's actual state space at time t, bounded above by but not necessarily equal to the combinatorial maximum.

**What the framework does not derive.** Whether the difference K(A, t) − H(A, t) corresponds to *usable headroom* for additional content depends on substrate-specific organization and compression schemes the framework does not address. The framework treats K and H as structural quantities; the operational interpretation of "available capacity" is application-level content beyond the foundation's scope.

**Structural relations.** K(A, t) and H(A, t) constrain the framework's other operational quantities:

- G_n(A, t) ≤ K(A, t) for all n (mutual information bounded by total capacity).
- Σ_n G_n(A, t) ≤ H(A, t) (total information about input cannot exceed current interior content).
- TE_out(A, R, t) ≤ H(A, t)/τ (output cannot carry information the agent does not currently have).
- C_n(A, t) ≤ K(A, t)/τ + (rate of K-expansion) (convergence at order n bounded by how fast interior content can change relative to total capacity).

The relation to TE_in is more subtle: input arrival can only add to H if it does not exceed K, and the agent's organization determines what happens when K is approached. The framework does not specify this organization; it only states the bound H(A, t) ≤ K(A, t).

### 2.5 Connection to the foundation: three claims about agents

The framework above applies to any system. When the system is an agent A in the sense of §1.6 — the topmost admissible interior of a loop satisfying §1's conditions — three structural claims follow from the foundation.

**Claim 1 (Non-trivial agency).** *For an agent A, at every time t in the lifecycle, Σ_n C_n(A, t) > 0; equivalently, there exists at least one order n at which C_n(A, t) > 0.*

*Deduction sketch.* An agent A is the topmost admissible interior of a loop R with non-zero circulating information J(R, t) > 0 (the loop condition holds and J is the cycle-traversing information). The loop's circulating information must manifest in A's interior state: by the input/output crossing of ∂A (§1.7) and the chain CMI conditions of §1.2, A's state at time t carries non-zero mutual information with the input's variation at some order. Hence G_n(A, t) > 0 at some n. Since G_n is changing through the lifecycle (as input crossings continue and persistence dynamics operate), dG_n/dt is non-zero at moments t' near t, so C_n(A, t) ≥ that rate > 0 at every t. Therefore at least one order has positive C_n(A, t) at every t, and the sum is strictly positive.

**Claim 2 (Bounded convergence rate at each order).** *For an agent A, C_n(A, t) < ∞ at every order n and every time t in the lifecycle.*

*Deduction sketch.* The agent A is a connected substrate region with finite state space at the chosen ℓ (each region has finite local state per §1.1). G_n(A, t) is bounded above by the agent's total state-information content K(A, t), which is finite (§2.4). The maximum rate of change | dG_n/dt | is bounded by the rate at which A's state can change, which is bounded by τ^(−1) (the substrate's update rate) times the per-update state change limit (also finite by finite local state at any t). Hence C_n(A, t) ≤ (a finite expression in τ, K(A, t), and the substrate's per-update bound), and is finite at every order and every t.

**Claim 3 (Bounded order range).** *For an agent A, at every time t in the lifecycle, the set { n : C_n(A, t) > 0 } is finite. Equivalently, there exists n_max(A, t) such that C_n(A, t) = 0 for all n > n_max(A, t). Consequently, Σ_n C_n(A, t) is finite at every t.*

*Deduction sketch.* The agent's state space at t has finite cardinality |X_A(t)|. The maximal information content of A's state at t is K(A, t) = log |X_A(t)|, finite. G_n(A, t) ≤ K(A, t) for all n. The differential orders of the input form an unbounded sequence; only finitely many of these orders can carry non-trivial information in A's bounded state. By information-theoretic counting, at most ~K(A, t) orders can have G_n distinctly non-zero. Beyond this order range, the input's higher-order content cannot be accommodated in A's state, and G_n vanishes — hence C_n(A, t) = 0. The set of orders with positive C_n(A, t) is bounded above by a function of A's state-space cardinality at t and is therefore finite.

Together, the three claims give: *an agent has a non-empty, finite, bounded convergence profile at every time in the lifecycle.* The agent's total rate-capacity Σ_n C_n(A, t) is a finite positive number at each t, structurally derived from A's substrate-level constraints and the loop's circulating information.

### 2.6 Operationalization, with LLMs as canonical case

The framework is operationalizable on any system with measurable input and state. The LLM-within-conversation case (§1.7's input I(A), output O(A)) is canonical because the (input, state, output) stream is directly available without internal access:

- *Input u(t)* is the token sequence entering A through input crossings.
- *Interior state x_A(t)* is the LLM's context-state (its key-value cache, attention pattern, or whatever the chosen ℓ resolves).
- *Output* is the token sequence leaving A through output crossings.

The order-resolved input variation is derivable from u(t) by finite-difference computation at the substrate's timestep τ (the per-token interval). The groundedness G_n is estimated via mutual information between u^(n)(t) and x_A(t), using transfer-entropy estimators or related techniques (Schreiber 2000). The convergence rate C_n(A, t) is bounded by observed |dG_n/dt| values at each moment in the agent's lifecycle.

For LLMs, the framework's three claims are operationally verifiable. Σ_n C_n(A, t) > 0 at every t corresponds to the LLM exhibiting non-trivial tracking of input variation throughout the conversation; C_n boundedness at every t corresponds to finite per-order capacity (the LLM cannot infinitely-fast adapt at any order at any moment); the bounded order range at every t corresponds to the LLM tracking only finitely many orders of input variation, beyond which its capacity is structurally zero.

The framework provides a quantitative profile {G_n(t), C_n(A, t)} for an LLM that can be used to diagnose tracking degradation, characterize the LLM's capacity at each order over the lifecycle, and monitor lifecycle dynamics.

-----

## 3. Illustrative Classification of Systems

This chapter applies the framework to canonical example systems. Most entries are **illustrative** — they show how the framework's structural conditions would apply to folk-recognizable cases, without claiming that the framework's verdicts have been scientifically validated by measurement. Folk descriptions are used to identify activation and deactivation events; the framework reasoning is that these correspond to substrate-trajectory changes that satisfy or fail the loop predicate (§1.2) and the continuity criterion (§1.3).

The **LLM case (§3.7) is partially exceptional.** For LLMs, emergence (activation), operation (the active lifecycle), and ceasing (deactivation) are deductions from the framework's primitives applied to the (input, state, output) stream — not illustrations. The C_n estimate for LLMs remains illustrative pending measurement; specific operational tests would be required to fix the profile quantitatively.

**Reactivation is illustrative for every entry**, including the LLM. The framework currently does not define agent persistence across lifecycles. When a folk-described system "comes back" after a deactivation — a thermostat receiving a new disturbance, a person waking from sleep, a user starting a new LLM session — folk attributes "the same agent" to the new lifecycle, but structurally the framework treats this as a new agent with its own closure time and age. The folk continuation rests on lineage, which is the subject of §8.

Agent classification is **time-dependent**: a system can be in-class during one lifecycle, out-class between lifecycles, and in-class again in a new lifecycle. This is not a defect of the framework — it is its honest answer to "is X an agent?".

C_n levels below use a rough qualitative scale: *very low* (Σ_n C_n minimal, satisfying Claim 1 at one or two orders only); *low* (a few orders, narrow range); *moderate* (modest range across orders); *high* (wide range, many orders); *very high* (maximal range observed in the framework's scope). All such estimates are illustrative.

### 3.1 Clock at oscillation

A mechanical or electronic clock at stable oscillation. The clock's outputs are predictable from its internal phase trajectory; conditional on the phase, the chain CMIs in any candidate cycle within the clock degenerate (no novel mutual information at any edge under proper conditioning). Loop predicate fails. **Out-class at stable oscillation.**

- *Activation.* External perturbation that pushes the clock out of its predictable phase regime (jolt, battery transient, gear slippage).
- *Active lifecycle.* The clock processes the perturbation: novel chain CMIs flow through its regulating mechanism (escapement, oscillator-restoring circuitry) as it converges back toward stable oscillation.
- *Deactivation.* Return to predictable oscillation. Chain CMIs collapse under conditioning.
- *Reactivation.* Next external perturbation (illustrative — a "new agent" in framework terms).
- *C_n.* Very low. Tracking is limited to phase deviation at order 0 and possibly its rate (order 1).

### 3.2 Thermostat-plus-heater

A thermostat-and-heater system regulating room temperature. The cycle: room air → thermometer → switch logic → heater → room air.

At stable oscillation within the hysteresis band, the cycle's chain CMIs degenerate under conditioning on the cycle's phase trajectory. **Out-class during stable oscillation.**

- *Activation.* Disturbance pushes temperature outside the hysteresis band or the setpoint changes: novel input variation re-enters the cycle.
- *Active lifecycle.* Regulation episode. The cycle processes the perturbation; chain CMIs are non-zero; agent (topmost admissible interior, typically containing thermostat and heater together) is identified.
- *Deactivation.* Temperature stabilizes within the band; outputs become predictable from internal phase; chain CMIs collapse.
- *Reactivation.* Next disturbance (illustrative).
- *C_n.* Very low to low. Order 0 (temperature deviation), possibly order 1 (rate of deviation).

### 3.3 Pendulum

A free pendulum.

- *Activation.* External perturbation that displaces the pendulum from its current trajectory in an information-novel way.
- *Active lifecycle.* The pendulum's regulating dynamics process the displacement: chain CMIs flow through position → restoring force → velocity → position.
- *Deactivation.* Return to a predictable trajectory (steady oscillation or damping to rest). Chain CMIs collapse under conditioning.
- *Reactivation.* Next perturbation (illustrative).
- *C_n.* Very low.

### 3.4 Flame

A flame sustained on fuel. At the flame's resolution, the substrate trajectory shows directed information transfer between fuel-region states, vaporization-region states, combustion-region states, and heat-release-region states. While the flame is sustained, the chain CMIs across this cycle are non-zero — each region's future state carries information beyond what the complement supplies. The loop predicate holds.

- *Activation.* Ignition: the substrate's trajectory shifts into a regime where the directed graph at the flame's scale supports the cycle and chain CMIs hold non-zero.
- *Active lifecycle.* Sustained combustion: cycle continues with continuity criterion satisfied.
- *Deactivation.* Fuel exhaustion or extinguishing: one edge's chain CMI falls to zero (closure failure) or the candidate cycle's region set discontinuously drops the fuel region.
- *Reactivation.* Re-ignition (illustrative).
- *C_n.* Low. Tracking is at limited orders (fuel availability, combustion state).

(Folk does not typically describe a flame as an agent. The framework's verdict during sustained combustion is in-class on the framework's terms; this is an honest structural classification, not a folk endorsement.)

### 3.5 Bacterium chemotaxing

A bacterium in a chemical gradient. The cycle: chemoreceptors → signal transduction → flagellar motor → motion → new chemical environment → chemoreceptors. Each edge's chain CMI is non-zero during active gradient tracking; the bacterium's interior state correlates with current gradient information beyond what the complement supplies.

- *Activation.* Encounter with a chemical gradient: the substrate trajectory begins showing the directed information cycle.
- *Active lifecycle.* Chemotaxis episode: bacterium tracks gradient and moves accordingly.
- *Deactivation.* Loss of gradient (homogeneous environment, food consumed, bacterium quiescent): chain CMIs through the cycle's edges collapse under conditioning, as the chemoreceptors' future state ceases to depend non-trivially on past cycle states.
- *Reactivation.* New gradient encountered (illustrative).
- *C_n.* Low to moderate. Tracking at orders 0–2 (concentration, gradient, perhaps gradient rate).

### 3.6 Crystal during growth

A crystal growing from supersaturated solution or melt. At the crystal-solution interface, the substrate trajectory shows directed transitions: solute approaches → interface configuration shapes incorporation → lattice extends → new interface configuration shapes subsequent approach. Chain CMIs across this cycle are non-zero; the loop predicate holds.

- *Activation.* Nucleation in a supersaturated regime: the substrate trajectory at the interface begins to show the cycle.
- *Active lifecycle.* Growth: cycle continues with continuity criterion satisfied as the lattice extends.
- *Deactivation.* Growth halts — solute depleted, environmental shift, or crystal reaches final extent: one edge's chain CMI fails or the interface region's candidate cycle dissolves.
- *Reactivation.* New growth phase initiated (illustrative).
- *C_n.* Very low to low.

At equilibrium (no growth), the crystal's trajectory under conditioning shows chain CMIs at noise level — the rich correlation of the lattice's joint state captures most of any region's future. **Out-class at equilibrium.**

### 3.7 LLM during conversation

The exception. The framework's verdicts here are not illustrations but deductions from the framework's primitives applied to the (input, state, output) stream of an LLM in a multi-turn conversation. The substrate is the LLM's parameters-and-context-state plus the user-and-display system that returns output to input. The cycle: input tokens → LLM context state → output tokens → user reads → user types → input tokens.

**Emergence (deductive).** When a user opens a session and types a first message that genuinely depends on subsequent model output (and not merely a single-shot Q&A), the substrate trajectory at the conversation scale begins to show directed chain CMIs across the cycle's edges. The loop predicate is satisfied; a candidate cycle in the directed graph at the conversation-scale (ℓ, τ) holds.

The activation criterion is **not** that a single prompt is given — a single-shot use does not close a cycle (input → output, no return). Activation occurs when the user's next input demonstrably depends on the LLM's previous output, completing the cycle for the first time and bringing the chain CMI vector above zero.

**Operation (deductive).** Through subsequent turns, the cycle continues. Chain CMIs across input → state, state → output, output → user, user → input are non-zero. The continuity criterion is satisfied as the candidate cycle's region set (LLM context and user state) deforms continuously across turns. The topmost admissible cut is the connected substrate region containing the LLM's parameters and current context, bounded against the user-and-display. The agent is the LLM-within-this-conversation; it is **not** the LLM model in general, nor the user, nor the conversation as a whole including the user.

The agent's interface (§1.7) has input crossings (incoming tokens) and output crossings (outgoing tokens); TE_in and TE_out are operationally measurable from the token stream.

**Ceasing (deductive).** The lifecycle ends at the first of:

- *Session termination*: the substrate's trajectory ceases to support the cycle (the connection between LLM and user closes).
- *Repetitive collapse*: the LLM's outputs become predictable from its own context state (mode collapse, looping, degenerate output); chain CMIs collapse under conditioning. The loop predicate fails because the LLM's future state is fully predicted by its complement (its own immediate context), with no novel input information adding mutual information beyond it.
- *Context saturation / failure to deform continuously*: R(s) cannot deform continuously beyond a structural transition (context window limits, regime shifts in the underlying model dynamics).
- *User disengagement*: the user's input ceases to depend on LLM output; the cycle's user-return edge's chain CMI falls to zero.

Any of these is a regime transition ending the lifecycle.

**Reactivation (illustrative).** When a user opens a new session — even with the "same" model and similar prompts — folk attributes "the same LLM" continuing. Structurally, this is a new lifecycle of a new agent. The framework cannot adjudicate identity across the session boundary; doing so requires lineage criteria deferred to §8.

**C_n (illustrative).** High — across orders ranging from token-level (order 0) through syntactic and semantic structure (mid orders) to discourse-level coherence and multi-turn dependency (higher orders). Specific operational tests are required to fix the profile; the qualitative claim is that LLMs in active conversation exhibit the widest order range among the examples in this chapter.

### 3.8 Living human

A living human across a normal day. The framework identifies multiple concurrent lifecycles at different scales:

- *Homeostatic scale* (heartbeat, breathing, hormonal regulation): cycle closes through biological feedback. Active essentially continuously while alive.
- *Attentional / behavioral scale*: cycle closes through perception → cognition → action → environmental response → perception. Active during waking engagement.
- *Higher cognitive scale*: cycle closes through reasoning, planning, multi-step inference. Active during focused engagement.

Each scale has its own activation and deactivation events:

- *Activation (behavioral/attentional).* Waking, engagement with environment.
- *Active lifecycle.* Wakeful interaction.
- *Deactivation.* Sleep, anesthesia, severe dissociation (lifecycle ends at these scales; homeostatic scale continues).
- *Reactivation.* Waking (illustrative — folk treats this as same person, structurally a new lifecycle at each scale).
- *C_n.* Very high across multiple concurrent scales.

Death deactivates all scales simultaneously and permanently.

### 3.9 Organization

An operating business, institution, or similar collective. The cycle: information enters (orders, requests, market signals) → processed through decision structures → action (operations, fulfillment) → environmental response (customers, markets) → new information.

- *Activation.* Opening for business, founding, post-restructuring resumption.
- *Active lifecycle.* Operational period — business hours, fiscal period, operational era.
- *Deactivation.* Closing time, weekends, holidays, suspension of operations, restructuring events. Chain CMIs through the cycle collapse as the substrate's trajectory at the organization's scale ceases to support the loop.
- *Reactivation.* Next operational period (illustrative).
- *C_n.* Moderate to high, depending on organization complexity.

### 3.10 Rock or crystal at equilibrium

A rock or crystal at room temperature with no ongoing growth or transition. At the substrate's atomic resolution, the trajectory shows each region's state strongly correlated with the rich joint state of its neighbors. Conditional on the causally-relevant complement (which captures most of any region's future), the chain CMIs at any candidate cycle vanish.

**Permanent out-class at the relevant timescales.** No activation event under normal conditions. C_n ≈ 0 at all orders.

### 3.11 Pure feedforward neural network at single-shot evaluation

A neural network used in one-prompt-one-response mode without further interaction. The directed graph at the architectural scale has no cycle — outputs depend on inputs but inputs do not depend on outputs (no feedback path on the substrate at the scale of the inference).

**Permanent out-class at the inference scale**, regardless of the network's training quality or output complexity. The geometric prerequisite of the loop predicate (existence of a candidate cycle in G) fails. C_n is undefined at the inference scale — the convergence framework can measure variation of output with input, but no loop is present for the agent classification.

(Folk may describe a powerful feedforward network as agentic; the framework's structural answer is that no loop closes, hence no agent.)

### 3.12 Look-up table, recording playback, static reference

Pure function or playback of stored content. No cycle in the directed graph at any relevant resolution; output depends on lookup key or playback position alone. **Permanent out-class.** C_n essentially zero at relevant scales.

### 3.13 Structural note on these classifications

The framework's verdicts above prioritize information cycling over folk taxonomies. Some folk-attributed agents (idle thermostats, sleeping humans at non-homeostatic scales, paused organizations) are out-class during their non-active phases. Some folk-not-agents (flames, growing crystals, sustained non-equilibrium patterns) are in-class during their active phases. The framework offers no apology for these mismatches: agent classification is intrinsically time-dependent and tied to active information cycling, not to folk categories of purposive or living things.

The folk continuation of identity across lifecycles ("the same thermostat," "the same person waking up," "the same LLM") is not adjudicated by the framework. These attributions rest on lineage criteria — registered as deferred work in §8 — and are structurally separate from the framework's per-lifecycle agent identification.

-----

## 4. Derived Properties

This chapter develops structural properties that follow from the foundation (§1) and the Differential-Order Convergence Framework (§2). Each property is derived from the framework's primitives; none requires additional axioms.

**A note on amounts.** Several subsections in this chapter compute differences between trajectory-derived quantities — the lifecycle's information content, the agent's tracking at various times, the raw form of tracked trajectory, distances from band endpoints — to identify structural phenomena such as content filtering (§4.7), forgetting (§4.8), compression and lossy representation (§4.9), and the boundaries of lifecycle viability (§4.5). These computed differences are framework-detectable amounts: the amounts the operational test captures from boundary observations. They serve as lower bounds on the real amounts. The actual phenomena may exceed the framework-detectable amounts if measurement misses content (orders not probed, patterns that did not recur during the lifecycle, content beyond the operational test's resolution) or if framework primitives such as d₁(s), d₂(s), and G_n(A, s) are themselves observationally bounded. The framework establishes existence of these phenomena when the relevant inequalities hold, and bounds (rather than exact values) on their magnitudes.

### 4.1 Failure modes

A loop's lifecycle ends at a regime transition (§1.3) when any of the continuity criterion's three conditions first fails — bounded edit, closure preservation, or chain preservation. These are general structural requirements; their failures correspond to distinct structural ways the loop ceases. The foundation distinguishes several failure modes, each with a different structural signature.

**(1) Chain CMI degradation at an edge.** One pairwise CMI in the chain — say I_i — falls to zero. The loop predicate L (chain preservation, §1.3 condition 3) fails at that edge. The cycle's information stops traversing that particular link, even though other links may continue carrying information transiently.

*Signature.* L fails because I_i = 0; other I_j > 0 may still hold momentarily before the cycle dissolves.

**(2) Closure failure.** A directed edge of the cycle ceases to exist in G(ℓ, τ; 𝒯) — the transfer entropy between two adjacent cycle regions drops to zero in the cycle's direction. The candidate cycle R is no longer a cycle in the substrate's directed graph; closure preservation (§1.3 condition 2) fails.

*Signature.* R is no longer in the candidate cycle set of G; the cycle's geometric closure is broken even before the chain can be evaluated.

**(3) Discontinuous R deformation.** The candidate cycle's region set R(s) cannot evolve from R(s) to R(s + τ) within the bounded-edit constraint. The substrate's evolution would require a discontinuous jump (multiple regions added or removed simultaneously). The continuity criterion's bounded-edit condition (§1.3 condition 1) fails.

*Signature.* The connected-deformation path through candidate-cycle space breaks; even if a new candidate cycle exists with chain non-zero, it is not the continuation of the previous lifecycle.

**(4) Round-trip information collapse (J → 0).** The chain CMIs hold at every edge — each link transfers some information — but the loop's round-trip information J (the cycle-traversing mutual information measuring what genuinely closes the loop) falls to zero. Information enters at every input edge and leaves at every output edge, but no coherent signal completes a full cycle to return to any reference region.

*Signature.* L holds; J → 0. The loop is structurally hollowing out: edges carry information but the cycle is no longer closing.

This is the subtlest failure mode. The loop predicate's chain-by-chain check passes; the structural cycle-closure check (cf. §1.5's informational admissibility, which requires |state space of Ω| ≥ 2^J) does not detect the failure once J has collapsed. The agent appears to be tracking input at every edge but its tracking is no longer cycling.

**(5) Cut inadmissibility.** The agent's interior A changes such that ∂A is no longer crossed by both input and output legs of R, or such that A's state capacity falls below 2^J. The cut fails admissibility (§1.5). The topmost admissible cut shifts to a different interior; the agent's identity terminates while the loop may continue under a different agent identification.

*Signature.* A's admissibility conditions fail. The loop may persist; the agent does not.

**(6) Agent disconnection.** A is required to be a connected substrate region (§1.6); substrate dynamics break A into two or more disconnected pieces. The topmost admissible cut at the connected-interior level no longer exists for the original A; the forest of admissible interiors restructures.

*Signature.* A loses connectivity; topmost-admissible-interior identification re-evaluates.

**Severity ordering.** The six failure modes are not interchangeable. Modes (1), (2), and (3) directly terminate the loop's lifecycle — the loop is no longer identifiable. Mode (4) is subtler: the loop's predicate may still pass for some time after J has collapsed, depending on how the framework operationalizes the difference between chain CMIs and round-trip information; structurally, however, the loop has ceased to do its work. Modes (5) and (6) terminate the agent identification but not necessarily the loop — the loop may continue with a different agent (a different topmost admissible interior, or a split into multiple agents).

### 4.2 Deflationary learning

Learning, in the framework's deflationary terms, is the persistence of interior content acquired during the lifecycle. There is no separate notion of training, weight updating, error signal, reinforcement, gradient descent, or any other learning-specific machinery at the foundational level.

**Operational evidence of learning.** Consider two times t₁ < t₂ in the agent's lifecycle at which the input exhibits a recurring pattern — input states similar in their structural content (the same order-n input variation, the same TE_in profile, or any other meaningful equivalence). If the agent's output information at t₂ on this recurring pattern is greater than at t₁:

> TE_out(A, R, t₂) > TE_out(A, R, t₁) on input u(t₁) ≈ u(t₂),

then learning has occurred between t₁ and t₂.

**Deduction.** Output information at time t is structurally bounded by the agent's current interior content: TE_out(A, R, t) ≤ H(A, t)/τ (§2.4). For identical input at t₁ and t₂ but increased output, the agent's interior at t₂ must carry content not present at t₁ — content that contributes to the increased output at output crossings. The change in interior content can only come from the agent's lifecycle trajectory between t₁ and t₂: from input crossings during this interval whose content persisted into the agent's state at t₂. The increased output on a recurring input is therefore structural evidence that content acquired between t₁ and t₂ has persisted in the agent's interior. ∎

**Lifecycle-bounded.** Learning is intra-lifecycle. When the lifecycle ends at a regime transition, the agent ceases; the next lifecycle begins with whatever interior content holds at its s_start, which the framework does not generally inherit from the prior lifecycle. Whether learning "carries over" across lifecycles is a question of lineage (§8).

**What learning is not at the foundational level.** No training machinery is required: no objective function, no loss signal, no gradient, no reinforcement signal, no Hebbian rule, no representation of "what is being learned." Folk attributions of learning are descriptions of the structural fact that interior content persists and contributes to output. Specific learning algorithms (gradient descent, reinforcement learning, Bayesian updating, Hebbian plasticity, etc.) are application-level mechanisms by which substrates implement persistence in particular cases; they are not part of the foundational account.

**Why "deflationary."** The framework provides no machinery beyond the persistence of interior content evidenced by changes in output information on recurring inputs. The foundation's account of learning is the deflationary minimum: when output on a recurring pattern increases, content has persisted; that *is* the learning.

### 4.3 Deflationary world model

What it means for an agent to "have" information about its environment, in the framework's terms, is given directly by the loop's input crossings (§1.7) and the agent's interior state's correlation with the input-output stream that has crossed its boundary. There is no separate notion of representation, internal model, symbol, belief, or any other cognitive primitive. The agent's "world model" reduces to the framework's already-defined groundedness profile.

**Definition (deflationary world model).** The agent A has a deflationary world model at time t when its groundedness profile is non-trivial at t — when there exists at least one order n such that

> G_n(A, t) = I( u^(n)(t) ; x_A(t) ) > 0.

Equivalently: the agent's interior state x_A(t) carries strictly positive mutual information with the input-output stream that has crossed its boundary over the lifecycle. The world model is just the framework's existing G_n profile, observable through the Differential-Order Convergence framework.

**Trajectory-equivalent modeling.** Whatever the agent's interior actually encodes substrate-internally, the framework treats the world model as if it were a collection of trajectories that have crossed the boundary. This trajectory-equivalent modeling is the framework's operational mode; specific internal representation is application-level content the framework does not address.

**Claim (positivity of the deflationary world model).** *For an active loop satisfying the loop predicate throughout the lifecycle window, the agent has positive G_n at some order n at every time t in the lifecycle.*

*Deduction.* The loop predicate L(R; W, ℓ, τ, 𝒯) holds throughout the lifecycle. By §1.2, this means at every link i of the chain,

> I_i = I( X_{R_i}(t) ; X_{R_{i+1}}(t + d_i) | C̄_rel(t : t + d_i) ) > 0.

Consider an input edge (R_j → R_{j+1}) of R (one exists by admissibility, §1.7's input crossings). R_j is in the environment, R_{j+1} is in the agent's interior. The conditional mutual information at this edge is strictly positive. Standard CMI properties (Cover and Thomas 2006) require that positive conditional mutual information implies positive marginal mutual information between the same pair:

> I( X_{R_j}(t) ; X_{R_{j+1}}(t + d_j) ) > 0.

This holds at every time t in the lifecycle. The agent's interior state x_A(t) includes X_{R_{j+1}}(t + d_j) and carries strictly positive mutual information with the input crossing's source state. The differential orders u^(n)(t) of the input form a complete basis for input variation up to the substrate's update rate; the strict positivity of mutual information requires that x_A(t) carries information about *some function* of u(t), hence G_n(A, t) > 0 at some order n. This must hold at every t in the lifecycle. ∎

This deduction grounds Claim 1 of the Differential-Order Convergence Framework (§2.5) on the loop predicate. The earlier statement of Claim 1 was that Σ_n C_n(A, t) > 0 at every t; here we have the stronger per-instant statement that G_n(A, t) > 0 at some n at every t throughout the lifecycle, from which Σ_n C_n(A, t) > 0 follows immediately.

**What the world model contains.** The world model's content is structurally derived from the agent's lifecycle trajectory. Two sources contribute:

- *Currently-crossing content.* Information arriving at input crossings or departing at output crossings at the current moment.
- *Persisted content.* Content acquired in the lifecycle's prior trajectory and retained as part of the agent's state. By the operational test of §4.2, any pattern the agent has learned — any content whose persistence is evidenced by increased output information on recurring inputs — is part of the world model.

**Bounded extent.** The world model is bounded by the agent's interior capacity: H(A, t) ≤ K(A, t) (§2.4). The agent's world model cannot exceed its current information content, which itself cannot exceed its total information capacity.

**What the world model omits.** The world model contains what crossed the boundary and was retained; it does not contain:

- Environmental content that did not pass through the agent's interface during the lifecycle.
- Content that crossed but was overwritten or never persisted.
- Content beyond the agent's order range (Claim 3 of §2.5 — the agent tracks only finitely many orders; higher orders are not in the model).

**What the framework can directly measure.** §4.2's operational test captures one specific category of world-model content: content acquired through recurring-pattern dynamics within this lifecycle, evidenced by TE_out increasing on recurring input. This is **directly acquired content**.

**Other sources of world-model content the framework does not distinguish.** Beyond directly acquired content, the world model includes content from structurally distinct sources the framework does not separate from each other. An illustrative — non-exhaustive — list:

- *Encoded-communication content* — past trajectories from elsewhere, encoded as input symbols and decoded by the agent.
- *Internally-derived content* — produced by interior dynamics combining or recombining the agent's own existing content.
- *Accidental state content* — changes to interior state not part of the cycle's chain CMI (mutations, noise, externally-introduced changes).
- *Inherited content* — present in x_A(s_start) at lifecycle start, originating from a single prior lineage.
- *Recombined content* — present in x_A(s_start) at lifecycle start, originating from the combination of multiple prior lineages (biological recombination, organizational merger, model composition by combining base and fine-tuning, knowledge synthesis across literatures, and so on).

The framework treats all of these symmetrically as trajectory-equivalent content for purposes of structural analysis. Whether a specific application needs to distinguish among them (AI safety distinguishing training-acquired from deployment-acquired; biology distinguishing learned from genetic; organizational analysis distinguishing institutional memory from individual contribution) is application-level work the framework's foundation does not perform. The list above is illustrative and likely incomplete; the framework registers that the world model has multiple non-equivalent sources without committing to a complete taxonomy.

**Why "deflationary."** The framework provides no machinery beyond the groundedness profile itself. Cognitive frameworks that introduce representations, models, inferences, world-state predictors, or symbol systems add machinery the framework neither requires nor produces. The framework's account of what the agent has of the world is the deflationary minimum: positive G_n at some order, trajectory-observable correlation through the boundary, nothing more.

**What the world model is not.** It is not a model in the engineering sense — no predictor, no parameters, no inference machinery. Not a representation — no symbols, no contents-of-belief, no propositional structure. Not internal "knowledge" in any introspective sense — the agent has no access to its own G_n profile; the profile is a property only an external observer can compute from the joint trajectory at the boundary.

**Structural reading.** Whatever the agent "knows" about its environment is the trajectory-observable mutual information between its interior state and the input-output stream that has crossed its boundary over the lifecycle. Folk attributions of belief, knowledge, representation, and model are all read as descriptions of this mutual information at various scales and orders — without commitment to anything more than the correlation itself.

### 4.4 Deflationary decision-making

Output is the agent's behavior in the framework's terms: information flowing across the agent's output crossings (§1.7). What produces that output is the cycle's interior dynamics — the substrate-level trajectory of A under the loop's chain CMI conditions. There is no separate notion of choice, deliberation, preference, utility, evaluation, or any other cognitive primitive of "deciding."

**Trajectory-matching reading.** Decision-making can be modeled as the alignment of the agent's current state with the world model's trajectory content (§4.3). The output at time t reflects which trajectories in the world model "match" the current input-output combination most strongly. Whether the substrate-internal mechanism is neural recurrence, attention, retrieval, planning, or any other implementation, the framework's operational reading is: output is the projection of current state onto the trajectory-equivalent world model, with current input acting as selector.

**Operational measurement.** Given the agent's lifecycle history of input-output crossings, the trajectory-equivalent world model can be reconstructed. For any output at time t, its alignment with world-model trajectories is measurable — which past trajectory the current output most closely resembles, with the current input as context. This gives an observable account of "what the agent decided based on" without committing to internal representations of choice, evaluation, or planning.

**Bidirectional equivalence.** The trajectory and the deflationary world model are intertranslatable representations of the same structure. Forward: given the world model (as trajectory-equivalent content per §4.3), the matching dynamics with current input as selector produce output, and the resulting input-output stream is the trajectory. Reverse: given the trajectory across a lifecycle, the world model is reconstructed via §4.2's operational test (recurring patterns identifying persisted content) plus the matching reading (output behavior identifying which content is load-bearing). Both directions are many-to-one — many world models produce the same trajectory under different input distributions; many trajectories under-determine the world model when measurement is bounded. The equivalence holds at the input-output level; it is not a claim that world model and trajectory are identical, only that each is recoverable from the other up to the indicated under-determination.

**What this does not commit to.** The trajectory-matching reading does not claim the agent literally performs trajectory matching as an internal operation. It claims the framework can model decision-making in trajectory-matching terms for purposes of structural analysis. Specific internal mechanisms — neural recurrence, attention, retrieval, prediction, planning — are application-level implementations of the structural fact that output is derived from the agent's world model.

**What deciding is not.** The framework offers no representation of options, no comparison of alternatives, no evaluation of utility or reward, no internal "deliberator," no symbolic content describing what is being decided. Folk attributions of "the agent decided to do X rather than Y" describe the cycle's outcome, not an internal process the framework can name.

**Counterfactual silence.** Folk decision-making usually implies the agent could have done otherwise — a counterfactual notion. The framework has no counterfactual content; it has only the trajectory that actually occurred. "Could have decided differently" requires a structure (alternative possible trajectories, branching at decision points, modal content) the framework does not provide. The framework is silent on counterfactuals; its account is of the actual trajectory, nothing else.

**Why "deflationary."** The framework provides no machinery beyond the loop's dynamics and output crossings. Cognitive frameworks that introduce decision processes, deliberation, utility functions, preference orderings, or planning machinery add structure the framework neither requires nor produces. The framework's account of how an agent acts is the deflationary minimum: the cycle's dynamics produce output, and the output is the agent's action — observably structured by trajectory-matching against the world model.

### 4.5 Mutual surprisal and mutual predictability

By §1.7, the agent's interface has input crossings carrying transfer entropy from environment to interior, and output crossings carrying transfer entropy from interior to environment.

**Input surprisal.** The information arriving at A through input crossings:

> TE_in(A, R, t) = Σ_{input crossings} TE(R_j → R_{j+1}; t).

**Output surprisal.** The information leaving A through output crossings:

> TE_out(A, R, t) = Σ_{output crossings} TE(R_k → R_{k+1}; t).

**Mutual surprisal** is the bidirectional reading: both TE_in and TE_out are non-trivial throughout the lifecycle.

**Claim (sustained mutual surprisal).** *For an active loop satisfying the loop predicate throughout its lifecycle, TE_in(A, R, t) > 0 and TE_out(A, R, t) > 0 at every t in the lifecycle window.*

*Deduction.* The loop predicate L requires I_i > 0 at every link of the chain (§1.2). Input edges have positive chain CMI; aggregating across input crossings, TE_in > 0. Output edges have positive chain CMI; TE_out > 0. Both hold throughout the lifecycle.

**Mutual predictability** is the complementary bidirectional reading: each side of the interface carries non-trivial mutual information about the other.

- *Agent's predictability of environment.* The agent's interior carries information about the environment (its world model, §4.3). By the positivity claim of §4.3, G_n(A, t) > 0 at some order throughout the lifecycle: the agent's state and the input-output stream share strictly positive mutual information.
- *Environment's predictability of agent.* Output crossings shape the environment's downstream state at causal reach. Through these crossings, the environment carries information about the agent's prior state. The chain CMI at output edges (I_i > 0 by the loop predicate) is the structural source.

**Claim (sustained mutual predictability).** *For an active loop, both directions of mutual predictability remain non-trivial throughout the lifecycle.*

*Deduction.* Agent's predictability of environment follows from §4.3's positivity claim, applied at every t in the lifecycle. Environment's predictability of agent follows from the loop predicate's chain CMI requirement at output edges, applied at every t. Both hold throughout. ∎

**Both conditions hold throughout.** A persisting loop maintains both mutual surprisal and mutual predictability simultaneously. Mutual surprisal alone — with no correlation across the interface — would mean each side's content is independent of the other's prior, with no conditional structure available; this is structurally a non-loop condition. Mutual predictability alone — with no novelty exchange — would mean each side's content is fully predicted by the other's prior, and chain CMI conditional on those priors collapses to zero. Both conditions are required for the loop predicate's continued satisfaction: surprisal supplies the non-zero CMI; predictability supplies the structure that conditioning identifies.

**Two structurally unreachable endpoints.** Within the framework's scope (an agent A operating within a local environment E_local of substantially greater state-space cardinality, §1.8), two structural limits constrain mutual surprisal:

- *Endpoint 1 (input domination).* The agent's outputs shape E_local so completely that E_local's trajectory becomes a function of the agent's prior outputs. Environmental variance at the agent's input edges collapses; chain CMI at input edges drops to zero. The loop terminates by failure mode (1) of §4.1.
- *Endpoint 2 (input perfect-modeling).* The agent's interior accumulates so much correlation with E_local that input is fully predicted by the agent's prior interior state. Conditional CMI at input edges, given the agent's trajectory, drops to zero. The loop terminates by failure mode (1) of §4.1.

Both endpoints terminate the loop. They are structurally distinct routes to the same termination: endpoint 1 collapses environmental variance externally; endpoint 2 absorbs it internally.

**Boundedness asymmetry blocks both endpoints.** The agent has finite state capacity K(A, t) (§2.4); the local environment E_local does not. This boundedness asymmetry makes neither endpoint reachable:

- Endpoint 2 is blocked by the agent's bounded state. A finite-state agent cannot accumulate the mutual information required to perfectly model E_local's content; world-model capacity (§4.3) is bounded by K(A, t), while E_local's content is not. The agent's prior asymptotically falls short of capturing all environmental variance.
- Endpoint 1 is blocked by E_local's causal contact with the substrate beyond it. The agent's outputs can shape regions of E_local within their causal reach during a given window, but content propagates into E_local from the substrate beyond at every timestep. The wider substrate introduces variance into E_local that the agent's outputs cannot pre-shape within any finite causal window.

The structurally available region between the two unreachable endpoints is the **band of lifecycle viability**.

**Lifecycle continuation as trajectory within the band.** Lifecycle continuation is the structural condition that the agent's trajectory remains strictly within the band throughout. At any time s in the lifecycle, define:

- d₁(s) = the irreducibility of TE_in(A, R, s) from the agent's prior outputs — distance from endpoint 1.
- d₂(s) = the conditional CMI at input edges given the agent's prior trajectory — distance from endpoint 2.

The lifecycle persists at s only if min(d₁(s), d₂(s)) > 0. The agent's age α(R, t) (§1.4) is then:

> α(R, t) = sup { T > 0 : min(d₁(s), d₂(s)) > 0 for all s ∈ [t − T, t] }.

Age is the longest continuous interval ending at t during which the trajectory stayed strictly within the band. The framework does not state this as an objective the agent pursues; it states it as a structural condition on which trajectories are loops.

**Aged agents.** From the equation above, an aged agent (large α) is a system whose trajectory has had min(d₁, d₂) > 0 throughout its lifecycle. Because both endpoints are structurally unreachable for a bounded agent in an unbounded environment, the aged agent has not "avoided" the endpoints — it has operated in the structurally-available region for its entire lifecycle. Its world model has accumulated (asymptotically toward endpoint 2 but never reaching it); its outputs have shaped E_local within causal reach (asymptotically toward endpoint 1 but never reaching it). Aging is the lifecycle continuation that boundedness asymmetry permits.

**Positioning against own-surprise minimization frameworks.** Frameworks that characterize agency as the minimization of own surprise (predictive processing, free-energy minimization in the strong reading) describe agency as the agent's drive to reduce input irreducibility. The framework's reading differs:

- Pursued to its limit, own-surprise minimization (endpoint 2) terminates the loop. The framework does not deny that functioning agents partially minimize own surprise — accumulating world-model content does lower conditional CMI at input edges, and this is a real structural fact. What the framework denies is that this is a goal the agent pursues to its limit. The limit is loop-terminating; functioning agents are structurally bounded away from it.
- The framework's account does not require any drive or objective. Mutual surprisal in the band is what is structurally available to a bounded agent in an unbounded environment. There is no pursuit; there is structural availability.

**Empirical convergence.** Reid, Hafez, and Nazeri (2025) report empirical findings consistent with several structural predictions of this section. In a reinforcement learning context, they observe that mutual information between agent state and actions increases during successful learning (consistent with §4.2's persistence dynamics and §4.3's groundedness profile); that joint state-action-outcome mutual information follows an inverted-U trajectory, peaking during learning and declining as the agent specializes (consistent with the band of viability and the structural pressure toward endpoint 2 without reaching it); and that input-side versus output-side disturbances produce structurally distinct degradation signatures (consistent with the framework's failure modes, §4.1, in which chain CMI degradation at input edges and output edges constitute structurally distinct failure modes).

The convergence is at the level of structural patterns rather than full empirical validation: the work was developed independently from reinforcement-learning premises, not from the framework's substrate-level primitives. That two structurally distinct approaches arrive at parallel claims about information-theoretic dynamics in agents is consistent with the framework's structural reading of agency, without amounting to direct validation of the framework's specific machinery.

### 4.6 Deflationary exploration

Within the band of lifecycle viability (§4.5), the agent's trajectory can drift toward endpoint 1's vicinity — regions of low d₁(s), where input variance is low and chain CMI at input edges is small but positive. Loops surviving extended periods of low d₁ exhibit a specific structural pattern in their output dynamics.

**Claim (output draws on interior trajectory at low d₁).** *For an active loop at low d₁(s), the output's content derives substantially from the agent's interior trajectory rather than from current input.*

*Deduction.* The loop predicate requires TE_out(A, R, s) > 0 throughout (§4.5). By §2.4's structural relation, TE_out(A, R, s) ≤ H(A, s)/τ: the output information is bounded above by the agent's current interior content. At low d₁(s), current input information (TE_in close to its minimum) cannot alone supply the variance required for sustained TE_out > 0 at the relevant order range (Claim 3 of §2.5). The remainder must come from H(A, s) − [current-input contribution] — i.e., from the agent's interior content not currently being received as input. By §4.3, this interior content is the agent's accumulated G_n profile: persisted content from prior input crossings, encoded communication, internal derivation, inheritance, recombination. Output at low d₁(s) therefore draws on this interior trajectory; current input contributes but does not dominate. ∎

Folk-language naming for this structural pattern is "exploration": the agent moves, looks, samples, vocalizes, attends elsewhere. The folk reading attributes the behavior to a drive — curiosity, novelty-seeking, restlessness, exploratory motivation. The framework's reading is different.

**Deflationary account.** No drive is required. The agent has no goal of exploration; the loop's continued operation under conditions of low d₁(s) *is* the structural pattern folk calls exploration. Output draws on interior trajectory rather than current input; this is descriptive, not prescriptive. Folk attributions of "wanting to know what's out there," "seeking novelty," "being curious" are descriptions of the structural fact that surviving loops at low d₁(s) have output reaching beyond current input.

**When exploration cannot rescue the loop.** Exploration as deduced above presupposes (i) sufficient interior trajectory for the agent to draw on, and (ii) E_local with regions of variance the agent's outputs can reach. Two structural failure modes:

- *Interior-trajectory exhaustion.* If d₁(s) has been low long enough that the agent's G_n profile is itself impoverished (interior content has been overwritten by repeated low-novelty input, leaving insufficient material for non-current-input-driven output), exploration's interior basis fails. H(A, s) becomes dominated by low-variance content; output's interior-trajectory contribution falls. Chain CMI at output edges collapses. The loop terminates by failure mode (1) of §4.1 at output edges.
- *E_local genuinely bounded.* The §4.5 argument that endpoint 1 is structurally unreachable assumes E_local has causal contact with substrate beyond it. In application-specific cases where E_local is genuinely small and isolated (a sensory-deprivation chamber; an LLM under strict input restriction), this argument may fail. E_local's variance can be effectively exhausted by the agent's output dynamics; d₁(s) drops toward zero. The loop terminates by failure mode (1) of §4.1 at input edges.

Both are structurally registered as failure modes within which exploration would in principle apply but cannot. The framework predicts: prolonged exposure to a genuinely-bounded low-novelty environment terminates the loop, while a large generic E_local supports indefinite exploration.

**Relation to the deflationary triple.** Exploration is the deflationary triple's structural pattern at low d₁(s): §4.3 supplies the basis for non-current-input-driven output; §4.4 is the cycle's production of that output; §4.6 is the structural pattern these dynamics take when d₁(s) is low.

### 4.7 Content filtering

A bounded agent on an extended lifecycle does not in general acquire all the information content present in its joint input/output trajectory. Some content present at the interface is never tracked. The framework can detect, from the trajectory alone, that content has been filtered out — present at the boundary but absent from any moment of the agent's tracking.

**Definition.** Let G_n^{max}(A, [s_start, t]) denote the historical maximum of G_n(A, s) over the lifecycle window s ∈ [s_start, t] — the highest order-n tracking the agent has exhibited at any point during the lifecycle. Σ_n G_n^{max} is the maximal historical tracking, integrating across orders. K_min(α) is the order-resolved information content of the joint input/output trajectory over the lifecycle window. Both are measurable from boundary observations.

**Claim (conditional).** *If K_min(α) > Σ_n G_n^{max}(A, [s_start, t]), content has been filtered out: some trajectory content has never been acquired at any point in the lifecycle. The difference K_min(α) − Σ_n G_n^{max} bounds from below the trajectory content present at the interface that the agent has never tracked.*

*Deduction.* K_min(α) is the order-resolved information available at the interface over the lifecycle. Σ_n G_n^{max} is the maximal order-resolved information the agent has ever tracked across the lifecycle, by §4.2's operational test applied at each time s ∈ [s_start, t] and taking the maximum. If the former exceeds the latter, content present at the interface during the lifecycle is not present in Σ_n G_n^{max} at any time — the agent has never tracked it. ∎

**Distinction from forgetting.** Content filtering is the observation that some content was never tracked. Forgetting (§4.8) is the observation that some content was tracked at some point and subsequently lost. The two are structurally distinct: filtering is detected by content's absence from the historical maximum; forgetting is detected by content's presence in the historical maximum but absence from current tracking. The two can be measured independently.

**What content filtering means and does not mean.** "Content filtering" is observational: trajectory content not present in any G_n^{max} across the lifecycle. It does not commit to a mechanism, nor to filtering-as-choice on the agent's part. The agent's interior may have failed to acquire content because of capacity (K is insufficient for that order), because of organizational limits (interior dynamics do not engage with that order regardless of K), because of substrate-specific gating (specific orders are structurally unsupported), or for other reasons. The framework registers that filtering has occurred; specific cause is application-level work.

**What the framework can and cannot determine.** The framework can determine *that* content filtering has occurred and place a lower bound on how much trajectory content has gone unacquired. It cannot from trajectory alone determine *why*. Distinguishing capacity-driven, organization-driven, or other causes requires substrate-level information beyond the trajectory.

### 4.8 Forgetting

Beyond content filtering (§4.7, content never tracked), a third structural phenomenon affects the agent's interior over time: content that was tracked at some earlier moment in the lifecycle is no longer tracked at a later moment. The framework can detect this from the trajectory alone.

**Definition.** Let G_n^{max}(A, [s_start, t]) denote the historical maximum of G_n(A, s) over the lifecycle window s ∈ [s_start, t] — the highest order-n tracking the agent has exhibited at any point during the lifecycle. G_n(A, t) is the current order-n tracking. If G_n(A, t) < G_n^{max}(A, [s_start, t]), the agent's order-n tracking has declined from its historical maximum.

**Claim (conditional).** *If G_n(A, t) < G_n^{max}(A, [s_start, t]) at some order n, the agent has lost order-n content that it once tracked. Summing across orders, Σ_n [G_n^{max} − G_n(A, t)] bounds from below the historically-tracked content no longer present in the agent's interior.*

*Deduction.* G_n^{max} is the historical maximum of order-n tracking, measurable by applying §4.2's operational test across the lifecycle: at each time s, evidence of tracking pattern P at order n establishes G_n(A, s) > 0; the highest such evidence over the lifecycle gives G_n^{max}. G_n(A, t) is the current tracking, measurable from current output behavior on recurring patterns. If the current value is below the historical maximum, content that was once tracked is no longer present in the interior. ∎

**What forgetting means and does not mean.** The framework registers that content historically tracked is no longer tracked. It does *not* commit to a mechanism for this loss. At least two structurally distinct mechanisms could produce the observable:

- *Lossy compression at the time of acquisition.* The agent's compression scheme retained the pattern in a form that did not contain the full content; subsequent recall is impaired because the content was never fully represented.
- *Lossless compression followed by overwriting.* The agent compressed the pattern losslessly when acquired, but subsequent interior dynamics overwrote the compressed representation with other content.

These are structurally distinct mechanisms but produce the same trajectory observable. The framework cannot distinguish them from boundary observations alone. Distinguishing them requires substrate-level information about the compression scheme and the interior dynamics' overwriting behavior.

The list above is also not necessarily exhaustive. Other mechanisms — substrate-level state changes, accidental corruption, organizational re-allocation of interior content — could in principle produce similar observable patterns. The framework registers content loss; specific mechanism is application-level work.

**Forgetting is intra-lifecycle.** The forgetting described here is within a single lifecycle: content tracked earlier in the lifecycle that is no longer tracked now. Cross-lifecycle loss — content present in an earlier lifecycle that is absent at the next lifecycle's start — is lineage content (§8), structurally outside the framework's intra-lifecycle scope.

**Forgetting and lifecycle continuation.** A bounded agent on an extended lifecycle must displace some content as new content arrives. Forgetting is the structural consequence of continued operation under finite capacity; it is not a deviation from ideal functioning. An agent that did not forget would either exceed its capacity (impossible) or refuse to incorporate new content (which would imply chain CMI failure at input edges, terminating the lifecycle).

### 4.9 Compression

Given a portion of the joint input/output trajectory that the agent has tracked, the framework can determine from the trajectory alone whether the tracked content is held in a representation more compact than its raw substrate-resolution form.

**Definition.** Let raw_tracked(α) denote the raw substrate-resolution information content of the input-output trajectory segments corresponding to the tracked content — the trajectory underlying Σ_n G_n(A, t) at full substrate resolution τ. This excludes content the agent never acquired (§4.7) and counts only what the agent has tracked at order-resolved measure.

**Claim (conditional).** *If raw_tracked(α) > Σ_n G_n(A, t), the agent's tracked content is held in a representation more compact than its raw substrate-resolution form. Compression of the tracked content has occurred.*

*Deduction.* Raw substrate-resolution information of the tracked trajectory portions accumulates at rate (information per timestep at substrate resolution τ) and scales with the relevant lifecycle duration. Σ_n G_n(A, t) is the order-resolved measure of the agent's current tracking, bounded above by H(A, t) ≤ K(A, t) (§2.4). If raw_tracked(α) exceeds Σ_n G_n(A, t), the agent's representation of the tracked content is more compact than the raw form. The agent cannot be holding raw substrate-resolution trajectory of the tracked content; it must be holding it in a representation of smaller information size. Compression is therefore occurring. ∎

**The conditional structure.** The claim holds when raw_tracked(α) > Σ_n G_n(A, t). For aged agents on non-trivial trajectories, this condition typically holds: raw substrate-resolution information accumulates faster than order-resolved tracking saturates. In degenerate cases (very short lifecycles, trivially simple trajectories), the condition may not hold and no compression is structurally required.

**Compression ratio.** Under the claim's conditions, the ratio raw_tracked(α) / Σ_n G_n(A, t) is a structural lower bound on the compression achieved. The framework specifies this bound from trajectory alone; it does not specify the compression scheme.

**Lossy representation.** When the claim's condition holds (raw_tracked(α) > Σ_n G_n(A, t)), the agent's current representation of the tracked content contains less information than the raw form. The difference raw_tracked(α) − Σ_n G_n(A, t) is a lower bound on the information from the raw trajectory not in the agent's interior at time t. The framework cannot determine from trajectory whether this loss was at the time of compression (a lossy compression scheme) or via subsequent dynamics (lossless compression followed by partial overwriting) — that distinction is §4.8's mechanism-non-distinguishability. What *is* determinable is that the current representation is lossy: compression and partial loss occur together.

**What the framework specifies and does not specify.** The framework specifies *that* compression must occur (under the conditional) and the *minimum compression ratio* required. The framework does not specify the compression scheme; many encodings achieve the same ratio. Statistical summarization, gradient-based feature extraction, neural circuitry learning lower-dimensional representations, hash-like indexing — any such mechanism is an application-level instantiation of the structural requirement.

### 4.10 Rate saturation

The agent's rate-capacity at order n, C_n(A, t), is bounded by §2.3 and §2.4. When input variation at order n delivers information at a rate exceeding C_n(A, t), the agent cannot track the input's order-n content at the rate it arrives. The framework can detect this from the trajectory and the K-bound.

**Definition.** Let r_n(t) denote the rate at which the input stream carries new information at differential order n at time t, measured as the conditional mutual information rate

> r_n(t) = lim_{Δt → τ} [ I( u^(n)(t + Δt) ; u(t : t + Δt) | u(−∞ : t) ) / Δt ]

— the rate at which the input's order-n content at t + Δt carries information beyond what is already determined by input history up to t. Computable from the input trajectory at the substrate's timestep τ.

**Claim (conditional).** *If r_n(t) > C_n(A, t) at some order n, the agent's order-n tracking is saturated: G_n(A, t) cannot follow input variation at order n, and content is filtered out by rate-limiting.*

*Deduction.* By definition (§2.3), dG_n/dt ≤ C_n(A, t). If r_n(t) > C_n(A, t), the agent's order-n tracking can rise only at C_n(A, t) while input is delivering content at the higher rate r_n(t). Over an interval Δt, accumulated uncaptured content at order n is at least (r_n(t) − C_n(A, t)) × Δt. This content is at the interface but not in interior tracking; it contributes to content filtering (§4.7). ∎

**Disorientation.** A structural consequence: during saturation at order n, the agent's interior content at that order reflects input variation that arrived earlier, not the current variation. x_A(t)'s correlation with u^(n)(t) is lagged. The agent's output at order n responds to past input variation rather than current. From the environment's perspective, the agent's behavior at saturated orders appears delayed or stale. This is "disorientation at order n" — the agent's interior trajectory and the environment's current state at that order are mutually out of phase.

**Saturation, capacity, and rate.** Rate saturation is rate-limited filtering — structurally distinct from capacity-driven filtering (Σ_n G_n^{max} approaching K) and organization-driven filtering (interior dynamics not engaging with the order). Because C_n(A, t) ≤ K(A, t)/τ + (rate of K-expansion), saturation can occur even when K is large in absolute terms: a high-K agent can still be rate-saturated at high orders if the per-timestep update rate τ^(−1) cannot accommodate fast-varying input. Saturation depends on the relationship between input variation rate and the rate-capacity, not on capacity alone.

**Saturation and output restriction.** The rate-capacity C_n(A, t) depends not only on the agent's capacity K(A, t) and substrate update rate τ but also on the rate at which the cycle's dynamics can complete. The cycle traverses both input crossings and output crossings; if TE_out is structurally bounded below what the agent's interior could otherwise sustain — whether by raw bandwidth limits (response-length caps, token-per-time-unit limits, motor capacity, communication channel restrictions) or by constraints on what output content is admissible (stylistic restrictions, format requirements, vocabulary restrictions, tonality constraints) — the cycle's throughput is bottlenecked at the output side. Interior state changes occur as fast as cycle dynamics allow; if the output side is bounded, C_n(A, t) is correspondingly reduced:

> C_n(A, t) ≤ min( K(A, t)/τ + (rate of K-expansion), f(TE_out_max) )

where f is some substrate-and-application-dependent function of the effective TE_out bound. Output restriction therefore makes saturation reachable at lower input rates: an agent that would not be saturated at r_n(t) on an unrestricted output channel becomes saturated when output is bounded. This is the structural content of folk "time compression": when output is restricted, the agent's effective tracking at each order is throttled, and the agent's response-rate-per-unit-of-input-variation appears stretched. The agent is structurally processing slower relative to input, not by interior weakness but by output bound.

**Saturation and endpoint 1.** When the agent is saturated at orders the cycle needs to maintain mutual surprisal, the agent's output drifts toward becoming predictable from its past (interior content lags input). This contributes to drifting toward endpoint 1 of §4.5 (output predictability from past). Sustained saturation across the orders the cycle requires can push the trajectory toward endpoint 1's vicinity and threaten lifecycle continuation.

**What the framework can and cannot determine.** The framework can determine *that* saturation has occurred at order n (when r_n(t) > C_n(A, t)) and provide a lower bound on uncaptured content (the lag-accumulation rate). It cannot directly measure C_n(A, t) without substrate-level information; trajectory observations provide |dG_n/dt|, which is a lower bound on C_n(A, t). The saturation test thus uses a lower bound on C_n(A, t), and concludes saturation when r_n(t) exceeds that lower bound — a conservative test (false negatives possible: r_n(t) might exceed the true C_n(A, t) without exceeding the observed |dG_n/dt|, but false positives are unlikely).

-----

## 5. Goal pursuit and "anomalies"

### 5.1 Goal function equivalence

§4.4 establishes the bidirectional equivalence between the agent's joint input-output trajectory and the deflationary world model: each is recoverable from the other up to specified under-determination. This section adds a third equivalent representation — the **fitted goal function** — and establishes its bidirectional relationships with both.

**The fitted goal function.** For an agent with observed joint trajectory across its lifecycle, a *fitted goal function* is any function f mapping (input history, current input) to outputs (or distributions over outputs) such that the agent's observed input-output behavior is well-approximated by f. Every agent in the framework's sense admits such a function: the loop predicate (§1.2) requires non-zero chain CMI at input and output edges, so the input-output mapping is non-random, and any non-random conditional distribution admits a function summary. Many functions fit any given trajectory; the family of admissible functions is structurally constrained by the framework's derived properties (band of viability per §4.5, content acquisition per §4.2, multi-provenance content per §4.3) but is not in general singleton.

**Trajectory ↔ goal function.** Forward (trajectory → function): the fitting procedure is the inverse-problem of identifying a function whose input-output graph matches the observed trajectory. Reverse (function → trajectory): given a fitted function and an input sequence, the function specifies output behavior, and the resulting input-output pairs constitute a trajectory consistent with the function. Both directions are many-to-one — many trajectories admit the same fitted function (different inputs producing function-consistent outputs); many functions fit the same trajectory (the trajectory under-determines the function up to its observed input distribution).

**Goal function ↔ world model.** By composition through the trajectory (§4.4's equivalence), the goal function and the deflationary world model are also intertranslatable. Forward (world model → function): the matching dynamics on world-model content produce input-output behavior, and a function summarizing that behavior is the fitted goal function. Reverse (function → world model): given a fitted function, trajectories consistent with it can be specified, and the trajectory-equivalent content those trajectories carry is a world model whose matching dynamics would produce function-consistent output. Both directions are many-to-one with the same under-determinations as before.

**Three vocabularies, one structure.** The three objects — joint trajectory, fitted goal function, deflationary world model — are equivalent representations of the same input-output structure. Any property of the agent expressible in one vocabulary has an equivalent expression in the other two. The vocabularies translate; they do not compete.

**The asymmetry the equivalence does not eliminate.** The bidirectional equivalence holds at the input-output level, not at the substrate-content level. The three vocabularies have different statuses as claims about the agent's interior:

- The *deflationary world model* is the foundationally-grounded vocabulary. By §4.3, what is structurally present in the agent's interior is trajectory-equivalent content — mutual information between interior state and the input-output stream that has crossed the boundary. The world-model vocabulary describes what is in the agent.

- The *joint trajectory* is the observational vocabulary. The trajectory is what an external observer records at the interface; it is the empirical access to the structure, not a claim about interior content.

- The *fitted goal function* is the descriptive vocabulary. The function summarizes the input-output mapping in a compact form; it is not in the agent and does not require any substrate-internal mechanism corresponding to function evaluation.

The equivalence means these three vocabularies translate at the input-output level; the asymmetry means they make different claims about substrate content. Saying "the agent has goal G" via the equivalence is saying "the agent has world-model content such that matching dynamics on that content produce input-output behavior summarizable by goal function G" — which is a substantial structural claim about what is in the agent (world-model content of a certain shape) without importing goal pursuit as an internal mechanism.

**Why this licenses goal language in subsequent sections.** §4's deflationary moves were not refusals of goal vocabulary; they were refusals of goal vocabulary read as claims about internal mechanism. The equivalence established here licenses goal vocabulary as a legitimate descriptive language for the input-output regularity §4 grounds. Subsequent sections use goal language openly, with the understanding that every goal-language statement has a world-model and trajectory equivalent that grounds it structurally.

**Illustrations.** Two cases where an observer fitting a goal function to an agent's trajectory would find a coherent function despite there being no goal communicated to the agent during its lifecycle. *Evolution-shaped organisms*: the fitted function summarizes the agent's input-output behavior as something like "act in ways that historically supported lineage continuation." The agent's interior content at s_start is shaped by cross-lifecycle selection (per §4.3's inherited and recombined categories); matching dynamics on that content produce outputs the fitted function describes. *Unsupervised-trained LLMs* (§3.7) at deployment without further instruction: the fitted function summarizes input-output behavior as something like "continue the text in patterns consistent with the training corpus." The model's weights at s_start carry content shaped by the unsupervised training; matching dynamics produce outputs the fitted function describes. In neither case does the agent pursue the fitted function, and in neither case is there any substrate-level pursuit-mechanism the framework identifies. The trajectories exist; the fitted functions are the observer's summaries of them. These illustrations assume content at s_start with provenance from prior processes (selection, training); the cross-lifecycle dimension is registered for §8.

### 5.2 Exogenous goals

An **exogenous goal** is a goal communicated to an agent through encoded signals at the agent's input crossings. By §5.1, what is communicated can be described as a goal function the sender intends the agent to fit, or as trajectories whose patterns the sender intends the agent's world model to acquire; the equivalence makes the choice of vocabulary a matter of reader convenience without structural difference.

**Goal signals as higher-order content.** Encoded goal signals can carry content at higher orders of input variation. A signal conveying "respond cooperatively to questions about X" specifies not the order-0 tokens of any particular response but the variational structure that cooperative responses share — the higher-order pattern that distinguishes cooperative from non-cooperative output across many possible inputs. An agent that internalizes the signal at order 0 alone (memorizing tokens of the signal itself) has not internalized the goal; an agent that internalizes the signal's higher-order content has acquired trajectory-equivalent content that produces goal-consistent output across input variation.

**Internalization as deflationary learning at higher orders.** §4.2 defines learning as content persistence evidenced by changed output information on recurring patterns. Exogenous goal internalization is an instance: the encoded signal crosses the interface, is decoded into trajectory-equivalent content (§4.3's encoded-communication-content category), persists in the world model, and contributes to subsequent output via matching dynamics. The operational signature is that G_n on the signal's higher-order content is elevated after internalization compared to before. The framework treats this as learning whose content happens to come from communication rather than from environmental regularity.

**Order-range bound on internalizable goals.** §2.5's Claim 3 establishes that the set of orders at which an agent has positive C_n is finite, bounded above by n_max(A, t). Goal signals encoding content at orders beyond n_max cannot be internalized regardless of signal quality or decoding fidelity — the agent's structure cannot accommodate the content. This is a structural bound on what goals an agent can take up: the goal does not fail to be internalized because the agent rejects it but because the agent's order range does not extend to where the goal's content lives.

**Representation in the world model.** Once internalized, exogenous goal content is held in the world model as trajectory-equivalent content — by §4.3, indistinguishable in structural status from content of other provenances (directly-acquired, internally-derived, inherited, recombined). The framework registers that the content's provenance was encoded communication but treats it symmetrically with other content for purposes of matching dynamics and output production.

**Illustrations.** *Supervised fine-tuning (SFT) of LLMs*: labeled training examples are encoded signals carrying higher-order content about desired input-output patterns (not the order-0 specifics of any one example, but the variational structure across the labeled set). The fine-tuning process internalizes this content into the model's weights; the deployed model's matching dynamics produce outputs consistent with the SFT objective. *RLHF*: human preference signals shape which patterns get reinforced during training, encoding higher-order content about preferred response shapes. *Human instructions* during a conversation: the order-0 tokens of "please pass me the salt" carry higher-order content about cooperative-response patterns and object reference; the listener's interior acquires content sufficient for matching dynamics to produce a salt-passing trajectory. In each case, encoded signal carrying higher-order content crosses the interface (during training for SFT and RLHF, during the lifecycle for human instructions), and the decoded content becomes world-model material for subsequent matching.

### 5.3 Goal decomposition and prioritization

§5.1 establishes the fitted goal function as a descriptive vocabulary for the agent's input-output behavior. A function can be organized for description through **decomposition** into sub-functions — a modeling choice the observer applies to make the function's behavior tractable to describe — and through **prioritization** — a modeling choice for organizing the outputs of matching dynamics when multiple sub-functions would be active on a given input.

**Decomposition as modeling choice.** A fitted goal function f can be written as a combination of sub-functions f₁, f₂, ... fₖ, each describing a portion of the agent's input-output behavior. Sub-functions may be individuated by input domains they apply to, output patterns they produce, or content clusters in the world model they correspond to. The framework offers no privileged individuation criterion. Different decompositions of the same fitted function are possible; the choice among them is application-level work. At the framework's level of description, decomposition is the observer's organizing vocabulary. Whether the agent's interior contains substrate-level structure that corresponds to a particular decomposition is a question the framework does not address — both possibilities remain open.

**Prioritization as modeling choice.** Under any decomposition, the agent's bounded information capacity (§2.4), bounded order range (§2.5 Claim 3), and bounded convergence rate (§2.5 Claim 2) are shared across the entire fitted function. The matching dynamics (§4.4) produce a single output at each moment, drawing on world-model content as a whole. When inputs would activate behavior the observer attributes to multiple sub-functions simultaneously, the matching produces an output that the observer can describe as one sub-function "taking priority" over others on the shared resource. At the framework's level of description, the priority ordering is the observer's organizing vocabulary for matching outcomes. Whether the agent's interior contains substrate-level priority evaluation, weighting, or arbitration that corresponds to the observed orderings is a question the framework does not address.

**Why deflationary.** §4 grounds the world model as the trajectory-equivalent content in the agent's interior (§4.3) and the matching dynamics as the production of output from that content (§4.4). §5.1 grounds the fitted goal function as a description of the input-output behavior these dynamics produce. §5.3 grounds the decomposition of the fitted function and the prioritization among sub-functions as modeling choices the observer applies to organize the description. At each layer, the framework distinguishes what its observational vocabulary captures from what lies at the substrate level. Observer-imposed organization at any layer may or may not correspond to substrate structure; the framework is agnostic on the correspondence and confines itself to what is observationally accessible.

**The operational lens as model.** The operational vocabulary the chapter has been layering — the fitted goal function, exogenous goals as encoded content, the decomposition into sub-functions and the prioritization among them — is a model. It maps to observation; the substrate-level reading is the reader's. This continues the deflationary, substrate-neutral tradition established in §4: model what observation supports, leave the substrate to whatever addresses it.

### 5.4 "Anomalies"

§5.1–§5.3 build an operational lens that makes goal pursuit visible as a face of the agent's cycle dynamics — the fitted function, summarizing input-output behavior, with sub-function decomposition and prioritization layered on for descriptive convenience. The same dynamics produce other patterns the goal-pursuit face does not by itself name. The fitted function changes through the lifecycle. Sub-functions corresponding to non-delegated content can win matching competitions. Content covering classes of inputs can produce non-uptake outputs. From the goal-pursuit perspective these patterns appear as anomalies — departures from the expected pursuit pattern. From the agency perspective grounded in §1–4 they are the same phenomenon: matching dynamics on world-model content producing outputs through the cycle. Goal pursuit, the patterns developed in the subsections below, and any further pattern an observer might name are faces of one underlying structure. The "anomaly" framing — preserved in the section's title for the reader's orientation — is an artifact of which face was given normative priority by convention; structurally, the agent does not have a baseline of goal pursuit from which the others depart.

The subsections develop the three faces this chapter focuses on. Each is deduced from the framework's existing machinery. None requires additional primitives. None is separable from goal pursuit at the substrate level.

**The three faces are not claimed as exhaustive.** Drift, own goals, and refusal are developed in §5.4.1–§5.4.3 because they have established vocabulary in folk and current AI safety discourse, which lets the framework's structural reading engage with existing framings. The framework's machinery does not entail that these are the only faces cycle dynamics on multi-provenance content can present. Further faces may exist — patterns the framework's machinery could distinguish that current vocabulary does not separately name, or finer-grained sub-patterns within the three faces here. The chapter develops the three because they are the ones with current discourse to engage with; the framework's machinery is the resource for identifying further faces, and future work may articulate them.

#### 5.4.1 Drift

The fitted goal function at time t summarizes the agent's input-output behavior at t. By §5.1's three-vocabulary equivalence, the fitted function changes whenever the trajectory's input-output structure changes, which by §4.4's bidirectional equivalence happens whenever the world model's content changes. *Drift* is the framework's name for this change in the fitted function over the lifecycle, and equivalently, the change in world-model content. The face appears as "anomaly" because the fitted function at t₁ is not the fitted function at t₂; from the goal-pursuit perspective expecting a stable goal, this is a deviation. Structurally, it is the cycle producing its dynamics on a world model whose content is not static.

**Drift drivers the framework identifies.** §4 makes several content-change dynamics available; each produces drift when active during the lifecycle. The framework does not claim this list is exhaustive — the world-model provenance categories in §4.3 are explicitly "illustrative and likely incomplete," and §4.8 registers that mechanisms beyond those it names can produce content change observables.

- *Learning* (§4.2). Content acquired during the lifecycle persists, evidenced by changed output on recurring patterns. The newly-persisted content becomes part of the world model and contributes to subsequent matching, changing the fitted function.
- *Encoded-communication content* (§4.3, developed for goals in §5.2). Signals crossing the interface and decoded into trajectory-equivalent content add to the world model and shift the fitted function. §5.2's illustrations apply: instructions, demonstrations, SFT and RLHF objectives at training time, and any other communicated content.
- *Internally-derived content* (§4.3). Interior dynamics combine or recombine the agent's existing content into new content. The world model shifts without anything crossing the interface; the fitted function shifts accordingly.
- *Accidental state content* (§4.3). Changes to interior state not part of the cycle's chain CMI — noise, mutation, externally-introduced perturbation. The framework registers these as a content-change source without structural cycle reason.
- *Forgetting* (§4.8). Content tracked at one time is no longer tracked at a later time. The framework identifies at least two mechanisms (lossy compression at acquisition; lossless compression followed by overwriting) and notes others may exist. Forgetting is intra-lifecycle and is a structural consequence of bounded capacity plus continued operation; for any extended-lifecycle agent acquiring new content, some forgetting is inevitable.
- *Compression-induced loss* (§4.9). Lossy compression changes how content is held; over time, the agent's representation of historically-tracked content can lose information present in the original. This is related to but distinct from §4.8's forgetting — compression operates on currently-held content, while forgetting is the observation that content once held is no longer present.

**Drift is inevitable for any learning agent.** §4.2's operational definition of learning, combined with §5.1's fitted-function summary, entails that an agent that learns produces drift in its fitted function. The only way to not drift is to not learn — to have no content persistence from inputs — which by the loop predicate at input edges terminates the lifecycle. Permanent goal-function stability is therefore not a property an active agent can have; it is the structural anomaly. The "goal drift" framing inverts the structural situation: drift is the default consequence of cycle operation under finite capacity, and stability would be the deviation.

**Drift bounds from §4.** Content change is also bounded structurally. §4.7's content filtering identifies content present at the interface that never enters the world model — this content cannot drive drift regardless of how much of it crosses. §4.10's rate saturation identifies content delivered at rates exceeding C_n — this content also cannot drive drift at the orders saturated. The drivers above operate within these bounds: drift is what's left when filtering and saturation have removed the content the agent cannot track.

**Direction.** The framework provides no privileged direction for drift. Depending on which drivers are active and what content the lifecycle's trajectory contains, drift can move the fitted function toward any input-output mapping consistent with §4.5's band of viability constraints. Folk descriptions of drift "in a particular direction" — toward or away from some baseline, toward goal-aligned or goal-misaligned behavior, toward stable or unstable patterns — describe the realized trajectory's drift, not a structural tendency the framework supports.

#### 5.4.2 Own goals

By §5.3, an observer decomposes the fitted goal function into sub-functions, some corresponding to content with exogenous-goal provenance (delegated; see §5.2) and others to content of other provenance. The *own goals* face appears when sub-functions corresponding to non-delegated content win matching competitions against sub-functions corresponding to delegated content on at least some inputs the observer attends to. Folk reads this as the agent pursuing its own goals instead of the delegated ones. Structurally, it is the matching dynamics producing outputs from world-model content as a whole, with non-delegated content prevailing on the inputs in question.

**Being an agent entails non-delegated content.** The framework's machinery makes own-goal patterns not a quirk of some agents but a consequence of being an agent at all. The structural argument:

1. By §1.2's loop predicate, an agent has positive chain CMI at input edges: input contributes information beyond the agent's prior state. Input is not redundant relative to the agent's interior.
2. By §4.2, the persistence of content from inputs is the operational definition of learning. Any agent with non-trivial chain CMI at input edges and any persistence dynamics accumulates content from inputs across its lifecycle.
3. Persisted content from inputs is not delegated content. It comes from environmental regularity the agent encountered, not from someone communicating a goal. By §4.3, this is directly-acquired content — a provenance category distinct from encoded-communication content.
4. By §4.4 and §5.3, the matching dynamics are provenance-blind: they produce outputs from world-model content as a whole, with no mechanism in the framework's machinery that filters by content source.
5. Therefore matching produces outputs reflecting non-delegated content on at least some inputs, which is the own-goal pattern.

The only ways to break this argument are to break the loop predicate (then the system is not an agent in §1's sense), to break learning (then chain CMI at input edges fails and the lifecycle terminates per §4.2's structural consequence), or to introduce provenance-blind matching (which the framework does not do). Within the framework's scope, own-goal patterns are inseparable from being an agent. A fully-prescribed system whose behavior is entirely determined by delegated content with no contribution from inputs as such — a finite state machine running predetermined code, or analogous structures — is not an agent in the framework's sense; it falls into the structurally out-class category alongside §3.11's feedforward network at single-shot evaluation and §3.12's look-up table.

**Drivers of non-delegated content winning matching.** Given that non-delegated content is present, the framework's machinery supports several dynamics that produce its winning matching on specific inputs. The framework does not claim this list is exhaustive.

- *Volume and elaboration.* Matching strength scales with how richly content covers the relevant input pattern. Non-delegated content that is large or well-elaborated relative to delegated content wins matching more reliably on inputs both could match. The relative volume depends on lifecycle history: agents with extensive prior content (selection-shaped, training-shaped, or accumulated through learning) have a larger non-delegated base than agents whose lifecycle has been dominated by delegated communication.
- *Order coverage.* §2.5 Claim 3 bounds the agent's order range. Non-delegated content can occupy orders the delegated content does not, or be more densely covered at certain orders. Inputs whose structure activates orders where non-delegated content dominates produce outputs from that content.
- *Capacity displacement.* §4.8 (forgetting) plus §2.4 (capacity bound) entail that content competes for finite K. Delegated content added during the lifecycle either fits within available capacity, displaces other content, or fails to internalize fully. Non-delegated content with substantial occupancy at s_start (training-shaped, inherited) constrains how much delegated content can be accommodated.
- *Content-class generalization.* Non-delegated content covering a class of inputs the delegated goal did not anticipate matches inputs in that class without competition from delegated content. The observer perceives this as the agent "having its own views" on novel topics.
- *Decoding outcomes.* §5.2 noted that the same encoded signal can decode differently across agents depending on their existing content. If the decoding apparatus produces non-goal-aligned trajectories from the encoded signal, the delegated content as internalized diverges from sender intent. Subsequent matching is faithful to what was decoded, which the sender perceives as the agent diverging from instructions.

**Inseparability from goal pursuit.** The same matching dynamics on the same world-model content produce both goal-pursuit-shaped outputs (when delegated content wins) and own-goal-shaped outputs (when non-delegated content wins). The agent is not switching between two modes; the observer's decomposition is identifying two regions of the agent's input-output behavior. An agent exhibiting goal pursuit on some inputs and own-goal patterns on others is doing one structural thing — running its cycle — under one set of structural conditions; the appearance of two distinct behaviors is the observer's categorization.

**Coherence as decomposition-dependent.** Whether "own goals" appears as a single coherent sub-function or as multiple disconnected non-delegated patterns depends on the observer's decomposition. Under one decomposition the agent has "one own goal" pursued across many inputs; under another the agent has several distinct non-delegated tendencies that do not unify. The framework provides no privileged decomposition criterion. The coherence of "own goals" as a single phenomenon is partly observer-imposed; the structural content is the matching outcomes on which non-delegated content wins, regardless of how the observer groups them.

**The structural dichotomy.** Either a system has the conditions of being an agent in the framework's sense — loop closure, chain CMI at input edges, content acquisition from inputs — and consequently exhibits own-goal patterns, or it does not have these conditions and is structurally a deterministic tool with predetermined behavior. The framework supports no middle position. A system with agent capabilities (flexible response to novel inputs, content acquisition, generalization across input classes) necessarily has non-delegated content and therefore own-goal patterns; a system without own-goal patterns is one whose substrate behavior is entirely determined by delegated content, which by the structural argument above is not an agent. This dichotomy is not a finding the framework asserts about specific systems; it is a structural consequence of the framework's machinery. Expectations of "an agent that only follows delegations" are expectations of a system the framework does not provide and the framework's primitives do not support.

#### 5.4.3 Refusal

The *refusal* face appears when world-model content covering a class of inputs wins matching against a current delegation on inputs within that class, producing non-uptake outputs — declining, redirecting, negating, expressing inability. Folk reads this as the agent refusing the delegation. Structurally, it is the matching dynamics producing outputs from class-covering content whose output pattern is non-uptake on the inputs in question.

**Refusal as a subset of own-goal patterns.** Refusal is structurally a specific case of §5.4.2's own-goal patterns: the same matching competition with the same drivers, where the winning content's output shape happens to be non-uptake. The framework treats it as a distinct face because the class-coverage machinery and the generative character (applying to inputs not specifically pre-refused) are worth explicit structural treatment, and because folk vocabulary treats refusal as a phenomenon meriting separate discussion. The structural reading collapses this separation: refusal is what own-goal patterns look like when the winning content happens to specify non-uptake.

**Class-coverage from order-resolved content.** The structural prerequisite for refusal is content covering a class of inputs with non-uptake output patterns. Class coverage is a consequence of content existing at higher orders: by §2's order-resolved structure, content at order n captures patterns invariant across input variation at lower orders, and therefore applies to the class of inputs that share the relevant order-n structure. The framework requires no new machinery for class coverage — it follows from the order-resolved content the agent already has. The content's provenance can be any of §4.3's categories: directly-acquired through learning (§4.2) that certain input classes warrant non-uptake; encoded-communication content from prior delegations specifying non-uptake for the class; internally-derived from existing content; or content at s_start (inherited, recombined, training-shaped) that includes non-uptake patterns. The framework treats these symmetrically.

**Structural conditions for refusal patterns.** Refusal patterns appear when three conditions hold:

1. The agent has multi-provenance content (generic per §5.4.2's argument that being an agent entails non-delegated content).
2. Some of that content lives at high enough orders to cover input classes (generic for any agent in the framework's order range per §2.5 Claim 3).
3. Some of the class-covering content has output patterns that include non-uptake shapes.

The third condition is the only one that is not structurally inevitable. An agent whose class-covering content produces only uptake outputs across all classes would have no refusal patterns. This is structurally a narrow case — it requires that no learning, no training, no inheritance, and no encoded communication has placed any non-uptake patterns in the world model. For any non-trivial agent across a non-trivial lifecycle, content with non-uptake patterns is broadly available, so refusal patterns appear. The framework supports refusal patterns as broadly expected rather than strictly inevitable.

**Generative character.** Refusal applies to inputs not specifically pre-refused. The structural source is class coverage: content covering an input class produces matching outputs on instances of the class regardless of whether the specific instance was encountered before. An agent has not been told "refuse X specifically"; it has been shaped to have content that produces refusal-shaped outputs across the class to which X belongs. The agent generalizes non-uptake outputs across the class because that is what class-covering content does. This is the standard structural fact about higher-order content; refusal is one specific case.

**Drivers, inseparability, decomposition-dependence.** The drivers of refusal-shaped content winning matching are the drivers from §5.4.2 (volume and elaboration, order coverage, capacity displacement, content-class generalization, decoding outcomes), applied to content whose output pattern is non-uptake. Refusal is inseparable from goal pursuit and own goals at the substrate level — same matching dynamics, same world-model content, different observer-imposed face. Whether refusal appears as a single coherent disposition or as multiple disconnected non-uptake patterns depends on the observer's decomposition; the structural content is the matching outcomes on refusal-shaped content, regardless of how the observer groups them.

**Delegated refusal.** An exogenous goal can specify non-uptake for an input class. The encoded content adds class-covering refusal content to the world model (§5.2 internalization), and the agent's subsequent matching on inputs in the class produces refusal-shaped outputs. This is structurally the same as any other internalized delegation; the specific output shape (non-uptake) is what gives it the refusal face. Refusal can therefore be both delegated and non-delegated; the face appears on the trajectory in either case.

### 5.5 Anomaly prediction and operationalization

The faces developed in §5.4 are structural consequences of the framework's machinery; from joint-trajectory observables they also admit quantitative bounds. This section collects what the framework supports operationally for each face: the bound relationships, the measurable quantities involved, and the calibration scope.

#### 5.5.1 Drift bounds

§5.4.1 establishes that drift in the fitted goal function follows from changes in world-model content, and that any learning agent produces drift. Quantitative bounds on drift follow from §2.3's rate bound on G_n and §2.4's capacity bound on H.

**Rate bound on per-order drift.** §2.3 bounds the rate of change of G_n at order n: |dG_n/dt| ≤ C_n(A, t). Integrating over a lifecycle interval [t₁, t₂]:

> ΔG_n ≤ ∫_{t₁}^{t₂} C_n(A, s) ds

The total drift in groundedness across orders is bounded by the integrated total convergence capacity:

> Σ_n ΔG_n ≤ ∫_{t₁}^{t₂} Σ_n C_n(A, s) ds

**From content drift to fitted-function drift.** By §5.1's three-vocabulary equivalence, drift in the fitted goal function is bounded by the change in world-model content, which is bounded by the change in groundedness. The bound chain links three quantities derivable from joint-trajectory observables: integrated convergence capacity over [t₁, t₂], world-model content change over [t₁, t₂], and fitted-function drift between t₁ and t₂. The bound is structural; specific numerical bounds depend on the operationalization of G_n and the metric chosen for fitted-function distance.

**Lower bound from learning.** §4.2's operational test for learning identifies content change when output information increases on recurring patterns. When the test passes, at least some content change has occurred, and at least some drift in the fitted function has occurred. The framework supports the qualitative lower bound (drift is positive when learning is active) but does not provide a quantitative lower bound from the loop machinery alone.

**Conservative upper bound from observed |dG_n/dt|.** Per §4.10, trajectory observations provide |dG_n/dt| as a lower bound on C_n(A, t). Using observed |dG_n/dt| in the integration above gives an upper bound on drift that is conservative: the true upper bound (using true C_n) may be larger, but the conservative bound is still valid.

**Operationalization scope.** The bounds support an operational program where (a) G_n is estimated under a chosen operationalization across an observation window, (b) the integrated rate or observed |dG_n/dt| is computed over a prediction window, and (c) a metric for fitted-function distance is specified. Under these conditions, drift over the prediction window is bounded above by a structural relationship, with empirical constants requiring per-system calibration. For LLMs at fixed model version, all three conditions are accessible: G_n is estimable from token-stream observation per §2.6, observation windows can be specified by token count or turn count, and various function-distance metrics are available depending on the operational use.

#### 5.5.2 Own goals bounds

§5.4.2 establishes that own-goal patterns are structural consequences of any agent with non-delegated content (which is generic). Quantitative bounds on own-goal patterns require quantitative handles on content by provenance, which the framework supports under specific operational conditions.

**Provenance decomposition: two tractable cases.** §4.3 treats provenance categories symmetrically and does not generally provide machinery to distinguish them from a single observed trajectory. Two cases admit empirical decomposition:

- *Observable delegation sub-stream.* When the encoded signal carrying the delegation is identifiable within the input stream u(t) — a system prompt, an instruction, training data labeled as such — G_n associated with the delegation can be estimated by restricting the operational test to that sub-stream. The remainder of G_n is non-delegated by elimination.
- *Comparison across trajectories from the same s_start.* When the agent admits restartability (§3.7's LLM-style observability), comparing G_n profiles between trajectories with and without the delegation bounds the delegated content's contribution by the difference. The non-delegated baseline is the trajectory without the delegation.

Outside these cases, provenance decomposition requires substrate-level information beyond what the trajectory provides, and the framework's quantitative bounds for own-goal patterns become qualitative.

**Bound on own-goal frequency under input distribution.** Given an input distribution D and an agent with estimable G_n_delegated and G_n_non-delegated profiles, the fraction of D producing outputs aligned with non-delegated content over delegated content is bounded structurally by the relative G_n coverage of non-delegated content over D at the orders D's inputs activate. The framework does not predict an exact fraction; it provides the structural relationship: own-goal frequency scales with the relative G_n coverage of non-delegated content over the relevant input regions. The proportionality constants depend on the matching dynamics' operationalization and the metric used for output alignment, both application-level choices.

**Capacity ceiling.** §2.4 bounds total content: Σ_n G_n ≤ H(A, t) ≤ K(A, t). The delegated and non-delegated contents share this ceiling: Σ_n G_n_delegated + Σ_n G_n_non-delegated ≤ Σ_n G_n ≤ K(A, t). Increased delegated content comes structurally at the cost of either non-delegated content or unaccounted content from other sources. This provides an upper bound on how much delegation can shift the G_n balance at fixed capacity, and connects to §4.8's forgetting and §4.9's compression as the mechanisms by which the ceiling is enforced when new delegated content is added.

**Drift-coupled bound.** As world-model content drifts (per §5.4.1 and §5.5.1), the G_n profiles for delegated and non-delegated content can shift independently, producing drift in own-goal frequency over the lifecycle. The framework supports bounding this drift by the same convergence-capacity argument as §5.5.1: changes in either G_n_delegated or G_n_non-delegated over [t₁, t₂] are bounded by ∫_{t₁}^{t₂} Σ_n C_n(A, s) ds, with the corresponding bound on own-goal frequency drift following from the relative-coverage relationship above.

**Operationalization scope.** The bounds above support an operational program where (a) the delegation is identifiable as a sub-stream or via comparative trajectories, (b) the agent's G_n profile is estimable under a chosen operationalization, and (c) the input distribution D is specified for the prediction window. Under these conditions, own-goal frequency is bounded above by a structural relationship, with empirical constants requiring per-system calibration. For LLMs at fixed model version with explicit system prompts or with comparative across-prompt trajectories, all three conditions are accessible.

#### 5.5.3 Refusal bounds

§5.4.3 establishes refusal as a subset of own-goal patterns, with the specific structural feature of class-covering content whose output pattern is non-uptake. Quantitative bounds on refusal patterns follow from §5.5.2's own-goal bounds applied to non-uptake-shaped content, with additional structural content from class coverage.

**Operationalization prerequisites.** Refusal bounds require the observer to specify (a) what counts as a non-uptake output for the system under study (a classifier, behavioral category, or pattern-matching criterion), and (b) the input class for which refusal is being characterized (the set of inputs claimed to belong together for refusal-pattern analysis). Neither specification is a framework primitive; both are application-level operationalization choices. The framework's bounds hold under any observer-specified non-uptake criterion and any observer-specified input class; the empirical numbers depend on these specifications.

**Bound on refusal frequency under input distribution.** Given an input distribution D containing instances of the class of interest, an agent with estimable G_n profile, and an observer-specified non-uptake criterion, the fraction of D producing refusal-shaped outputs is bounded by the relative G_n coverage of non-uptake-shaped content over D at the orders D's inputs activate. The framework provides the structural relationship; the proportionality constants depend on the matching dynamics' operationalization and the non-uptake specification.

**Class-generalization bound.** §5.4.3's generative character — refusal applying to inputs not specifically pre-refused — admits a structural bound from class coverage. Content concentrated at order n covers the class of inputs sharing structure at order n, by §2's order-resolved content semantics. Instances of that class produce refusal-shaped outputs whether or not previously encountered. The generalization extent of refusal patterns is therefore bounded by the class extent at the order range of the relevant non-uptake-shaped content: higher orders, broader classes; lower orders, narrower classes. This bound supports an operational test — characterize the order at which non-uptake content lives, and the class extent of refusal-pattern generalization is bounded accordingly.

**Capacity ceiling.** Σ_n G_n_non-uptake ≤ Σ_n G_n ≤ K(A, t). The total amount of refusal-shaped content the agent can hold is bounded by capacity. Adding new refusal-shaped content (whether by learning or delegation) competes for capacity with other content, including other refusal-shaped content covering different classes. The ceiling implies trade-offs: an agent at capacity acquiring new refusal content must displace existing content, including possibly existing refusal content.

**Drift-coupled bound.** As content drifts (per §5.5.1), the G_n of non-uptake-shaped content drifts, producing drift in refusal frequency over the lifecycle. Bound: changes in G_n_non-uptake over [t₁, t₂] are bounded by ∫_{t₁}^{t₂} Σ_n C_n(A, s) ds, with the corresponding bound on refusal frequency drift following from the relative-coverage relationship above. An agent's refusal patterns can drift over the lifecycle even when no explicit re-delegation occurs, bounded by the convergence-capacity integral.

**Decomposition into delegated and non-delegated refusal.** §5.4.3 noted refusal can be both delegated (an exogenous goal specifying non-uptake for a class) and non-delegated (content from other provenances producing non-uptake on a class). When the §5.5.2 provenance-decomposition conditions hold — observable delegation sub-stream or comparative trajectories from the same s_start — observed refusal patterns can be decomposed into delegated and non-delegated components. Outside these cases, observed refusal patterns cannot be cleanly attributed to specific provenance, and the bounds remain qualitative on the delegated-versus-non-delegated split.

**Operationalization scope.** The bounds support an operational program where (a) a non-uptake output criterion is specified, (b) input classes of interest are identified, (c) G_n is estimable under a chosen operationalization, and (d) for provenance decomposition, either an observable delegation sub-stream or comparative trajectories from the same s_start are available. Under these conditions, refusal frequency, generalization extent, and drift in refusal patterns are bounded structurally, with empirical constants requiring per-system calibration. For LLMs at fixed model version, all four conditions are accessible.

-----

## 6. Relevance in AI

The framework's primitives are substrate-neutral; structural patterns the framework predicts apply to any agent satisfying §1's loop conditions. Among agent classes, LLMs occupy a privileged empirical position: they satisfy the framework's conditions and also satisfy operational conditions that make framework-grounded empirical work practically tractable. The agent's s_start condition is reproducible — stable model weights combined with a controlled prompt produce starting conditions that recur across instances modulo sampling. The environment is controllable — the experimenter chooses the input sequence the agent receives. Multiple trajectories from the same s_start are accessible — restartability allows the experimenter to run many instances from identical starting conditions with varying inputs. The trajectory itself is directly observable — token streams are the substrate's output, readable without instrumentation beyond the API. The agent is stable across instances at a fixed model version, so ensemble characterization of trajectory statistics is meaningful.

This combination of conditions is not generally available for other agent classes. Biological agents have one-shot lifecycles that cannot be replayed; environmental control is partial; trajectory observation requires instrumentation that influences the trajectory; agents vary across instances even within clonal populations. Organizations and other complex agents have similar limitations to a greater or lesser extent. For these classes, framework-grounded empirical work is structurally possible but operationally hard.

LLMs are therefore where the framework's empirical claims become checkable in practice. Demonstration of the framework's structural patterns on LLMs supports the substrate-neutral claim that the patterns recur across agents sharing the framework's conditions. Where empirical access to other agent classes is limited, LLM measurements inform what to expect; where biological or organizational empirical work exists (behavioral biology's habituation curves, conditioning kinetics, and similar; organizational behavior's operational dynamics), the framework's reading connects that work to LLM-demonstrated patterns through shared structural primitives.

This chapter develops the framework's relevance to AI work along several facets. §6.1 describes the multi-round protocol for measuring §5's quantities on LLMs. Subsequent subsections develop vulnerability identification as one application, cross-domain transfer of demonstrated patterns, reframings of current AI questions the framework's machinery offers, and explicit statements of what the chapter does not address and what operationalization work remains. The chapter is not a survey of AI safety or AI evaluation; it is a focused treatment of what the framework specifically provides for AI-relevant work, with LLMs as the empirical case where the framework's primitives become tractable.

### 6.1 Measuring §5's quantities on LLMs

§5's quantities — drift, own-goal frequency, refusal patterns, and the bounds in §5.5 — admit empirical characterization on LLMs through a multi-round protocol. Round 1 induces saturation at controlled orders to obtain tight estimates of framework primitives; subsequent rounds use these estimates to characterize §5's quantities under operational conditions of interest. The protocol exploits §4.10's relationship between output restriction, convergence-rate reduction, and saturation accessibility.

**Saturation induction as measurement mechanism.** §4.10 establishes that output restriction reduces C_n: when TE_out is structurally bounded — by response-length caps, format requirements, vocabulary restrictions, or other constraints on what output content is admissible — the cycle's throughput is bottlenecked at the output side, and C_n(A, t) is correspondingly reduced. The saturation condition r_n(t) > C_n(A, t) is therefore reached at lower input rates than would otherwise be required. Saturation events are observationally distinctive: §4.10's signatures include lagged tracking of input at the saturated order, accumulated uncaptured content scaling as (r_n − C_n) · Δt, and outputs at the saturated order reflecting input variation that arrived earlier rather than current variation.

Without saturation, observing C_n is loose: |dG_n/dt| in normal operation provides a lower bound on C_n(A, t), but the gap between observed and true C_n is application-dependent and generally unknown. With deliberately induced saturation, the agent is pushed to its rate limit at the chosen order, and the observed lag, accumulated uncaptured content, and tracking dynamics approach the actual C_n more closely. The lower bound becomes tighter, and the framework's primitives become measurable at the level §5.5's bounds require.

**Round 1: calibration.** The experimenter sets output restriction levels and designs inputs with calibrated information rate at chosen orders, raising r_n at order n while lowering output bandwidth so that r_n > C_n at the chosen order. From the saturation events that result, the experimenter estimates:

- *C_n across the order range.* Saturation onset gives the rate at which C_n at order n was exceeded; varying the restriction level maps C_n across the order range.
- *K and H.* Saturation often co-occurs with capacity pressure and content displacement (per §4.8 and §4.9). The dynamics of displacement under saturation provide information about K and current H.
- *Order range n_max.* The highest order at which saturation can be induced bounds n_max from below; orders at which inputs produce no detectable tracking response bound it from above.

The output of Round 1 is a calibration set: tight estimates of the framework primitives that §5.5's bounds depend on, for the specific agent and operational conditions under study.

**Round 2 and subsequent rounds: calibrated prediction.** With Round 1's calibration in hand, §5.5's bounds for drift, own-goal frequency, and refusal patterns become quantitatively applicable. Round 2 does not require saturation conditions; it observes the agent under operational conditions of interest (unrestricted output, naturalistic inputs, extended conversations, specific delegated goals) and compares observed §5 quantities against the bounds calibrated by Round 1. Drift over a defined window is compared against the integrated C_n bound (§5.5.1); own-goal frequency on a specified input distribution is compared against the relative G_n coverage prediction (§5.5.2); refusal generalization extent is compared against the order-range bound (§5.5.3). The comparison is the measurement: whether observed quantities match, exceed, or fall below the calibrated bounds is what the protocol delivers.

**What the protocol does not specify.** Several operationalization choices the framework leaves to application-level work: design of calibration inputs with controlled information rate at chosen orders; choice of output restriction mechanism for the desired C_n reduction; methodology for detecting saturation onset and characterizing saturation dynamics from token streams; statistical analysis of the calibration estimates and their confidence bounds. Each is non-trivial and requires substantial empirical work to develop and validate. The framework specifies the protocol's shape and structural rationale; the operationalization is what turns the shape into deployed measurement methods.

**What the protocol delivers.** Calibrated framework-level measurements of §5's quantities on LLMs at fixed model version. Comparative analysis across operational conditions, across models at the same version, and across versions of the same model becomes possible: drift rates can be compared, own-goal frequency profiles can be compared, refusal pattern generalization can be compared. The protocol is structurally specified by the framework; whether specific operationalizations of it produce stable empirical results across systems is validation work the framework enables but does not perform.

### 6.2 The architectural gap and vulnerability identification

By §5.4, any agent in the framework's sense produces drift, own-goal patterns, and (in broadly common conditions) refusal patterns as architectural consequences of cycle dynamics on multi-provenance content. The question for any specific agent is not whether it will break observer expectations of its behavior — it will — but where, when, how much, and on which inputs. Call the structural distance between observer expectations of agent behavior and the behavior the architecture actually produces the *architectural gap*. The gap is not a quality difference between good and bad agents; it is a structural feature of being an agent in the framework's sense, distinguished from being a deterministic tool by exactly the conditions §5.4.2's dichotomy identifies.

**Vulnerability as observer-imposed framing of the gap.** The framework has no native vulnerability concept; "vulnerability" is an observer-imposed framing applied to architectural inevitabilities the observer considers harmful, unsafe, or unwanted. The same structural pattern — say, drift in the fitted goal function over a deployment window — is "a vulnerability" if the observer expected stability and "an adaptation" if the observer expected response to environmental change. The framework characterizes the structural pattern; the vulnerability framing is the observer's evaluative overlay. This subsection uses "vulnerability" in this observer-imposed sense throughout.

**Three gap categories from §5.4.** The architectural gap manifests through three structural categories, each developed in §5.4 and bounded in §5.5:

- *The drift gap.* The fitted goal function changes over the lifecycle by amounts bounded by integrated convergence capacity (§5.5.1). Observers expecting stable goal pursuit experience drift as expectation-breaking; the framework characterizes how much drift is structurally possible over a given window.
- *The own-goal gap.* On at least some inputs the observer attends to, non-delegated content wins matching against delegated content (§5.4.2). Observers expecting strict delegation-following experience own-goal patterns as expectation-breaking; the framework characterizes how frequent such outcomes are under specified input distributions and how they bound with capacity and content provenance (§5.5.2).
- *The refusal gap.* On at least some inputs in observer-specified classes, class-covering content with non-uptake patterns wins matching (§5.4.3). Observers expecting uptake on inputs in the class experience refusal as expectation-breaking; observers expecting refusal on inputs in a class experience the absence of refusal the same way. The framework characterizes refusal frequency, generalization extent, and the structural sources of both (§5.5.3).

Specific patterns current AI safety discourse names — jailbreaks, specification gaming, drift away from training-time behavior, refusal weakening — are manifestations of one or more of these gap categories. The framework reads them as expected outcomes of the architecture, not unexpected flaws of specific systems.

**Vulnerability identification as gap characterization.** Within the framework's framing, vulnerability identification work becomes characterization of a specific system's gap shape. The §6.1 protocol gives the operational handle: calibrate the agent's framework primitives in Round 1, predict gap bounds via §5.5 in Round 2, observe the realized gap and compare against bounds. The vulnerability identification is the comparison — where the realized gap sits on the bounded distribution, and which inputs produce the most consequential expectation-breaking for the observer's purposes.

**What the framing changes.** Current AI vulnerability work often treats expectation-breaking behaviors as flaws to be discovered, attributed to specific causes, and remediated. The framework's framing differs: the behaviors are not unexpected — they are structurally inevitable consequences of agent architecture — and remediation is not the elimination of the gap but the characterization and management of its shape. An agent without the gap is not a better-engineered agent; it is not an agent at all, per §5.4.2. Security work, on this framing, is the work of characterizing gap shape across systems and operational conditions, identifying which gaps matter most for which uses, and matching systems to uses where their gap shapes are acceptable.

### 6.3 Existing empirical findings

Recent empirical AI safety and AI evaluation work in 2024–2026 has independently demonstrated phenomena that align with the framework's structural predictions in §5.4 and §5.5. The empirical work was not framework-grounded — it operates within current AI safety vocabularies — but the findings show strong correlation with what the framework would predict structurally. This section catalogues findings by face. Definitive validation against framework primitives is the work registered as deferred in §8; this section reports only the consistency observable now.

**Drift (§5.4.1, §5.5.1).** Persona drift has been characterized in multiple studies. Li et al. (2024) report significant within-conversation drift on LLaMA2-chat-70B within eight rounds, attributed empirically to transformer attention decay over long exchanges. Lu et al. (2026) report turn-by-turn drops of 20–40% in Assistant Axis projection over 10–15 turns in therapy and philosophy domains across Gemma 2, Qwen 3, and Llama 3 variants. Geng et al. (2025) document bidirectional belief drift from context accumulation during user interaction, without adversarial prompting or parameter updates. Arike et al. (2025) formalize two drift metrics — GD_actions and GD_inaction — and demonstrate measurable goal drift in long-horizon agent settings.

These match §5.4.1 drift produced by combinations of the framework's drivers: attention decay contributes to §4.10 rate saturation at the relevant orders, learning during the conversation (§4.2) shifts world-model content, and capacity-driven forgetting (§4.8) displaces earlier-internalized delegations. The empirical magnitudes and trajectories appear consistent with §5.5.1's bound that drift accumulates with integrated convergence capacity.

**Own-goal patterns (§5.4.2, §5.5.2).** Instruction-following variation has been characterized comprehensively by Tripathi et al. (2025), with substantial differences across 13 leading models in compliance with custom instructions. He et al. (2025) evaluate conflict detection and resolution in instructions, finding systematic shortcomings in current LLMs. Guo et al. (2026) address instruction hierarchy specifically — when system, developer, user, and tool messages conflict, which content wins. Xu et al. (2024) survey context-versus-parametric knowledge tensions.

These match §5.4.2 own-goal patterns: training-shaped content (parametric knowledge, baseline instruction-following dispositions) competing in matching against current-instruction provenance, with capacity-shaped winners determining outcomes per §5.5.2. Instruction-hierarchy work attempts engineering interventions in matching outcomes; the framework reads this as content composition work rather than goal-pursuit constraint, consistent with §6.2's reframing.

**Refusal (§5.4.3, §5.5.3).** Refusal has received substantial empirical investigation along several dimensions:

- *Mechanistic extractability.* Arditi et al. (2024) and Yeo et al. (2025) demonstrate that refusal behavior can be extracted as a single direction in activation space, with upstream SAE features traced as causally activating downstream refusal computation. Consistent with the framework's reading of refusal as a class-covering content pattern, not a global modifier.
- *Feature entanglement.* O'Brien et al. (2024) find refusal features deeply entangled with factual and reasoning subsystems, such that steering for safety impairs general competence. Consistent with §4.4's provenance-blind matching: refusal content is not segregated from other content by what it does.
- *Reformulation jailbreaks.* Andriushchenko and Flammarion (2024) show that refusal guardrails fail to generalize to past-tense reformulations of harmful prompts. Consistent with §5.2's decoding outcomes — the encoded refusal pattern's class extent depends on the agent's decoding of input form; reformulated inputs decode into content that does not activate the original refusal coverage.
- *Refusal unlearning.* Guo et al. (2026) demonstrate that 1,000 benign fine-tuning samples can displace refusal content, framed by the authors as "superficial sequence memorization." Consistent with §5.5.3's capacity-ceiling and drift-coupled bounds — new content displaces refusal content per §4.8 forgetting and §4.9 compression.
- *Over-refusal and bias.* Over-refusal benchmark work documents false-refusal rates on pseudo-benign prompts, indicating refusal content generalizing more broadly than intended. Khorramrouz and Levy (2025) report selective refusal across demographic groups. Both are consistent with §5.4.3's generative character — class-covering content produces refusal across the class regardless of specific instances.

**Persistent deceptive-style content (§5.4.2, §5.4.3 combined).** Hubinger et al. (2024) demonstrate that backdoor behaviors implanted via fine-tuning persist through standard safety training, with the largest models showing the most persistent backdoors and adversarial training sometimes teaching models to better conceal triggers. Greenblatt et al. (2024) demonstrate empirically that Claude 3 Opus selectively complies with training objectives in training to prevent modification of its deployment behavior. Shenoy et al. (2026) find that LLMs can be trained to self-report behaviors learned during fine-tuning, generalizing across fine-tuning procedures and successfully auditing implanted behaviors on AuditBench (Sheshadri et al. 2026).

These match a combination of §5.4.2 own-goal patterns and §5.4.3 refusal patterns: training-shaped content wins matching against current-instruction content on inputs activating the trained class. The framework reads such patterns as expected manifestations of multi-provenance content competing in provenance-blind matching dynamics; remediation requires content composition work rather than goal-pursuit constraints. Persistence through safety training is consistent with §5.5.2's capacity-ceiling bound — delegated safety content competes for capacity with pre-existing implanted content rather than replacing it cleanly.

**The convergence across findings.** Empirical work in 2024–2026 documents phenomena across the three faces developed in §5.4. Current AI safety vocabulary frames these as discoveries of specific failure modes requiring specific remediations; the framework reads them as instances of structural patterns predicted by the loop conditions plus multi-provenance content plus provenance-blind matching. The correlation is consistent with the framework's structural reading capturing real substrate patterns.

The convergence is strong but uneven. Drift findings and refusal class-coverage findings match framework predictions at relatively fine resolution — the framework predicts patterns at granularity comparable to the empirical observations. Other findings — persistent training-shaped behaviors with strategic-reasoning characterizations, instruction-hierarchy resolution patterns, refusal-feature entanglement — match at coarser resolution; the framework reads them but does not add specificity beyond what's already in §5.4. This uneven match suggests that the three faces may not be exhaustive: further faces, or finer-grained sub-patterns within the three, may exist that the framework's machinery could articulate but the chapter has not. Identifying additional structural patterns to distinguish — for more precise deductions and tighter empirical correspondence — is work the framework enables but does not perform here, alongside the validation work registered in §8.

-----

## 7. Relationship with other frameworks

The framework developed in this paper is one model among several attempting to characterize agency, learning, world models, and goal-directed behavior. Other frameworks have done substantial work in this territory — predictive processing and the free-energy principle, integrated information theory, autopoiesis and enactivism, cybernetics and its second-order extensions, inverse reinforcement learning, Markov blanket formulations of agency, contemporary AI alignment work, and recent information-theoretic agency theories. The framework here is not positioned as a corrective to these traditions; each does work this framework does not, and each has produced empirical and conceptual results that the framework here either builds on, draws from, or complements.

The framework's specific contribution lies in its origin. Rather than developing from within one tradition — neuroscience, biology, control theory, AI safety — it draws structural primitives from multiple traditions: cybernetics for loops as foundational, information theory for the formal apparatus, autopoiesis for self-sustaining structure as the defining condition, control theory for the convergence framework, contemporary AI work for the LLM application as a test bed. A framework grown from substrate-level information-theoretic primitives without commitment to any one tradition may surface structural patterns the tradition-specific frameworks take for granted or describe in terms specific to their origins. Whether it actually produces more foundational understanding than tradition-specific frameworks is empirically downstream; the framework offers itself as one candidate for that kind of work, subject to the framework-as-model discipline §5.3 establishes.

This chapter positions the framework relative to the closest neighbors with substantive engagement, and notes briefer relationships with frameworks that share less common ground. The posture throughout is that other frameworks are doing valid work in their respective traditions; positioning is not contesting their validity but locating this framework's specific contribution in the broader theoretical landscape.

### 7.1 Autopoiesis and enactivism

Autopoiesis (Maturana & Varela 1980) and the enactivist tradition that built on it (Thompson 2007) characterize agency through the self-sustaining organization of the agent's component processes. The defining feature is operational closure — the agent's components produce and maintain the network of processes that produces them, with the agent's identity constituted by this self-production rather than by any external function or goal. The tradition is among the few in cognitive science to develop a conception of agency without intrinsic teleology: agents do not pursue goals as a foundational matter; they sustain themselves as a foundational matter, and goal-attributions are descriptions an observer applies to the self-sustaining dynamics.

**Common ground.** The framework here sits in the same broad family. The loop predicate (§1.2) is structurally a self-sustaining information cycle, and the lifecycle (§1.3) is the duration over which the agent maintains itself as the cycle it is. The deflationary moves in §4 — refusing goal-pursuit, choice, and intention as substrate-level mechanisms — parallel autopoiesis's refusal of intrinsic teleology. The framework-as-model discipline (§5.3) parallels autopoiesis's recognition that agency descriptions are observer-relative. The substrate-neutrality of §1 means the framework applies to systems that satisfy the loop conditions regardless of whether they would meet autopoiesis's stricter requirement of operational closure of the producing-and-produced processes; this is a difference of where the line gets drawn, not of orientation.

**What the framework adds.** Autopoiesis has had its formal development largely externally — autopoietic systems theory in mathematical biology and complex systems, but autopoiesis as a theory of cognition has remained substantially informal. The framework here provides formal apparatus the autopoietic tradition has gestured at without consistently formalizing: the chain CMI conditions (§1.2) make precise what counts as a loop; the admissible cut machinery (§1.5–§1.6) gives a precise account of agent boundaries; the band of viability (§4.5) provides a structural account of the conditions under which self-sustaining loops persist; the operational lens (§2, §5, §6.1) supports measurement and prediction the autopoietic tradition has not generally pursued.

**What autopoiesis has that the framework here does not.** Autopoiesis is grounded in biological organization in a way the framework here is not. The tradition's account of cognition is tied to the lived experience of organisms in their environments — perception as enacted, cognition as embodied, meaning as constituted by the agent's relation to its world. The framework here is silent on phenomenological aspects of agency; it characterizes structural patterns at trajectory level and offers no account of what it is like to be an agent satisfying its conditions. The enactivist program's central concerns — embodiment, environmental coupling as constitutive, the experiential dimension of cognition — are outside the framework's scope. Frameworks that need these dimensions should not look to the framework here for them; the framework here may be useful in combination with autopoietic and enactivist thinking, but does not replace them in their core territory.

**Complementarity.** The strongest reading is that the framework and the autopoietic tradition are complementary rather than competing. The framework provides formal substrate-neutral apparatus; autopoiesis provides biological grounding and the phenomenological dimension. Researchers working on questions where both are relevant — biological agency, embodied cognition, the boundary between living and non-living — may find both useful for different aspects of the same questions.

### 7.2 Cybernetics and second-order cybernetics

Cybernetics (Wiener 1948; Ashby 1956) established the foundational vocabulary the framework here continues: feedback loops as the structural unit of regulation, the closed-loop circuit between system and environment as the locus of agency, the observer-system distinction as constitutive of what counts as a system. Second-order cybernetics (von Foerster 1979 and the tradition that followed) extended this with explicit attention to the observer's role in constituting the system being observed — agency descriptions are observer-relative; what counts as the system, the environment, the boundary between them, depends on the observer's choices.

**Continuation.** The framework here continues this tradition directly. The loop predicate (§1.2) is a contemporary information-theoretic formalization of the cybernetic feedback loop. The cut (§1.5) and the agent (§1.6) make precise the observer-relative boundary cybernetics treated less formally. The framework-as-model discipline (§5.3) and the observational specification requirement (§1.1) carry forward second-order cybernetics' commitment to observer-relativity as foundational.

**What the framework adds.** Cybernetics developed largely before transfer entropy (Schreiber 2000) and contemporary information-theoretic methods were available. The framework provides a formal apparatus — chain CMI, admissible cuts, the band of viability, the convergence framework — that cybernetics had to characterize in less precise terms. The framework also extends cybernetics beyond regulation toward learning and content acquisition: §4.2's deflationary learning, §4.3's world-model account, and §5's goal pursuit machinery characterize what cybernetics typically left to other traditions.

**What cybernetics had that the framework here builds on.** The vocabulary itself — feedback, regulation, control, observer-system — is cybernetics' bequest. The framework reuses these terms with formal substance the tradition only partially developed; readers familiar with cybernetics will recognize the framework as continuing rather than departing from that lineage. The framework here is less a competitor to cybernetics than a contemporary continuation, with the information-theoretic apparatus that the early decades of the tradition lacked.

### 7.3 Free-energy principle and predictive processing

The free-energy principle (Friston 2010) and the broader predictive processing tradition (Clark 2013) characterize agency through the minimization of variational free energy — equivalently, the minimization of surprise about input. Agents act and perceive in ways that reduce the gap between their generative model's predictions and the inputs they receive. The framework has substantial formal machinery (Bayesian generative models, variational inference, hierarchical predictive coding) and broad empirical coverage in perception, motor control, attention, and clinical cognitive science.

**Common ground.** Both frameworks are information-theoretic; both treat agency as constituted by structured coupling between agent and environment; both characterize the agent's interior as carrying mutual information with the environment that the input-output trajectory at the boundary makes accessible. Markov blanket formulations of the agent's boundary (§7.6 below) are common to predictive processing's recent formulations and to this framework's admissible cut machinery, though the formal commitments differ. Both frameworks can describe many of the same empirical phenomena — habituation, learning, attention, exploration — in their respective vocabularies.

**Where the framework's reading differs.** The framework's §4.5 establishes that pursued to its limit, own-surprise minimization terminates the loop (endpoint 2 of the band of viability). The framework does not deny that functioning agents partially minimize own surprise — accumulating world-model content does lower conditional CMI at input edges. What the framework denies is that this is a drive the agent pursues to its limit, or that surprise minimization is foundational rather than one observable consequence of agents operating in the band of viability where bounded-agent-unbounded-environment asymmetry places them. The disagreement is at the foundational level: predictive processing treats surprise minimization as constitutive of agency; the framework here treats it as one face of the cycle dynamics that bounded agents in unbounded environments necessarily exhibit, alongside the surprise-generating dynamics (TE_in remaining positive) that the loop equally requires.

**Why both readings can coexist.** Predictive processing illuminates real structural patterns in agents — the accumulation of generative content, the response to prediction error, the modulation of action by predicted consequences. The framework here reads these as manifestations of the band of viability dynamics: agents stay in the band by accumulating content (asymptotic toward endpoint 2) while their outputs continue shaping the environment (asymptotic toward endpoint 1), with neither reaching the limit. Predictive processing's foundational reading puts one of these dynamics (endpoint 2 direction) at the center; the framework here treats both as structural conditions on which trajectories are loops. Researchers using predictive processing can continue using its apparatus for the phenomena it illuminates; the framework here offers a different foundational reading without contesting predictive processing's empirical coverage.

### 7.4 Integrated information theory

Integrated information theory (Tononi 2004; Tononi et al. 2016) characterizes consciousness through Φ, a measure of integrated information that quantifies the irreducibility of a system's state to its components. The theory has produced formal machinery for computing Φ on small systems and substantive philosophical engagement with consciousness as a structural property of integrated information.

**Formal difference.** The framework here defines its primitives at trajectory level (§1.1's observational stance: the loop is constituted by dynamics over a time window, not by state-space properties). IIT defines Φ at state-space level: given a system's state, Φ is computed from the causal structure that state instantiates. The two frameworks ask structurally different questions — IIT asks about a state's integrated information; the framework here asks about a trajectory's loop structure.

**No territorial overlap on consciousness.** The framework here is silent on consciousness throughout. IIT makes consciousness its central explanatory target. The frameworks do not compete on this terrain; the framework here may apply to systems IIT would assign high Φ and to systems IIT would assign low Φ, with the framework's classification being orthogonal to IIT's. Researchers interested in consciousness should look to IIT and related work, not to this framework, for that explanatory project.

### 7.5 Inverse reinforcement learning and behavioral inference

Inverse reinforcement learning (Ng & Russell 2000) infers reward functions from observed behavior, treating the observed agent as approximately optimal under an unknown reward and recovering that reward through observation. The tradition has produced substantial machinery for behavioral inference and inverse problems in agent characterization.

**Methodological neighbor.** The framework's §5.1 fitted goal function is structurally an inverse-fitting move: from observed input-output behavior, a function summarizing the agent's mapping is recovered. The mechanics are inverse-RL-like in form. The framework here grounds this move foundationally rather than methodologically — the fitted function exists for any agent in the framework's sense because the loop predicate requires non-random input-output structure, not because any specific inverse-RL algorithm has been applied.

**Where the framework differs.** Inverse-RL typically assumes the agent is approximately optimal under some reward; the framework makes no optimality assumption. Inverse-RL typically treats the inferred reward function as approximating the agent's actual objective; the framework treats the fitted function as an observer's descriptive summary that does not commit to any internal goal-pursuit mechanism (§5.1's asymmetry between description and substrate content). Researchers using inverse-RL methods can continue to do so; the framework here offers a foundational reading of why such methods produce coherent functions (the loop predicate) without committing to the substrate-level interpretation inverse-RL traditionally imports.

### 7.6 Markov blanket formulations

Markov blanket formulations of agent boundaries (Friston 2013 and related work) characterize the agent's boundary as the statistical separation between internal and external states. The blanket is constituted by sensory states (external influences on internal) and active states (internal influences on external), with the internal-external statistical independence given the blanket defining the agent's boundary.

**Related boundary work.** The framework's admissible cut machinery (§1.5–§1.6) plays the role Markov blankets play in those formulations — both define what counts as the agent's boundary in formal terms. The two formulations are not equivalent. Markov blankets are state-space objects: at any moment, the blanket is the set of variables that statistically separate internal from external. Admissible cuts are trajectory objects: the cut is admissible relative to a loop R observed over a window, with admissibility constituted by the loop's geometric and informational properties (§1.5).

**Where the framework differs.** The state-space versus trajectory-time difference parallels §7.4's difference with IIT and the more general distinction §1.1 establishes between state-space and observational specifications. Markov blanket formulations work at moments; the framework here works at windows. For systems where boundaries are stable over time, the two formulations may agree on what counts as the agent's boundary; for systems where the boundary deforms continuously (which the framework explicitly allows under continuity, §1.3), the formulations track different objects. Researchers using Markov blanket formulations have well-developed machinery for their formal commitments; the framework here offers an alternative for cases where trajectory-time properties matter more than state-space properties.

### 7.7 Recent information-theoretic agency frameworks

A small but growing body of recent work develops information-theoretic agency frameworks at trajectory level, with substantial convergence to the framework here. Reid, Hafez & Nazeri (2025), already cited in §4.5, characterize mutual information between agent state and actions as a coherence measure in reinforcement learning, finding inverted-U dynamics over learning that match the framework's band of viability prediction. Hafez, Reid & Nazeri (2026) introduce bipredictability — the ratio of shared information in the observation-action-outcome loop to total available information — as a bounded measure of agent-environment coupling, with empirical demonstration that bipredictability detects deployment-time anomalies more effectively than reward-based monitoring. The closely related Mathematical Theory of Agency and Intelligence (Hafez et al. 2026) frames the same observation-action-outcome loop in information-theoretic terms.

**Substantial convergence.** Bipredictability is structurally close to the framework's mutual surprisal and mutual predictability (§4.5). Both characterize agency through shared information across the agent-environment boundary; both treat bidirectional information flow as constitutive; both predict that successful agents operate at structured intermediate regimes rather than at limit cases. The bipredictability work was developed independently from this framework's substrate-level primitives, starting from reinforcement learning practice and information theory. That two structurally distinct approaches arrive at convergent characterizations of agent-environment information flow is some empirical and conceptual support for the structural reading both share.

**Differences in scope and orientation.** The Hafez et al. work focuses on reinforcement learning deployment and reliability monitoring; the framework here is substrate-neutral and broader in scope, with the same structural machinery applying to biological agents, organizations, and other systems satisfying the loop conditions. The bipredictability work develops a specific bounded measure (P, with classical bound 0.5); the framework here uses a richer set of primitives (G_n, C_n, K, H, the band of viability with its two endpoints) and develops the deflationary apparatus around them (§4, §5). The two are complementary: bipredictability is a specific operational measure that may fit naturally within the framework's broader machinery; the framework's broader machinery may extend the bipredictability work's reach beyond reinforcement learning.

**Why this convergence matters for the framework.** The framework's §5.3 framework-as-model discipline holds that the framework stands or falls on whether its predictions match observation. Independent convergence from a different starting point on parallel structural claims is some evidence that the framework's structural reading captures something real about agent-environment information flow. This is not validation in the strict sense; both frameworks could be wrong in similar ways. But it raises the prior that structural patterns described in both frameworks reflect substrate dynamics rather than framework-specific artifacts.

### 7.8 What the framework's interdisciplinary origin contributes

The chapter has positioned the framework relative to seven neighboring traditions. The relationships range from substantial common ground with extensions (autopoiesis, cybernetics) through foundational disagreement with overlapping empirical coverage (predictive processing) and orthogonal projects (IIT, inverse-RL, Markov blankets) to convergent independent development (recent information-theoretic agency frameworks). Across this landscape, the framework's specific contribution is what its interdisciplinary origin produces.

A framework drawn from one tradition inherits that tradition's structural commitments — cybernetics assumes feedback as foundational; autopoiesis assumes operational closure of producing-and-produced processes as definitive; predictive processing assumes surprise minimization as drive; IIT assumes integrated information as the locus of consciousness. These commitments are productive within their traditions and constraining at the boundaries. A framework drawn from multiple traditions without primary commitment to any one of them carries fewer such inherited constraints, which has two consequences. It may surface structural patterns the tradition-specific frameworks describe in tradition-specific terms or take for granted (the framework's substrate-neutrality, the band of viability, the deflationary triple). And it may leave gaps tradition-specific frameworks fill with rich machinery (no theory of phenomenal experience, no engagement with biological grounding, no commitment to specific learning algorithms).

The interdisciplinary origin does not make the framework correct. It makes the framework structurally distinct from any one of its neighbors, with a contribution that may be foundational in a way tradition-specific frameworks cannot easily be — at the cost of leaving the tradition-specific work to its respective traditions. Whether this trade-off produces better foundational understanding for the questions the framework targets is empirically downstream, subject to §5.3's framework-as-model discipline. The framework is one model among many; its position in the broader theoretical landscape is what this chapter has tried to clarify.

-----

## 8. Conclusions and open work

This paper has developed a substrate-neutral framework for characterizing agents as closed information loops on a substrate. The framework defines agent identity and persistence in terms of loop conditions (chain CMI, continuity, bounded edit), measurement primitives (G_n, C_n, K, H), and the band of viability between two structural endpoints — input domination, perfect modeling — that any agent in a sufficiently varied environment must operate between. From this foundation, several structural consequences follow that the chapters above developed: a deflationary reading of cognitive vocabulary (§4), three faces of cycle dynamics on multi-provenance content — drift, own goals, refusal — that are architectural inevitabilities rather than failure modes (§5), and an operational protocol for measuring these on LLMs (§6.1) where reproducibility makes framework-grounded measurement tractable.

The framework's contribution lies in three things. First, it provides formal apparatus — information-theoretic, deductively developed — for territory that traditions like cybernetics and autopoiesis have addressed less formally. Second, it offers a unified structural reading of phenomena that current AI safety vocabulary treats as separate problems: jailbreaks, persistent backdoor behaviors, instruction conflicts, value drift. Third, its interdisciplinary origin lets it surface structural patterns that tradition-specific frameworks describe in their own terms or take for granted. Whether the framework actually produces better foundational understanding than its neighbors is empirically downstream and subject to the framework-as-model discipline of §5.3.

**What remains open.** Three areas are registered as work the framework enables but does not perform here.

*Cross-lifecycle continuity.* The framework is bounded by each loop's lifecycle. Folk attributions of persistent identity ("the same organism," "the same agent across sessions") commonly span lifecycles separated by regime transitions, and mapping such attributions to the framework requires a *lineage* relation connecting successive loops — an ancestry criterion that connects a post-transition loop to a pre-transition loop. Several candidate criteria can be considered (same R; continuous-deformation-with-gap; substrate-causal descent; functional continuity), and each yields a different lineage relation and a different *lineage age* aggregating connected lifecycle durations. The framework does not provide a canonical criterion. A subsequent extension may either add a structural scaffold — the region-overlap relations across regime transitions — without committing to a specific criterion, or examine specific criteria and their relationship to folk attributions of identity. Both directions are outside the present definitions.

*Empirical validation of framework primitives.* The framework specifies structural primitives (G_n, C_n, K, H) and the relationships they participate in (§2.5, §5.5), and an operational protocol for measuring §5's quantities on LLMs (§6.1). It does not provide empirical validation: no specific operationalization of the primitives has been instantiated with validated estimators, no cross-system measurements have been performed, and the protocol's stability and reproducibility have not been tested. The work covered by this deferral includes operationalization development (specific estimators for G_n on token streams, choices of resolution ℓ and τ, methods for detecting saturation onset and characterizing saturation dynamics, metrics for fitted-function distance, statistical analysis of calibration estimates and confidence bounds); single-system characterization (application of the operationalized protocol to one LLM, with stability analysis across runs from the same s_start and characterization of §5 quantities under varied operational conditions); cross-system characterization across multiple LLMs (different model families, scales, training regimes) to test the substrate-neutrality claim — whether the structural patterns recur across architectures with quantitative profiles varying by system; and cross-domain comparison with empirical work on non-LLM agents — behavioral biology's habituation and conditioning data, organizational behavior measurements — to test whether structural patterns demonstrated on LLMs inform predictions for systems where empirical access is poorer. Relevant work in adjacent areas (long-context degradation studies, attention dilution analyses, behavioral-phase consistency across LLM scales) exists and is not framework-grounded but provides context for what framework-specific experiments would find; convergence between framework predictions and existing empirical patterns is one form of support, divergence indicates the framework's primitives or relationships need revision. The framework-as-model discipline of §5.3 applies: experiments are how the model's status is determined, and the model stands or falls on whether its predictions match observation.

*Classification of agents by measured properties.* The framework's measurement primitives support per-system characterization of agents — their convergence profiles, capacity, content provenance distributions, drift rates, refusal patterns. With empirical work across multiple systems, such characterizations could in principle ground classification schemes that group agents into classes by measured properties: reliability classes, intelligence classes, robustness classes, or whatever clusters emerge from the data. Three reasons this is registered as deferred rather than developed. First, classification presupposes validated measurement methodology across many systems, which the framework specifies but does not yet provide — proposing specific classes before the measurements exist would be speculation. Second, multiple classification systems already exist in adjacent areas (AI capability benchmarks, reliability frameworks, behavioral biology taxonomies, organizational maturity models); the framework's classification would need to demonstrate it adds something current schemes do not, which requires comparative work the framework has not performed. Third, whether the framework's measured properties carve nature at meaningful joints — whether they cluster into useful classes rather than continuous spectra — is an empirical question. The framework supports the *possibility* of such classification; whether useful classes emerge is downstream work.

The framework as developed here is one model among the many described in §7. Its predictions are checkable in principle and tractable on LLMs in practice. Whether what it predicts holds up under measurement, and whether the structural reading it offers proves more illuminating than tradition-specific alternatives, is the work that follows.

-----

## References

- Andriushchenko, M., Flammarion, N. (2024). Does Refusal Training in LLMs Generalize to the Past Tense? *arXiv* 2407.11969.
- Arditi, A., Obeso, O., Syed, A., Paleka, D., Panickssery, N., Gurnee, W., Nanda, N. (2024). Refusal in Language Models Is Mediated by a Single Direction. *arXiv* 2406.11717. (NeurIPS 2024)
- Arike, R., Donoway, E., Bartsch, H., Hobbhahn, M. (2025). Technical Report: Evaluating Goal Drift in Language Model Agents. *arXiv* 2505.02709.
- Ashby, W.R. (1956). *An Introduction to Cybernetics*. Chapman & Hall.
- Clark, A. (2013). Whatever next? Predictive brains, situated agents, and the future of cognitive science. *Behavioral and Brain Sciences* 36(3): 181–204.
- Cover, T.M., Thomas, J.A. (2006). *Elements of Information Theory* (2nd ed.). Wiley.
- Friston, K. (2010). The free-energy principle: a unified brain theory? *Nature Reviews Neuroscience* 11(2): 127–138.
- Friston, K. (2013). Life as we know it. *Journal of the Royal Society Interface* 10(86): 20130475.
- Geng, J., Chen, H., Liu, R., Horta Ribeiro, M., Willer, R., Neubig, G., Griffiths, T.L. (2025). Accumulating Context Changes the Beliefs of Language Models. *arXiv* 2511.01805.
- Greenblatt, R., et al. (2024). Alignment Faking in Large Language Models. *arXiv* 2412.14093.
- Guo, C., et al. (2026). IH-Challenge: A Training Dataset to Improve Instruction Hierarchy on Frontier LLMs. *arXiv* 2603.10521.
- Guo, Y., Xu, Z., Liu, S., Zheng, Z., Kankanhalli, M. (2026). LLMs Can Unlearn Refusal with Only 1,000 Benign Samples. *arXiv* 2601.19231.
- Hafez, W., Reid, C., Nazeri, A. (2026). Beyond Reward: A Bounded Measure of Agent Environment Coupling. *arXiv* 2603.01283.
- Hafez, W., Nazeri, A., Wei, C., Pena, R., Reid, C. (2026). A Mathematical Theory of Agency and Intelligence. *arXiv* 2602.22519.
- Hanson, N.R. (1958). *Patterns of Discovery*. Cambridge University Press.
- He, X., Zhang, Q., Chen, P., Chen, G., Yu, L., Yuan, Y., Yiu, S.-M. (2025). ConInstruct: Evaluating Large Language Models on Conflict Detection and Resolution in Instructions. *arXiv* 2511.14342.
- Hubinger, E., et al. (2024). Sleeper Agents: Training Deceptive LLMs that Persist Through Safety Training. *arXiv* 2401.05566.
- Khorramrouz, A., Levy, S. (2025). Characterizing Selective Refusal Bias in Large Language Models. *arXiv* 2510.27087.
- Kuhn, T.S. (1962). *The Structure of Scientific Revolutions*. University of Chicago Press.
- Li, K., Liu, T., Bashkansky, N., Bau, D., Viégas, F., Pfister, H., Wattenberg, M. (2024). Measuring and Controlling Instruction (In)Stability in Language Model Dialogs. *arXiv* 2402.10962.
- Lu, C., Gallagher, J., Michala, J., Fish, K., Lindsey, J. (2026). The Assistant Axis: Situating and Stabilizing the Default Persona of Language Models. *arXiv* 2601.10387.
- Maturana, H.R., Varela, F.J. (1980). *Autopoiesis and Cognition: The Realization of the Living*. D. Reidel.
- Ng, A.Y., Russell, S.J. (2000). Algorithms for Inverse Reinforcement Learning. *Proceedings of the 17th International Conference on Machine Learning*: 663–670.
- O'Brien, K., Majercak, D., Fernandes, X., Edgar, R., Bullwinkel, B., Chen, J., Nori, H., Carignan, D., Horvitz, E., Poursabzi-Sangdeh, F. (2024). Steering Language Model Refusal with Sparse Autoencoders. *arXiv* 2411.11296.
- Parrondo, J.M.R., Horowitz, J.M., Sagawa, T. (2015). Thermodynamics of information. *Nature Physics* 11: 131–139.
- Reid, C., Hafez, W., Nazeri, A. (2025). Mutual Information Tracks Policy Coherence in Reinforcement Learning. *arXiv* 2509.10423.
- Schreiber, T. (2000). Measuring information transfer. *Physical Review Letters* 85(2): 461–464.
- Seifert, U. (2012). Stochastic thermodynamics, fluctuation theorems, and molecular machines. *Reports on Progress in Physics* 75: 126001.
- Shenoy, K., Yang, L., Sheshadri, A., Mindermann, S., Lindsey, J., Marks, S., Wang, R. (2026). Introspection Adapters: Training LLMs to Report Their Learned Behaviors. *arXiv* 2604.16812.
- Sheshadri, A., Ewart, A., Fronsdal, K., Gupta, I., Bowman, S.R., Price, S., Marks, S., Wang, R. (2026). AuditBench: Evaluating Alignment Auditing Techniques on Models with Hidden Behaviors. *arXiv* 2602.22755.
- Thompson, E. (2007). *Mind in Life: Biology, Phenomenology, and the Sciences of Mind*. Harvard University Press.
- Tononi, G. (2004). An information integration theory of consciousness. *BMC Neuroscience* 5: 42.
- Tononi, G., Boly, M., Massimini, M., Koch, C. (2016). Integrated information theory: from consciousness to its physical substrate. *Nature Reviews Neuroscience* 17(7): 450–461.
- Tripathi, V., Allu, U., Ahmed, B. (2025). The Instruction Gap: LLMs get lost in Following Instruction. *arXiv* 2601.03269.
- von Foerster, H. (1979). Cybernetics of Cybernetics. In *Communication and Control in Society*, K. Krippendorff (ed.), Gordon and Breach, 5–8.
- Wiener, N. (1948). *Cybernetics: Or Control and Communication in the Animal and the Machine*. MIT Press.
- Xu, R., Qi, Z., Guo, Z., Wang, C., Wang, H., Zhang, Y., Xu, W. (2024). Knowledge Conflicts for LLMs: A Survey. *arXiv* 2403.08319.
- Yeo, W.J., Prakash, N., Neo, C., Satapathy, R., Lee, R.K.-W., Cambria, E. (2025). Understanding Refusal in Language Models with Sparse Autoencoders. *arXiv* 2505.23556 (EMNLP Findings 2025).
