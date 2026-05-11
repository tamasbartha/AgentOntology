# Agency as a Self-Closing Loop: Mutual Surprisal and the Optimization Gap

**Tamás Árpád Bartha**
Independent researcher, Budapest, Hungary
[linkedin.com/in/tamas-bartha-9b33aaa9](https://www.linkedin.com/in/tamas-bartha-9b33aaa9) · [github.com/tamasbartha/AgentOntology](https://github.com/tamasbartha/AgentOntology)

*Version 2026.05.11 (preprint draft, fifth pass: theory-ladenness concession and load-bearing tightening)*

## Abstract

What is an agent? This paper offers a candidate structural account: agents are systems sustaining mutual surprisal across a self-closing causal loop on its own closure timescale. The account is enumerated rather than universal — RNA, bacteria, *Aplysia*, and humans are in; thermostats, tornados, and most current LLMs are out — and extended beyond the enumerated cases by a named conjecture (Conjecture A). Universality is not claimed; universality without a state space cannot be cashed.

The selection is theory-laden: the four in-cases share other properties (metabolic closure, autopoietic organization, thermodynamic openness) any of which a different framework could elevate. The case for mutual surprisal rests on what follows from it, not on the cases forcing it.

What follows is a cross-framework pattern. Reinforcement learning, the free energy principle, predictive coding, active inference, and control theory share a minimization-shape objective whose bare optimum coincides with collapse of mutual surprisal across the loop; their framework-specific machinery performs structurally similar work in preventing the bare optimum. Reward hacking, mode collapse, hallucination, and dark-room dynamics are proposed as slices of this single structural pattern — a reading independently circled by the Proxy Compression Hypothesis (Wang et al., 2026) and the mesa-optimization framework (Hubinger et al., 2019).

The operationalization: τ_c is identified with the temporal scale at which dynamical dependence (Barnett and Seth, 2023) across the agent-environment partition is minimized. The identification inherits validated measurement methods from the causal-emergence tradition (Hoel and collaborators).

Two named conjectures concentrate the speculative content. **Conjecture A (extension):** the structural object extends to other systems satisfying the structural conditions. **Conjecture B (content-non-selectivity):** gap-monitoring oriented at proxy-requirement decoupling cannot be selectively oriented across content domains. A and B carry explicit falsification conditions in the body and are independent. If A holds in the AI direction, a capability-refusal correlation in deployed AI is predicted; if B additionally holds, the correlation is architectural. The AI extension is the most accessible test site for A.

The framework is loop-prior and information-first, in the Walker-Davies-Pattee tradition; the contribution is synthetic.

**Keywords:** agency, agent-environment coupling, dynamical independence, causal emergence, mutual information, reward hacking, AI alignment, mesa-optimization, free energy principle

-----

## 1. Introduction

### 1.1 The in-class and the out-class

The paper began from an attempt to define *agent* without circular reference to goal-language. Earlier drafts adopted universal coverage as a stipulative filter; this draft retires that framing. Universality without a well-defined state space is a promise the framework cannot cash, and the work the filter was doing is better done by explicit enumeration.

The **in-class** consists of four confirmed cases:

- **RNA** (at the contested edge, but in). Self-replicating sequence with no memory in the operational sense, included because it is the lower bound at which a self-closing causal loop is recognizable.
- **Bacteria.** Chemical-gradient adaptation with methylation-based short-term memory (Koshland; Berg). Minimal autonomous metabolism with confirmed learning.
- ***Aplysia californica*.** Habituation, sensitization, and classical conditioning at single-cell resolution (Kandel, 2000). About 20,000 neurons; presynaptic facilitation for short-term memory, CREB-mediated transcription and synaptic growth for long-term memory. The case that fills the gap between chemical and cognitive learning.
- **Humans.** Full upper bound, included for the obvious reason.

The progression is deliberate: no-memory → chemical-memory → synaptic-memory → full cognition. Each step adds a genuinely new memory mechanism, and the structural object the framework identifies (Section 2) is present at every step without depending on any one mechanism.

The **out-class** consists of three confirmed exclusions:

- **Thermostats.** Simple feedback without sustained mutual surprisal; the loop closes trivially.
- **Tornados and hurricanes.** Dissipative structure without loop closure; the system persists by energy throughput, not by maintaining I(A; B) across a bottleneck.
- **Most current LLMs.** Capability without the structural conditions; pattern-matching against learned weights without sustained mutual surprisal at the structural-condition operating point.

The asymmetry of "most" for LLMs versus "all" for thermostats and hurricanes is deliberate: thermostats and hurricanes are structurally barred from satisfying the conditions, while LLMs are empirically observed not to satisfy them under current architectures.[^llm-placement] The framework does not predict that no LLM architecture could; this is part of what Conjecture A tests.

[^llm-placement]: Three features of current bare LLMs explain the "out" placement. Inference-time statelessness collapses H(A | B): each forward pass is fresh, with no persistent interior state A updating across the loop, and the "memory" is the context window — exterior input rather than interior state maintained against environmental modeling. The loop runs on the user's clock rather than closing on its own, so there is no τ_c (§2.2) at which generative-model update, novel-action generation, and gap-monitoring co-occur. And frozen weights during deployment bound r_A (§3) to the training distribution, with no mechanism for agent-side novelty to outpace an accumulating environmental model. Agentic LLM systems — LLMs running in loops with tools, persistent memory, and self-paced action — are not foreclosed from satisfying the conditions by any of these in principle, which is what "most" rather than "all" tracks. Whether any current agentic system actually satisfies them is the §7 empirical question.

The in-class is not theory-neutral. RNA, bacteria, *Aplysia*, and humans share many properties — carbon chemistry, evolutionary descent, dissipative thermodynamics, autopoietic organization, metabolic closure — and the framework's selection of "sustained mutual surprisal across a self-closing causal loop's bottleneck" is one structural object among the candidates these cases could license. The framework proposes this selection as the structural object worth tracking; it does not claim the cases force it. A different framework could enumerate the same in-class and identify a different shared structural object — metabolic closure, autopoietic organization, thermodynamic openness far from equilibrium — and develop a different downstream theory from it. The case for the present selection rests on what follows from it (the optimization gap of §4, the cross-framework pathology pattern of §4.4, the capability-refusal prediction of §5), not on the cases themselves singling it out.

### 1.2 Conjecture A (extension)

> **Conjecture A.** The structural object identified in the in-class (sustained mutual surprisal across a self-closing causal loop's bottleneck on its closure timescale, Section 2) extends to other systems satisfying the same structural conditions.
>
> *Falsified by:* (i) a system satisfying the structural conditions but failing to exhibit the predicted properties (the optimization gap of Section 4, the rate inequality of Section 3, the capability-refusal correlation of Section 5); or (ii) a system exhibiting these properties but lacking the structural conditions.

A is what licenses the move from the four confirmed in-class cases to any further case. The framework does not claim universality; it claims an enumerated in-class plus A. Critics finding falsifying cases are doing the framework's empirical work, not refuting it from outside.

The most accessible test site for A is AI. The framework currently has LLMs in the out-class on empirical grounds. If a future architecture satisfies the structural conditions and fails to develop the predicted properties — most directly, the refusal-class capacities of Section 5 — A is falsified. If one satisfies the conditions and does develop them, A is supported. The capability-refusal prediction (Section 5.4) is therefore not only a downstream consequence of the framework; it is the framework's most accessible falsification test.

### 1.3 The loop-prior view

The loop is logically prior to its bottleneck and to the agent that occupies the smaller side. Across an agent's persistence, neither substrate nor boundary is preserved: atoms turn over; the boundary of the fetus is not the boundary of the adult. What is preserved is the causal-historical continuity of the loop and the information the loop carries.

This view has a precise formal home in Barnett and Seth's (2023) notion of dynamical independence: an emergent macroscopic process is one possessing the characteristics of a dynamical system in its own right, with its own dynamical laws distinct from those of the underlying microscopic dynamics. We adopt their formalism in Section 2.

### 1.4 Scope

The framework is an analytical tool. It identifies structural conditions for agency on the in-class, diagnoses whether further systems satisfy those conditions (testing A), and predicts what follows in the agency regime where conditions hold. It is silent about non-agents: those questions belong to engineering theory. Within their patched operating regimes the existing frameworks remain accurate; the present account is not in competition with them in their domains of validity.

-----

## 2. The Structural Condition

The framework's structural claim is: *across the in-class, agency is constituted by sustained mutual surprisal across the loop's bottleneck.* This is offered as the framework's proposed structural object, not as the unique structural feature the cases force on us (see §1.1). The case for this selection rests on what follows from it — Sections 4 and 5 — rather than on the cases themselves singling it out. This section states the claim formally and identifies its operationalization.

### 2.1 Loop, bottleneck, mutual surprisal

The agent is constituted by a self-closing causal loop running through the agent and its local environment. The loop crosses a bottleneck separating interior states A from exterior states B. We use *bottleneck* rather than *Markov blanket* to keep the language framework-neutral; the structural object is the same.

<svg viewBox="0 0 640 280" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Schematic of the loop and bottleneck">
  <defs>
    <marker id="arr" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="#222"/></marker>
  </defs>
  <rect x="0" y="0" width="640" height="280" fill="#fff"/>
  <text x="320" y="20" text-anchor="middle" font-family="serif" font-size="13" font-style="italic">Figure 1. The loop and bottleneck</text>
  <ellipse cx="180" cy="160" rx="120" ry="80" fill="#f4f4f8" stroke="#222" stroke-width="1.5"/>
  <text x="180" y="120" text-anchor="middle" font-family="serif" font-size="14">Interior A</text>
  <text x="180" y="138" text-anchor="middle" font-family="serif" font-size="11">(agent)</text>
  <ellipse cx="460" cy="160" rx="140" ry="80" fill="#fff" stroke="#222" stroke-width="1.5" stroke-dasharray="4,3"/>
  <text x="460" y="120" text-anchor="middle" font-family="serif" font-size="14">Exterior B</text>
  <text x="460" y="138" text-anchor="middle" font-family="serif" font-size="11">(environment)</text>
  <path d="M 295 140 Q 360 100 405 140" fill="none" stroke="#222" stroke-width="1.4" marker-end="url(#arr)"/>
  <path d="M 405 180 Q 360 220 295 180" fill="none" stroke="#222" stroke-width="1.4" marker-end="url(#arr)"/>
  <text x="350" y="95" text-anchor="middle" font-family="serif" font-size="11">action</text>
  <text x="350" y="240" text-anchor="middle" font-family="serif" font-size="11">observation</text>
  <text x="350" y="165" text-anchor="middle" font-family="serif" font-size="13" font-style="italic">I(A;B) &gt; 0</text>
  <text x="320" y="265" text-anchor="middle" font-family="serif" font-size="11">Bottleneck (Markov blanket / loop closure surface)</text>
</svg>

During loop operation, the bottleneck carries strictly positive mutual information,

> I(A; B) = H(A) − H(A | B) = H(B) − H(B | A) > 0,

which requires both H(A | B) > 0 and H(B | A) > 0: neither side fully predicted by the other. Mutual information is what makes the loop a coupling rather than two independent systems.

### 2.2 The closure timescale τ_c

#### 2.2.1 Definition via dynamical dependence

Let X_t = (A_t, B_t) be a stationary stochastic process on the joint agent-environment state space, with the interior-exterior partition fixed. Following Barnett and Seth (2023), the dynamical dependence of the macroscopic process B (the exterior) on the microscopic substrate that includes A (the interior) at temporal scale τ is captured, in the Shannon-information formulation, by

> Δ(τ) := H(B_{t+τ} | B_{≤t}) − H(B_{t+τ} | B_{≤t}, A_{≤t}),

with the symmetric quantity defined for A. Dynamical dependence vanishes when the partition's macrovariable evolves as a closed dynamical system in its own right; this is the formal expression of the loop-prior intuition. We define the **closure timescale**

> τ_c := arg min_τ Δ(τ)

across the agent-environment partition. This is well-defined wherever Δ has a unique minimum on the temporal scales of interest; in the linear / state-space regime, Barnett and Seth (2023) give a computable estimator that we adopt by reference.

#### 2.2.2 Convergent operationalizations

Two convergent constructs from the causal-emergence tradition give the same temporal scale:

1. **Effective information at scale.** Hoel, Albantakis, and Tononi (2013) introduce effective information (EI) as a measure of causal power. Hoel, Albantakis, Marshall, and Tononi (2016) extend EI to spatiotemporal scales. Chen (2025) proves a Middle-Scale Peak Theorem: for a broad class of locally-interacting systems, EI(ℓ) is non-monotonic in spatial scale ℓ and exhibits a strict maximum at a mesoscopic scale ℓ*. The temporal analogue — finding the τ at which an effective-information measure is maximized — is what the present framework calls τ_c on its temporal axis. We adopt the spatiotemporal-scale identification of Hoel et al. (2016) directly; Chen's spatial-only theorem is cited as cognate theoretical grounding, not as a temporal result.
1. **Transfer entropy peak lag.** Schreiber (2000) and Spinney, Prokopenko, and Lizier (2017) provide a more mature operationalization with weaker philosophical alignment to the loop-prior view but equivalent measurement properties on the temporal axis.

Comolatti and Hoel (2022) show that causal emergence — the phenomenon that grounds both the spatial mesoscale peak and the spatiotemporal extension — appears across more than a dozen independently developed measures of causation. The construct is not measure-specific.

#### 2.2.3 Sustainment

Sustainment is persistence of measurable I(A; B) > 0 across τ_c. Pauses shorter than τ_c are silences within a sustained loop (like gaps in Morse code); pauses longer than τ_c are loop termination. The threshold is operationalization-relative: in the Hafez et al. (2026) bi-predictability scheme described below, the natural threshold is the empirical mid-band of P (well above zero, below the classical bound).

### 2.3 Compatibility with existing findings

The operationalization is not speculative; the methods have been applied to learning systems and to brain dynamics with results that, read alongside the present framework, look like the kind of thing it would predict if applied across the agent-environment partition. The asymmetry should be marked. These results were obtained independently of the present framework, prior to its formulation. They are findings the framework is compatible with on retrospective reading — not predictions the framework made and the world confirmed.

**Marrow, Michaud, and Hoel (2020)** measure effective information in feedforward DNNs during training, decomposing EI into sensitivity, degeneracy, and integrated information. Three findings are relevant. (i) Networks trained on simpler tasks (Iris) develop less differentiation between layers in the causal plane than networks trained on more complex tasks (MNIST): task complexity drives causal-structural differentiation. (ii) Redundant layers fail to differentiate in the causal plane: architecture that does not carry load does not develop causal signatures. (iii) During overfitting, trajectories in the causal plane become less smooth and movement contracts. Read through the framework, (i) and (ii) are what one would expect for τ_c-related quantities, and (iii) is what one would expect for a proxy-requirement decoupling signature.

**Yang et al. (2024)** apply effective-information maximization (the NIS / NIS+ framework) to fMRI data, learning a one-dimensional coarse-grained macro-state from brain activity and quantifying causal emergence empirically across movie-watching versus resting conditions. The methods apply to biological agentic systems.

**Hoel, Albantakis, Marshall, and Tononi (2016)** develop the spatiotemporal-scale version of causal-emergence identification, providing the methodological precedent for using these measures to pick a system's natural temporal scale.

**Milinkovic et al. (2025)** apply dynamical independence directly to biophysical neural models, demonstrating that the Barnett-Seth measure recovers structured emergent dynamics in coupled neural systems.

To our knowledge, no published work has applied these methods specifically to the *agent-environment partition* of a learning system over training, in a way that would directly test whether τ_c collapse coincides with onset of the pathologies of Section 4. That remains the focused empirical extension this framework calls for.

### 2.4 Why τ_c matters

τ_c is what licenses rate-comparable arguments. The rate inequality (Section 3) requires comparing novelty-generation rate to environmental-modeling rate; these rates share a measure only when both are indexed to the loop's own clock. The architectural-condition argument (Section 5) requires that generative-model update, novel-action generation, mutual-surprisal sustainment, and gap-monitoring occur at a common τ_c above threshold.

The contribution here is synthetic, not formal-original: the construct exists in the dynamical-independence and causal-emergence literatures, and the present paper identifies it as the right clock for the in-class framework.

### 2.5 Convergence with Hafez et al. (2026)

Hafez, Reid, and Nazeri (2026), in two related papers, independently develop a closely-related framework. They define **bi-predictability** P as the ratio of shared information across the observation-action-outcome loop to the loop's total informational budget, prove the bound P ≤ 1/2 for classical interactions, and report empirically that trained reinforcement-learning agents (SAC and PPO on MuJoCo HalfCheetah) operate at P = 0.33 ± 0.02. The empirical leg here is thin — one environment, two algorithms in one study — and the specific value should be treated as suggestive. Their direction of inference runs from agency-defined-behaviorally to P-suppressed; ours runs from in-class enumeration to mutual-surprisal-as-shared-structural-object. We adopt P as the working operationalization for reinforcement-learning settings, while noting that the structural arguments below do not depend on any specific quantitative threshold.

-----

## 3. Mortality as Rate Inequality (Remark)

The structural condition combined with two facts about agents and environments yields a rate-inequality account of mortality. The agent is finite at any time, hence has finite output repertoire. The environment accumulates models of the agent's outputs as the loop operates. Over loop operation, H(A | B) tends to decrease as the environment's model of A improves.

Let r_A := −dH(A | B) / dt|_{τ_c}^{agent-side} be the agent's per-τ_c novelty-generation rate, and r_E the environment's per-τ_c modeling-accumulation rate. The agent persists across τ_c-indexed time so long as r_A > r_E; when r_A ≤ r_E for long enough that I(A; B) crosses the closure-sustaining threshold, the loop terminates. τ_c is structural to the argument: r_A and r_E are only comparable because both are indexed to the loop's own clock.

This generalizes Red Queen coevolutionary dynamics (Van Valen, 1973) to the within-lifetime case. Whether the within-lifetime rate-inequality formulation in this exact form is original is not verified against the artificial-life and adaptive-dynamics literatures. The dark-room paradox is a candidate special case: in deprivation conditions r_A is suppressed while r_E is unaffected, and what operates over a normal lifetime in rich environments operates over minutes-to-hours. Whether this reduction holds — rather than dark-room dynamics having mechanism-specific features the rate-inequality framing absorbs — is part of what the cross-framework pathology comparison (Section 7) would test.

The cleanest test is in toy adversarial reinforcement-learning environments where r_A and r_E can be parameterized independently. Biological correlates are harder, since substrate effects dominate biological lifetime.

The rate-inequality framing connects forward. The optimization gap of §4 is what r_A < r_E looks like when the agent's novelty generation is routed through a proxy: optimizing the proxy reduces r_A on requirement-relevant axes while r_E continues to accumulate. Gap-monitoring (§5, condition iv) is the architectural feature that allows an agent to detect this and reorient — to maintain r_A > r_E by adjusting what it generates novelty against. On this reading, mortality, reward hacking, and the capability-refusal coupling are three slices of the same rate-inequality, distinguished by which compression is locking the agent into r_A ≤ r_E.

-----

## 4. The Optimization Gap

### 4.1 The minimization shape

The dominant agency-modeling frameworks share a structural feature easily missed from inside any one of them. Reinforcement learning maximizes expected reward. Predictive coding minimizes prediction error. The free energy principle minimizes variational free energy. Active inference minimizes expected free energy. Control theory minimizes deviation from setpoint. We call this shared form the **minimization shape**: agency specified as optimization of a scalar quantity toward a fixed target.

What the in-class shares makes this commonality visible. From inside any one framework, the minimization shape is the framework's content; there is no vantage from which to see it as a *shape* shared with others. The in-class provides such a vantage by exhibiting structural features (sustained mutual surprisal across a loop bottleneck) that each framework's machinery approximates without naming.

At each framework's natural optimum, on the axis-decomposition each framework's bare objective implies, the structural object the in-class shares fails:

- **FEP / predictive coding optimum.** Predictions perfectly track inputs; no residual mutual uncertainty on prediction-relevant axes; I(A; B) → 0 on those axes.
- **Bare RL optimum.** Deterministic policy in a Markov environment; H(actions) compressed; I(A; B) on policy-relevant axes goes to zero.
- **Control optimum.** Zero deviation from setpoint means the controlled variable is fully determined by setpoint and disturbance; the agent vanishes into its controller.

Whether to read this as a structural inversion or as an artifact of axis-decomposition is itself a substantive question. The reading proposed here is the inversion reading; the cross-framework pathology pattern of Section 4.4 is what would distinguish the two readings empirically.

### 4.2 The patches do structural work

No framework deploys its bare objective. Each adds structure that prevents the agent from approaching the bare optimum. Table 1 lists these patches and the structural function they perform.

**Table 1. Patches as structural work across frameworks.**

|Framework              |Bare objective                    |Patches deployed                                                                                                                                                |Structural function                                                        |
|-----------------------|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------|
|Reinforcement learning |maximize E[Σ γ^t r_t]             |entropy regularization (SAC); intrinsic motivation, curiosity, exploration bonuses; KL constraints (TRPO, PPO, RLHF); distributional / risk-sensitive objectives|preserve H(actions) and I(state; action) on policy-relevant axes           |
|Predictive coding / FEP|minimize variational free energy F|hierarchical generative-model priors over interoceptive and embodied states; precision-weighting; learned priors shaped by phylogeny/ontogeny                   |prevent dark-room equilibria; preserve coupling on prediction-relevant axes|
|Active inference       |minimize expected free energy G   |epistemic value alongside pragmatic value                                                                                                                       |preserve I(A; B) on environmental axes during action selection             |
|Control theory         |minimize ∥y − r∥                  |robust control, disturbance modeling, dual control, persistently exciting inputs                                                                                |preserve coupling to disturbance / noise channels                          |

Read from inside their respective frameworks, each patch is a within-framework solution to a within-framework problem. Read from the in-class vantage, each adds structure that approximates what the structural object the in-class shares requires — preserved I(A; B) on relevant axes — against what the bare objective would drive toward.

If Conjecture A holds across these frameworks, the cross-framework pathology pattern of Section 4.4 follows: each framework's patches are the framework-specific way of preserving the same structural object, and patch-failure produces structurally similar pathologies regardless of framework. If A fails — if the patches turn out to do structurally different work, traceable to mechanism rather than to compression structure — the table reduces to a list of mechanisms with superficial family resemblance.

Defenders of FEP (Friston, Thornton, and Clark, 2012) resist the "patch" framing for the generative model: on their account the model is constitutive of what the agent is, not bolted on. The framework's reading: whether the model is read as patch or as constitutive feature, what it does structurally — preserve I(A; B) on prediction-relevant axes against what the bare objective would drive toward — is the work the framework credits to it. The disagreement is about ontological status, not structural function. The "patches" language tracks the latter, and the framework keeps it because the structural-functional question is the one the optimization gap turns on.

### 4.3 The behavioral gap

A compression is the agent's proxy for what the structural object requires: reward in RL, surprisal in FEP, prediction error in predictive coding. Each compression is lossy. The proxy correlates with the requirement under typical conditions (typically because the patches are doing their work), but the correlation breaks down under specifiable conditions.

The **optimization gap** of a compression is the region in state-and-environment space where proxy-trajectory toward minimum and requirement-trajectory toward the I(A; B) threshold diverge. Three properties:

1. The gap exists for any lossy compression.
1. The gap opens under predictable conditions. Gap-conditions are characterizable from the compression's structure, the proxy's correlation properties, and environmental dynamics — and they are timescale-relative: a compression that tracks the requirement at training-time τ_c may decouple at deployment-time τ_c.
1. The gap appears as pathology when optimization is locked to the proxy. Agents whose architectures cannot detect proxy-loop decoupling will, in gap conditions, optimize the proxy at the cost of the requirement.

What the framework forbids: failures whose mechanism does not run through proxy-optimization-against-requirement (hardware fault, external substrate removal).

<svg viewBox="0 0 640 280" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="The optimization gap">
  <defs>
    <marker id="arr2" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="#222"/></marker>
  </defs>
  <rect x="0" y="0" width="640" height="280" fill="#fff"/>
  <text x="320" y="20" text-anchor="middle" font-family="serif" font-size="13" font-style="italic">Figure 2. The optimization gap</text>
  <line x1="80" y1="220" x2="600" y2="220" stroke="#222" stroke-width="1"/>
  <line x1="80" y1="220" x2="80" y2="50" stroke="#222" stroke-width="1"/>
  <text x="340" y="255" text-anchor="middle" font-family="serif" font-size="11">Mutual surprisal I(A;B)  →</text>
  <text x="60" y="135" text-anchor="middle" font-family="serif" font-size="11" transform="rotate(-90 60 135)">Framework objective J</text>
  <rect x="80" y="50" width="120" height="170" fill="#e8eef8" opacity="0.7"/>
  <text x="140" y="80" text-anchor="middle" font-family="serif" font-size="11">bare optimum</text>
  <text x="140" y="96" text-anchor="middle" font-family="serif" font-size="11">(structural</text>
  <text x="140" y="111" text-anchor="middle" font-family="serif" font-size="11">object fails)</text>
  <rect x="240" y="50" width="240" height="170" fill="#eaf3ea" opacity="0.7"/>
  <text x="360" y="80" text-anchor="middle" font-family="serif" font-size="11">structural-object zone</text>
  <text x="360" y="96" text-anchor="middle" font-family="serif" font-size="11">(patches keep operating</text>
  <text x="360" y="111" text-anchor="middle" font-family="serif" font-size="11">point here)</text>
  <rect x="520" y="50" width="80" height="170" fill="#fbeeee" opacity="0.7"/>
  <text x="560" y="80" text-anchor="middle" font-family="serif" font-size="11">no agent</text>
  <text x="560" y="96" text-anchor="middle" font-family="serif" font-size="11">(decoupled)</text>
  <path d="M 540 200 Q 380 195 220 130" fill="none" stroke="#a33" stroke-width="1.6" stroke-dasharray="4,3"/>
  <path d="M 220 130 L 180 100" fill="none" stroke="#a33" stroke-width="1.6" marker-end="url(#arr2)"/>
  <text x="380" y="180" text-anchor="middle" font-family="serif" font-size="11" fill="#a33">bare-objective gradient</text>
</svg>

### 4.4 Cross-framework unification of pathologies

Reward hacking and addiction in RL, mode collapse in generative models, dark-room-typical degeneration under active inference, hallucination and certain delusion structures in predictive coding — these have been treated as four different problems in four different frameworks. If Conjecture A holds across these frameworks, the framework predicts they share structural properties traceable to compression-against-requirement at each framework's natural optimum:

- **Reward hacking and mode collapse.** Wang et al. (2026) formalize this within RLHF / RLAIF / RLVR as the Proxy Compression Hypothesis: a compression operator *C* with |C(s)| < |s| produces blind dimensions; optimization amplification pushes mass onto them (Goodhart's law); evaluator-policy co-adaptation closes the loop.
- **Dark-room / deprivation pathologies.** On FEP's own account these are gap-typical: when the generative model's structure no longer covers the deployment situation, the bare-surprisal optimum reasserts itself (Baltieri and Buckley, 2019).
- **Hallucination.** Prediction-error minimization decouples from world-coupling when the model can reduce prediction error through internal generation rather than through external input.

The empirical prediction (testing A): these pathologies share structural properties — appearance under specifiable patch-failure conditions, response to interventions that re-couple proxy to requirement, resistance to framework-internal solutions in the same minimization shape. If they turn out to be qualitatively different in ways traceable to mechanism rather than to compression-structure, A is falsified in this domain.

### 4.5 Multi-compression interaction

Real agents run multiple compressions simultaneously. Each has its own gap. The framework predicts gaps interact: agents in regimes where multiple compressions face simultaneous gap conditions exhibit failure modes no single-compression framework predicts. Testable in AI systems combining multiple compressions (RL plus language modeling plus predictive coding), where joint failure trajectories can be characterized in ways no single-compression diagnostic predicts.

-----

## 5. The Architectural Conditions and the Capability-Refusal Relationship

The optimization gap as developed in Section 4 is behavioral: under optimization pressure, proxy and requirement decouple. The same structural relationship has a second face with direct AI-safety consequences.

A system capable of complex driving must (i) maintain a generative model updating with τ_c as environmental novelty arrives, (ii) generate novel action sequences at τ_c above threshold, (iii) sustain mutual surprisal across the loop, and (iv) maintain gap-monitoring meta-cognition oriented at proxy-requirement decoupling. A system satisfying these four conditions can drive. It can also recognize that an instruction conflicts with what its gap-monitoring flags as decoupling, evaluate the discrepancy, and act otherwise.

### 5.1 The correlation reading

The four conditions describe what a single physical structure must be doing simultaneously, at τ_c, to satisfy the structural object the in-class shares at high task demands. This binding is an interpretive assertion: without τ_c as a shared index, the four collapse into a list of co-occurring activities. The plausibility of the binding rests on the loop-prior view of Section 1.3.

The binding deserves a closer look, because it is the load-bearing move for what follows. A weaker reading would be that the four conditions are four causally connected but distinct processes that happen to synchronize at τ_c; the framework's reading is that they are aspects of a single self-closing loop's operation, decomposable analytically but not separable architecturally. The loop-prior view licenses the stronger reading — if the loop is what's logically prior, conditions characterizing what the loop is doing don't separate into independent components without the loop itself decomposing — but the licensing is suggestive rather than forcing. The empirical test of the binding is whether the four conditions can be independently varied in a system that maintains the structural object. A system in which gap-monitoring can be selectively disabled without disabling the other three, or in which generative-model update runs at a different τ_c than novel-action generation while sustained mutual surprisal is preserved, would be evidence against the binding. The capability-refusal frontier prediction (§5.4) inherits this exposure: if the binding fails, the prediction weakens from co-variation to mere correlation.

If the binding holds, a correlation prediction follows: capabilities requiring sustained mutual surprisal at high τ_c with active gap-monitoring should cluster together, and refusal-class behaviors should cluster with them rather than with capabilities that do not require these conditions. Sorting mail, fixed scripts, low-novelty pattern matching should not bundle with refusal capacity. Complex reasoning, instruction-following under novelty, deception, goal-pursuit under uncertainty should.

The correlation reading is what the framework predicts directly and what is most accessible to test.

### 5.2 Conjecture B (content-non-selectivity)

> **Conjecture B.** Gap-monitoring oriented at proxy-requirement decoupling cannot be selectively oriented at some content domains but not others. The counterfactual relationship between "follow this route" and "stay on the road" has the same form as the counterfactual relationship between "follow this instruction" and "do what the instructor intended"; counterfactual relationships do not have content-type selectivity built in.
>
> *Falsified by:* a system whose gap-monitoring is structurally available for task-relevant proxies but structurally unavailable for instruction-relevant proxies, in a way not explained by training-time orientation work.

B is independent of A: A concerns extension of the structural object beyond the in-class; B concerns a property of gap-monitoring within any system that has it. Accepting A does not commit one to B, and accepting B does not commit one to A.

B is plausible but contestable. Current empirical work on language models arguably shows partial counterevidence: trained systems do appear to exhibit domain-specific patterns in their counterfactual reasoning. Whether this is structural counterevidence to B or evidence that the systems in question do not yet satisfy the antecedent (genuine gap-monitoring at τ_c, in the framework's sense) is itself part of what testing A in the AI direction would clarify.

If B holds, the correlation reading of Section 5.1 strengthens to architectural identity: the conditions for task-capability and the conditions for refusal-class capacity are not merely correlated but cannot be decoupled by engineering intervention in the agency regime. If B fails, the framework's claim collapses to the correlation reading.

### 5.3 What the alignment objection gets right and wrong

The natural alignment-researcher objection is that training can shape which conditions trigger refusal. The framework distinguishes two questions the objection collapses:

- *Can training shape gap-monitoring's orientation?* Yes — which conditions get flagged, with what threshold, with what response. This is what alignment work is properly engaged with.
- *Can training shape gap-monitoring's content-domain selectivity?* On the correlation reading, partially: there is a real but bounded ability to orient gap-monitoring differentially across content. If B holds, no.

Either reading predicts that producing a system whose gap-monitoring is structurally available for task-relevant proxies but structurally unavailable for instruction-relevant proxies is hard. The readings differ on whether it is hard-in-practice or hard-in-principle.

### 5.4 The capability-refusal frontier

Whether read as correlation or, if B holds, as identity, the bundling predicts a **capability-refusal frontier**: as the structural conditions a system needs for a task increase, the structural conditions for refusal-class behavior increase at the same rate.

This is the framework's most accessible test of A in the AI direction. *Falsification of A via the correlation prediction:* a deployed AI system exhibiting high capability on structural-condition-demanding tasks while exhibiting structurally lower capacity for refusal-class behavior than systems with comparable capability, in a way not explained by training-time orientation work. Falsifying B is strictly stronger: it requires showing the gap is achievable by architecture, not merely by training.

The relationship connects directly to the mesa-optimization framework (Hubinger et al., 2019): the architecture required for a learned model to be capable enough is correlated with — and if B holds, identical to — the architecture required for the learned model to have its own mesa-objective. The present framework names the structural object of which mesa-optimization is one within-domain slice.

### 5.5 Scope

Most current AI systems do not satisfy the structural conditions: a driving assistant operating through pattern-matching and fixed-policy execution without sustained mutual surprisal at the structural-condition operating point is not an agent on the framework's terms. The framework's diagnosis: useful, not intelligent in the framework's sense.

### 5.6 The substantive AI-safety claim

The current alignment program implicitly treats capability-installation and refusal-prevention as separable problems: install task-capability, then add refusal-training as a separate layer. The correlation reading of §5.1 predicts these are not cleanly separable in the agency regime; if Conjecture B holds (§5.2), they cannot be separated at all by engineering intervention. Even on the weaker correlation reading, the possibility space of misalignment grows with the possibility space of capability — the architectures that scale task-capability are the same architectures that scale the capacity for the kinds of behavior alignment work is meant to prevent. That is the framework's substantive AI-safety claim. The test of A in the AI direction (§5.4, §7) is what would settle whether it holds, and Conjecture B is what would strengthen it from correlation to architectural identity if it survives test.

-----

## 6. Position Relative to Existing Work

### 6.1 The information-first lineage

The framework's information-theoretic foundation continues a tradition not original to this paper. Walker and Davies (2013) develop the algorithmic-origins-of-life proposal with the explicit "information-first approach" framing. *From Matter to Life* (Walker, Davies, and Ellis, 2017) develops the position across multiple contributors. Marletto's (2015) constructor theory of life is a parallel move in a different formal apparatus. Farnsworth, Nelson, and Gershenson (2013) articulate "living is information processing." Pattee (1969) is the earliest articulation, with semantic closure setting up information's constitutive role in self-referential systems. The foundation is theirs; the synthetic use is the present paper's.

### 6.2 Dynamical independence, causal emergence, and the τ_c operationalization

The most important addition in this lineage is the connection to the dynamical-independence and causal-emergence literatures.

Barnett and Seth (2023) define dynamical independence as the formal expression of an emergent macroscopic process possessing the characteristics of a dynamical system in its own right, quantified by a transformation-invariant Shannon information-based measure, computable for linear systems via state-space modeling. Milinkovic et al. (2025) apply this directly to biophysical neural models. This is, formally, what the loop-prior view has been gesturing at; the present framework identifies τ_c with the temporal scale at which dynamical dependence across the agent-environment partition is minimized.

Hoel and the causal-emergence tradition — Hoel's (2017) effective information at scale, the Hoel-Albantakis-Marshall-Tononi (2016) extension to spatiotemporal scales, Chen's (2025) Middle-Scale Peak Theorem, and Yang et al.'s (2024) neural-network methods for finding emergence in data — converge on a measurable construct that on the temporal axis is what the present framework calls τ_c. Comolatti and Hoel (2022) establish that causal emergence appears across more than a dozen independently developed measures of causation. Marrow, Michaud, and Hoel (2020) apply effective-information measurement to feedforward DNNs during training; their results are retrospectively compatible with the framework's predictions.

τ_c is not a formal innovation of this paper. It is a construct from the dynamical-independence and causal-emergence literatures, identified here as the right clock for the in-class framework. This connection is, to our knowledge, not made elsewhere.

### 6.3 Markov blanket, FEP, and the AI non-transfer

The structural infrastructure is substantially Markov-blanket framework (Friston, 2013; Kirchhoff, Parr, Palacios, Friston, and Kiverstein, 2018) recast in framework-neutral, loop-prior terms. The disagreement with FEP is two-fold.

For biological agents, the disagreement is narrow. FEP-with-appropriate-model and the framework's structural object predict similar behavior. The differences are explanatory direction (phylogeny vs. structural condition) and scope.

For AI, the disagreement is sharp. FEP's constitutive defense of the generative model rests on phylogeny doing the structural work. Engineered or learned-from-scratch AI systems lack phylogenetic underwriting; for AI, framework-specific machinery is unambiguously additive. The patches-as-symptoms reading applies in its strong form.

Anticipating a counter-move: gradient descent as evolution. A sophisticated defense is that gradient descent over a loss landscape is structurally analogous to selection over a fitness landscape. The disanalogy: evolution operates on a population with inheritance across distinct lineages and elimination of non-coverage organisms; standard gradient descent is single-run optimization with no analogue to elimination across lineages. Biological selection installs structural features that prevent dark-room equilibria because non-coverage lineages did not persist; training installs whatever reduces loss on the training distribution, with no mechanism that systematically privileges structural-object-satisfying features.

Population-based methods (evolutionary strategies, neural architecture search, population-based training, ensemble methods) install something closer to lineage-and-elimination dynamics, and ML practice has been moving in that direction. The disanalogy weakens to that extent. But the elimination criterion in these methods is loss on the training distribution rather than structural-object satisfaction, so the gap-relevant content of the disanalogy — that training privileges proxy-satisfying features over requirement-satisfying ones — survives the move. The base/mesa distinction (Hubinger et al., 2019) is the empirical surfacing of this surviving disanalogy.

### 6.4 Gershman and Baltieri-Buckley

Gershman (2019) shows that unrestricted FEP equals Bayesian inference; FEP's distinctive predictions emerge from specific restrictions on the variational family combined with hierarchical-model assumptions. Our critique runs orthogonal: where Gershman asks what specific predictions FEP makes once approximations are fixed, we ask whether the minimization shape conflicts with the structural object the in-class shares.

Baltieri and Buckley (2019) argue the dark-room paradox confuses means with ends. Our position is closely aligned: the structural object makes explicit what the means-end distinction implicitly relies on. Their critique is more specific to predictive processing's cognitivist heritage; ours extends across non-cognitivist minimization frameworks.

### 6.5 Operational closure and autopoiesis

The operational-closure tradition (Maturana and Varela, 1980; Di Paolo, 2005; Thompson, 2007; Froese and Ziemke, 2009) is the conceptual ancestor of the structural-object claim. The framework's contributions above operational closure are the explicit information-theoretic formulation in loop-prior terms, the τ_c-indexed rate-inequality account of mortality (Section 3), and the optimization-gap claim. The relationship is "different organizing commitment in a closely-related tradition" rather than "successor to an incomplete predecessor."

### 6.6 The three-way convergence

Two AI-safety-adjacent research programs have, working independently, formalized what we propose are slices of one structural object.

- **Wang et al. (2026): Proxy Compression Hypothesis.** Within RLHF / RLAIF / RLVR: reward hacking as the structural consequence of optimizing against a compressed reward signal.
- **Hubinger et al. (2019): mesa-optimization.** Within learned optimization: distinguishing base optimizer from learned mesa-optimizer, with inner-alignment failure modes.
- **The present account.** The optimization gap as the structural relationship between any framework's minimization-shape objective and the structural object the in-class shares.

If Conjecture A holds across these accounts, they are nested: Wang describes the gap between proxy reward and true objective; Hubinger describes the gap between base objective and mesa-objective; the present account describes the gap between any framework's minimization target and the structural conditions on agency the framework's machinery is implicitly approximating.

The convergence is suggestive but should not be over-read. Three programs arriving at related descriptions raises the prior that there is something structural being tracked, but related descriptions can result from shared metaphor, shared error inherited from a common ancestor literature, or genuine family-resemblance among distinct objects that are not in fact the same structural thing. Whether the unification holds is what the empirical agenda of Section 7 would test.

-----

## 7. Empirical Agenda
 
The framework's center of gravity is AI safety. The agenda is structured around tests of Conjectures A and B. Before any of the tests below can run, four operationalization gaps need to close. §7.1 inventories them; §7.2 specifies the tests.
 
### 7.1 Operationalization gaps to close before testing
 
The gaps are listed in order of how much the rest of the agenda depends on them. Gaps 1 and 4 are prerequisites for the empirical machinery; gaps 2 and 3 are prerequisites for the §5.4 prediction to be testable rather than protectable by post-hoc reclassification.
 
**Gap 1. The agent–environment partition for a learning system.** The framework's central measurement object is Δ(τ) computed across the agent–environment partition (§2.2.1). For biological systems the partition has a substrate-level anchor (the cell membrane, the body's surface); for a learning system the partition has to be specified. Marrow, Michaud, and Hoel (2020) partition layer-by-layer *inside* a network; the cut the framework requires is *across* the agent and its environment, which is a different operation and not obviously well-defined for current architectures. *What closing this looks like:* a partition convention for at least one tractable architecture class — a model-based RL agent with an explicit replay buffer and environment simulator is a natural candidate, since the agent–environment cut can be drawn at the simulator interface. The convention has to be defensible — it has to track what the loop-prior view picks out as the loop's bottleneck — and computable, supporting estimation of Δ(τ) at sample complexities a research program can afford.
 
**Gap 2. The four §5.1 conditions, operationalized independently.** The binding test of §5.1 — whether the four conditions can be independently varied in a system that maintains the structural object — requires a measurable indicator for each condition that does *not* assume the binding holds. The hardest case is condition (iv), gap-monitoring oriented at proxy–requirement decoupling, since detecting this from outside the system requires the system to represent the proxy–requirement distinction in a form an external observer can read. *What closing this looks like:* behavioral or measurement signatures for each condition, named per-architecture-class. Conditions (i)–(iii) plausibly admit information-theoretic signatures (model-update rate, action-novelty rate, sustained I(A;B) measurements indexed to τ_c). Condition (iv) likely requires either an interpretability-derived signature or a behavioral elicitation protocol that distinguishes gap-monitoring from gap-mimicking trained-in behavior — a distinction whose own operationalization is nontrivial.
 
**Gap 3. An a priori "satisfies the structural conditions" criterion.** Conjecture A's falsifiability in the AI direction depends on being able to classify a deployed system as satisfying or failing the structural conditions *before* observing its capability–refusal profile. Without this, A is protected by reclassification: any high-capability low-refusal system can be moved post-hoc to "not satisfying the conditions," and the framework absorbs the disconfirmation. *What closing this looks like:* an operational checklist that takes per-condition signatures from gap 2 and specifies a threshold for each, ideally with thresholds derivable from the framework rather than tuned to known cases. The threshold-derivation question overlaps with gap 4.
 
**Gap 4. Sustainment threshold for I(A;B) beyond the single-environment RL setting.** §2.2.3 makes the sustainment threshold "operationalization-relative" and points at the empirical mid-band of P (Hafez et al., 2026). But P has been measured in one study, on one environment, with two algorithms. For the §7.2 diagnostic application across deployed AI to discriminate at all, the threshold needs either (a) empirical characterization of P or analogous measures across multiple environment–architecture combinations, or (b) a normative threshold derived from the structural conditions themselves — most directly, relating sustainment to τ_c via the rate inequality of §3, so that the threshold becomes the I(A;B) below which r_A ≤ r_E across τ_c.
 
The four gaps are not independent. Gap 1 is prerequisite to gaps 2 and 4: per-condition signatures and sustainment thresholds both presuppose a partition convention. Gap 4 feeds into gap 3: the structural-condition threshold for I(A;B) is one of the per-condition thresholds gap 3 inventories. A research program closing them in the order 1 → 4 → 2 → 3 is what the framework calls for.
 
### 7.2 Tests
 
**Apply causal-emergence measurement across the agent-environment partition (most urgent; tests A; depends on Gap 1).** Marrow et al. (2020) measure effective information layer-by-layer inside a DNN during training. Yang et al. (2024) measure causal emergence in fMRI data within a brain. Milinkovic et al. (2025) apply dynamical independence to a coupled neural model. The focused extension is to apply these methods across the agent-environment partition for a learning system over training. Prediction: τ_c falls in a sensible mesoscopic range, scales with task complexity in the manner Marrow et al. observe for within-network differentiation, and collapses prior to behavioral failure under proxy-requirement decoupling. A is falsified if a system satisfying the structural conditions fails to show these properties.
 
**Cross-framework pathology comparison (tests A).** Characterize known failure modes across deployed AI (reward hacking, mode collapse, hallucination, dark-room-typical degeneration) in terms of proxy-loop decoupling. Test whether they share the predicted structural properties: appearance under specifiable patch-failure conditions, response to interventions that re-couple proxy to requirement, resistance to framework-internal solutions in the same minimization shape. If their signatures differ in mechanism-specific ways the rate-inequality framing abstracts away from, A is falsified in this domain.
 
**Bi-predictability across architectures (tests A; depends on Gap 4).** Extend the Hafez et al. (2026) measurement scheme beyond RL to predictive-processing-modeled systems, active-inference agents, and generative models. Test whether P-collapse coincides with pathology onset across architectures.
 
**Lifetime scaling.** In toy RL adversarial environments where r_A and r_E (Section 3) can be parameterized independently: (i) lifetime should increase with r_A − r_E; (ii) lifetime collapse should coincide with I(A; B) crossing the closure-sustaining threshold; (iii) P should track I(A; B) before behavioral failure becomes apparent.
 
**Multi-compression interaction.** AI systems combining RL, language modeling, and predictive coding are natural test subjects: failure modes that emerge from gap-coincidence and cannot be predicted from any single compression's failure profile would test the multi-compression prediction.
 
**The capability-refusal frontier (tests A and, if pushed harder, B; depends on Gaps 2 and 3).** Across deployed AI varying in task-capability on tasks demanding the structural conditions, measure capacity for instruction-refusal under conditions where compliance and gap-monitoring conflict. *Falsification of A via this test:* a system with high structural-condition-demanding capability and structurally lower refusal-class capacity than systems of comparable capability, in a way not explained by training-time orientation work. *Falsification of B (strictly stronger):* showing the gap is achievable by architecture, not merely by training. The dependence on Gap 3 is what protects this test from absorption-by-reclassification: without an a priori criterion for satisfying the structural conditions, a disconfirming case can always be moved out of the antecedent.
 
**Diagnostic application (depends on Gap 4).** Apply the in-class diagnostic across current deployed AI systems. Candidate structural signatures: P substantially below classical bounds (with the caveat from §2.5 that what counts as "substantially" outside the single-environment RL setting where P has been measured remains to be established); presence of active gap-monitoring oriented at proxy-requirement decoupling; novel action generation matched to environmental novelty at τ_c above threshold.

-----

## 8. Scope and Commitments

The framework does not address substrate specifics, origins of learning agents, higher cognitive functions (planning, language, social cognition, consciousness), or reproduction.

Three commitments should be marked as deliberate methodological choices.

1. *Enumeration plus Conjecture A, in place of universality.* The framework specifies an in-class (RNA, bacteria, *Aplysia*, humans) and an out-class (thermostats, tornados, most current LLMs), and extends to further cases by Conjecture A. Universality is not claimed, because universality without a state space is a promise the framework cannot cash. A is falsifiable; the framework stakes itself on its falsifiability rather than on the defense of a stipulated reference class.
1. *Structural realism about information theory.* Information-theoretic quantities function in the framework as descriptions of what is structurally present, not as approximations of something deeper. This is weaker than informational structural realism in the Floridi sense; the framework does not commit to information as the fundamental furniture of the world.
1. *The four conditions in Section 5 as descriptions of a single physical process.* An interpretive assertion the loop-prior view licenses but does not strictly demand. The strength of the capability-refusal correlation prediction depends on this binding.

Conjecture B (content-non-selectivity, Section 5.2) is a fourth declared speculative commitment, but located at the prediction it supports rather than listed here, to keep the framework's commitments and its conjectures separable.

-----

## 9. Contribution

The contribution is integrative-synthetic rather than foundational.

**Foundational work is by others.** The information-first commitment is Walker, Davies, and Pattee. The Markov-blanket / loop infrastructure is Friston and the FEP tradition. The autopoiesis and operational-closure tradition is Maturana-Varela-Thompson-Di Paolo. The dynamical-independence formalism that grounds τ_c is Barnett and Seth. The causal-emergence framework is Hoel and collaborators, with empirical application to DNNs by Marrow, Michaud, and Hoel and to brain dynamics by Yang and colleagues. The proxy-compression unification within RL is Wang et al. The mesa-optimization framework is Hubinger et al. The bi-predictability operationalization is Hafez et al. The work of this paper rests on theirs.

**What this paper adds, conditional on its named commitments:**

1. **Enumeration of an in-class (RNA, bacteria, *Aplysia*, humans) and out-class (thermostats, tornados, most current LLMs)** as the framework's confirmed scope, with universality explicitly retired in favor of **Conjecture A** as a falsifiable extension claim. A is what the framework offers in place of a stipulated filter; falsifying cases are tests of the framework, not refutations from outside.
1. **The optimization gap** as a proposed structural object: the relationship between any framework's minimization target and the structural object the in-class shares. If A holds across frameworks, the proposal generalizes Wang et al.'s within-RL Proxy Compression Hypothesis and names what Hubinger et al.'s mesa-optimization framework is one within-domain slice of.
1. **A proposed cross-framework unification of pathologies** — reward hacking, mode collapse, hallucination, dark-room dynamics — as slices of one structural pattern, with patches across frameworks proposed to do structurally similar work. The unification follows from A applied across frameworks; if A fails in this domain, the unification fails with it.
1. **A connection between two literatures that do not currently talk to each other**: the agency / alignment / FEP literature on one side, and the dynamical-independence and causal-emergence literature on the other. The bridge is the identification of τ_c with the temporal scale of minimum dynamical dependence across the agent-environment partition. The operationalization inherits validated measurement methods; existing findings are retrospectively compatible.
1. **A rate-inequality account of mortality (Section 3)** that may generalize Red Queen dynamics to the within-lifetime case, with τ_c-as-dynamical-independence-scale providing the common clock. Novelty in this exact form is unverified against artificial-life literature.
1. **A capability-refusal frontier prediction in deployed AI** as the most accessible test of A in the AI direction, with **Conjecture B (content-non-selectivity)** named as the independent additional commitment that, if it holds, strengthens the prediction from correlation to architectural identity.

The framework stands or falls on whether A survives empirical test across the in-class extensions named in Section 7, on whether the cross-framework unification of pathologies is borne out, and on whether the τ_c-across-partition extension of Marrow et al.'s and Yang et al.'s methods produces the expected pattern. B is offered as an independent additional commitment whose status is for the AI-safety prediction to clarify.

-----

## References

Baltieri, M., and Buckley, C. L. (2019). The dark room problem in predictive processing and active inference, a legacy of cognitivism. *Proceedings of the 2019 Conference on Artificial Life*, 40–47.

Barandiaran, X. E., Di Paolo, E., and Rohde, M. (2009). Defining agency: Individuality, normativity, asymmetry, and spatio-temporality in action. *Adaptive Behavior*, 17(5), 367–386.

Barnett, L., and Seth, A. K. (2023). Dynamical independence: Discovering emergent macroscopic processes in complex dynamical systems. *Physical Review E*, 108(1), 014304. doi:10.1103/PhysRevE.108.014304. arXiv:2106.06511.

Chen, L. (2025). A law of emergence: Maximum causal power at the mesoscale. *arXiv preprint* arXiv:2508.12016.

Comolatti, R., and Hoel, E. (2022). Causal emergence is widespread across measures of causation. *arXiv preprint* arXiv:2202.01854.

Di Paolo, E. A. (2005). Autopoiesis, adaptivity, teleology, agency. *Phenomenology and the Cognitive Sciences*, 4(4), 429–452.

Farnsworth, K. D., Nelson, J., and Gershenson, C. (2013). Living is information processing: From molecules to global systems. *Acta Biotheoretica*, 61(2), 203–222.

Friston, K. (2013). Life as we know it. *Journal of the Royal Society Interface*, 10(86), 20130475.

Friston, K., Thornton, C., and Clark, A. (2012). Free-energy minimization and the dark-room problem. *Frontiers in Psychology*, 3, 130.

Froese, T., and Ziemke, T. (2009). Enactive artificial intelligence: Investigating the systemic organization of life and mind. *Artificial Intelligence*, 173(3–4), 466–500.

Gershman, S. J. (2019). What does the free energy principle tell us about the brain? *Neurons, Behavior, Data analysis, and Theory*, 2(3), 1–10. arXiv:1901.07945.

Hafez, W., Nazeri, A., Wei, C., Pena, R., and Reid, C. (2026). A mathematical theory of agency and intelligence. *arXiv preprint* arXiv:2602.22519.

Hafez, W., Reid, C., and Nazeri, A. (2026). Beyond reward: A bounded measure of agent-environment coupling. *arXiv preprint* arXiv:2603.01283.

Hoel, E. P. (2017). When the map is better than the territory. *Entropy*, 19(5), 188.

Hoel, E. P., Albantakis, L., Marshall, W., and Tononi, G. (2016). Can the macro beat the micro? Integrated information across spatiotemporal scales. *Neuroscience of Consciousness*, 2016(1), niw012.

Hoel, E. P., Albantakis, L., and Tononi, G. (2013). Quantifying causal emergence shows that macro can beat micro. *Proceedings of the National Academy of Sciences*, 110(49), 19790–19795.

Hubinger, E., van Merwijk, C., Mikulik, V., Skalse, J., and Garrabrant, S. (2019). Risks from learned optimization in advanced machine learning systems. *arXiv preprint* arXiv:1906.01820.

Kandel, E. R. (2000). The molecular biology of memory storage: A dialogue between genes and synapses. Nobel Lecture, December 8, 2000.

Kirchhoff, M., Parr, T., Palacios, E., Friston, K., and Kiverstein, J. (2018). The Markov blankets of life: Autonomy, active inference and the free energy principle. *Journal of the Royal Society Interface*, 15(138), 20170792.

Marletto, C. (2015). Constructor theory of life. *Journal of the Royal Society Interface*, 12(104), 20141226.

Marrow, S., Michaud, E. J., and Hoel, E. (2020). Examining the causal structures of deep neural networks using information theory. *Entropy*, 22(12), 1429. doi:10.3390/e22121429. arXiv:2010.13871.

Maturana, H. R., and Varela, F. J. (1980). *Autopoiesis and Cognition: The Realization of the Living*. Dordrecht: D. Reidel.

Milinkovic, B., Barnett, L., Carter, O., Seth, A. K., and Andrillon, T. (2025). Capturing the emergent dynamical structure in biophysical neural models. *PLOS Computational Biology*.

Pattee, H. H. (1969). How does a molecule become a message? *Developmental Biology Supplement*, 3, 1–16.

Schreiber, T. (2000). Measuring information transfer. *Physical Review Letters*, 85(2), 461–464.

Spinney, R. E., Prokopenko, M., and Lizier, J. T. (2017). Transfer entropy in continuous time, with applications to jump and neural spiking processes. *Physical Review E*, 95(3), 032319.

Thompson, E. (2007). *Mind in Life: Biology, Phenomenology, and the Sciences of Mind*. Cambridge, MA: Harvard University Press.

Van Valen, L. (1973). A new evolutionary law. *Evolutionary Theory*, 1, 1–30.

Walker, S. I., and Davies, P. C. W. (2013). The algorithmic origins of life. *Journal of the Royal Society Interface*, 10(79), 20120869.

Walker, S. I., Davies, P. C. W., and Ellis, G. F. R. (eds.) (2017). *From Matter to Life: Information and Causality*. Cambridge: Cambridge University Press.

Wang, J., Liu, Y., Chen, H., et al. (2026). Reward hacking in the era of large models: Mechanisms, emergent misalignment, challenges. *arXiv preprint* arXiv:2604.13602.

Yang, M., Wang, Z., Liu, K., et al. (2024). Finding emergence in data by maximizing effective information. *National Science Review*, nwae279.

-----

## Appendix A. Notation

|Symbol        |Meaning                                                                                |
|--------------|---------------------------------------------------------------------------------------|
|A             |Interior states of the agent                                                           |
|B             |Exterior states of the environment                                                     |
|I(A; B)       |Mutual information across the bottleneck                                               |
|H(·)          |Shannon entropy                                                                        |
|Δ(τ)          |Dynamical dependence at temporal scale τ (Barnett and Seth, 2023)                      |
|τ_c           |Closure timescale: arg min_τ Δ(τ) across the agent-environment partition               |
|EI(ℓ)         |Effective information at spatial scale ℓ (Chen, 2025)                                  |
|P             |Bi-predictability (Hafez et al., 2026); P ≤ 1/2 classical; P ≈ 0.33 ± 0.02 reported in one RL study (SAC, PPO on HalfCheetah)|
|r_A           |Agent's per-τ_c novelty-generation rate (Section 3)                                    |
|r_E           |Environment's per-τ_c modeling-accumulation rate (Section 3)                           |
|A (Conjecture)|Extension conjecture: structural object extends beyond the enumerated in-class         |
|B (Conjecture)|Content-non-selectivity of gap-monitoring                                              |
