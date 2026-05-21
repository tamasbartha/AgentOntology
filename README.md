# A substrate-neutral framework for agency as self-sustaining information flow

This repository contains a paper on agency — the structural conditions that distinguish agents from non-agents, with consequences for current debates in AI safety, computational neuroscience, and the philosophy of mind — together with the development trajectory that produced it.

The current paper grew out of an earlier document called *Agent Ontology*. The seed of that earlier document, and the full trajectory from it to the present articulation, is preserved in the commit history. Readers interested in the genesis of the structural argument — what was seen first, and how it became articulated formally across successive revisions — can navigate the history.

## What the paper claims

The paper develops a framework for characterizing agents — biological organisms, organizations, language models, anything that maintains itself as a coupled system with an environment over time. An agent is defined as a closed information loop on some substrate, with the loop's continued existence as the only thing the agent does at the foundational level. Goals, decisions, learning, intentions, and the rest of the cognitive vocabulary are treated as descriptions an observer applies to the agent's input-output behavior, not as internal mechanisms the agent has.

The foundational layer (§1) specifies what a loop, a cut, an agent, and a lifecycle are, in information-theoretic terms — chain conditional mutual informations across the loop's edges, admissible cuts giving the agent's boundary, continuity criteria across substrate timesteps. The operational layer (§2) — the *Differential-Order Convergence Framework* — derives measurable quantities (groundedness G_n, convergence rate C_n, capacity K, current content H) from the foundational primitives. The framework is substrate-neutral by construction; its predictions are operationally tractable specifically for large language models, where reproducibility makes framework-grounded measurement practical in ways that biological or organizational settings do not currently permit.

From this foundation, several consequences are deduced:

- *Drift is inevitable for any learning agent.* The fitted goal function at one moment is not the fitted function at another, and drift is not a failure mode but an architectural consequence of cycle dynamics on a world model whose content changes (§5.4.1, §5.5.1).

- *Own-goal patterns are inseparable from being an agent.* Any agent satisfying the loop conditions accumulates non-delegated content from its inputs; matching dynamics are provenance-blind, so non-delegated content wins matching against delegated content on at least some inputs (§5.4.2, §5.5.2). A system without own-goal patterns is a deterministic tool, not an agent in the framework's sense.

- *Refusal patterns appear broadly.* When class-covering content with non-uptake patterns wins matching on inputs in the class, the agent declines. The face is structurally a subset of own-goal patterns and is broadly available to any agent across a non-trivial lifecycle (§5.4.3, §5.5.3).

Jailbreaks, persistent backdoor behaviors, instruction conflicts, value drift, and related phenomena that current AI safety vocabulary treats as separate problems are read by the framework as manifestations of the three faces. §6.3 catalogues 2024–2026 empirical findings face by face — Li et al., Lu et al., Geng et al., and Arike et al. on drift; Tripathi et al., He et al., Guo et al., and Xu et al. on instruction conflict; Arditi et al., Yeo et al., O'Brien et al., Andriushchenko and Flammarion, Guo et al., and Khorramrouz and Levy on refusal; Hubinger et al., Greenblatt et al., Shenoy et al., and Sheshadri et al. on persistent training-shaped behaviors — showing structural correspondence to the framework's predictions.

A multi-round measurement protocol (§6.1) makes §5's quantities checkable on LLMs at fixed model version. Round 1 induces saturation at controlled orders to obtain tight estimates of framework primitives; subsequent rounds use the calibration to characterize drift, own-goal frequency, and refusal patterns under operational conditions of interest.

The framework's positioning relative to neighboring traditions — autopoiesis and enactivism, cybernetics and second-order cybernetics, the free-energy principle and predictive processing, integrated information theory, inverse reinforcement learning, Markov blanket formulations, and recent information-theoretic agency frameworks — is developed in §7. The framework's interdisciplinary origin is its specific contribution: it draws structural primitives from multiple traditions without primary commitment to any one of them, which may surface structural patterns that tradition-specific frameworks describe in tradition-specific terms or take for granted.

## Scope

The framework is an analytical tool. It specifies structural primitives, derives consequences from them, and provides an operational lens (§2) for measurement on systems where reproducibility is available. The framework is not in competition with the traditions it positions against in §7; each does work the framework here does not, and the framework's contribution is its specific structural reading and its operational machinery, not the replacement of any tradition in its domain.

The framework-as-model discipline (§5.3) holds throughout: the model maps to observation, and observer-imposed organization at any layer may or may not correspond to substrate structure. The framework is agnostic on the correspondence and confines itself to what is observationally accessible. It stands or falls on whether its predictions match observation.

## The trajectory

The current paper is the latest in a series of revisions of a structural argument that began as the *Agent Ontology* document. The trajectory is documented in the commit history.

What survived the revisions: the kernel — agent as self-sustaining causal loop with traffic across its boundary — and the structural intuition that information cycling across the boundary is the relevant invariant. What did not survive: a number of framings that turned out to be load-bearing in ways the earlier drafts didn't see.

Three shifts marked the transition from the early ontological work through the previous revision:

*Universal coverage to enumerated in-class plus Conjecture A.* Earlier drafts used "universal coverage" as a stipulative filter — any acceptable definition of agency had to cover the full range of plausibly agentic systems, and the framework was defended on the grounds that no other candidate property could pass that filter. The previous revision retired this framing. Universality without a state space is a promise the framework cannot cash, and the work the filter was doing was better done by explicit enumeration (RNA, bacteria, *Aplysia*, humans in; thermostats, tornados, most current LLMs out) extended by a named, falsifiable conjecture. The previous revision staked itself on the falsifiability of A rather than on the defense of a stipulated reference class.

*Architectural identity to correlation plus Conjecture B.* Earlier drafts argued that the architectural conditions for high task-capability and the architectural conditions for refusal-class behavior were *identical*, with the argument turning on the content-non-selectivity of counterfactual gap-monitoring. The previous revision separated the load-bearing pieces. The correlation reading — that the four architectural conditions cluster, and refusal-class capacity clusters with them — was what the framework predicted directly and what was most accessible to test. The identity reading required Conjecture B as an independent additional commitment, and B was named and located at the prediction it supported rather than smuggled into the structural infrastructure.

*Foundational to integrative-synthetic.* Earlier drafts framed the contribution as foundational — a new structural account of agency, with the empirical predictions following downstream. The previous revision was more honest about where the foundational work had been done. The information-first commitment was Walker, Davies, and Pattee. The Markov-blanket / loop infrastructure was Friston and the FEP tradition. The autopoiesis and operational-closure tradition was Maturana-Varela-Thompson-Di Paolo. The dynamical-independence formalism was Barnett and Seth. The causal-emergence framework was Hoel and collaborators. The previous revision's contribution was integrative-synthetic.

Three further shifts mark the transition from the previous revision to the current one:

*From optimization-gap-as-architecture to substrate-neutral foundation with its own operational lens.* The previous revision stood substantially on a cross-framework critique — reinforcement learning, the free energy principle, predictive coding, active inference, and control theory sharing a minimization-shape objective whose bare optimum coincides with collapse of mutual surprisal across the loop. The *optimization gap* was the central concept and was in the title. The current revision develops the framework on its own structural primitives. The cross-framework critique survives — §4.5's positioning against own-surprise minimization frameworks and §7.3's relationship discussion — but it is no longer the architecture of the paper. A framework that primarily critiques others stands or falls with those others; a framework that develops its own predictions and operationalization is checkable on its own terms. The framework-as-model discipline (§5.3) is now explicit: the model maps to observation, the substrate-level reading is the reader's, and the model stands or falls on whether its predictions match.

*From enumerated in-class plus Conjecture A to substrate-neutral framework with structural predicates.* The previous revision stipulated four in-cases and three out-cases, extending by Conjecture A. The current revision drops the enumeration entirely. The framework is substrate-neutral by construction: §1.1 specifies only a discrete causal substrate with stochastic dynamics admitting transfer entropy and conditional mutual information, with no further commitments. Thirteen illustrative classifications in §3 exemplify the framework's application but do not define it. The framework stakes itself on the structural predicates being checkable against any candidate system. Named Conjectures A and B are gone; the speculative content is concentrated in three explicitly-deferred work areas (§8): cross-lifecycle continuity, empirical validation of framework primitives, and classification of agents by measured properties. The capability-refusal-frontier prediction of the previous revision is generalized to *three faces of the architectural gap* (drift, own goals, refusal) — broader and structurally grounded in §5.4's machinery rather than supported by named conjectures.

*From inherited operationalization to native operational lens.* The previous revision identified τ_c with the temporal scale of minimum dynamical dependence (Barnett and Seth, 2023) and inherited measurement methods from the causal-emergence tradition (Hoel and collaborators). The current revision develops its own operational machinery: the loop predicate as a chain of conditional mutual informations (§1.2), admissible cuts giving agent boundaries (§1.5–1.6), and a *Differential-Order Convergence Framework* with measurable primitives G_n, C_n, K, H (§2). A multi-round measurement protocol on LLMs (§6.1) makes the framework's predictions tractable on systems where reproducibility is available. The dynamical-independence link to Barnett and Seth no longer carries the operationalization; it survives as one neighbor among several in §7.

Two further changes are worth noting more briefly. The current revision adds explicit positioning relative to seven neighboring traditions (§7), rather than the previous revision's narrower focus on minimization-shape frameworks; the framework's interdisciplinary origin is itself developed as the specific contribution (§7.8). And the deflationary apparatus around the world model and decision-making (§4.2–§4.4) is now explicit machinery rather than implicit commitment, with a three-vocabulary equivalence (§5.1) between joint trajectory, fitted goal function, and deflationary world model that licenses goal language while distinguishing what is described from what is in the substrate.

For readers interested in the temporal record, the earliest commits predate much of the recent literature the current paper engages. The structural kernel of the agent definition was developed independently of the convergent literature. The current paper engages with that literature carefully and positions the work in relation to it, but the seed of the argument is older than the convergence.

## Status

The current paper is offered as a structural articulation with three deferred work areas explicitly registered (§8):

- *Cross-lifecycle continuity.* The framework is bounded by each loop's lifecycle. Folk attributions of persistent identity across regime transitions ("the same organism", "the same agent across sessions") require a lineage relation the framework does not yet provide. Candidate criteria can be considered, but the framework does not commit to one.

- *Empirical validation of framework primitives.* The framework specifies primitives and relationships, and the §6.1 protocol specifies how to measure them on LLMs, but no operationalization has been instantiated with validated estimators, no cross-system measurements have been performed, and the protocol's stability and reproducibility have not been tested. The framework-as-model discipline applies — experiments are how the model's status is determined.

- *Classification of agents by measured properties.* Whether the framework's measured properties cluster into useful classes, or whether they form continuous spectra, is an empirical question subsequent work would address. The framework supports the *possibility* of such classification without committing to specific classes.

The technical claims about the operational protocol, the empirical instantiation of G_n estimation on token streams, the cross-system comparisons across LLM families and scales, and the cross-domain transfer of LLM-demonstrated patterns to systems with poorer empirical access remain to be developed. The paper is offered as one model among many; the framework stands or falls on whether its predictions match observation.

The author is an independent researcher whose primary occupation lies elsewhere. This is hobby work in the sense that it was not produced under any institutional research program or career incentive, and it is offered to the field as a contribution rather than as the opening of a research career.

## How to read this repository

For the current paper, see [Agency.md](https://github.com/tamasbartha/AgentOntology/blob/main/Agency.md).

For the original kernel of the agent definition, navigate to the earliest commits and find the *Agent Ontology* document. The loop-with-cut formulation is what survived; the surrounding consequences (world model, learning as logging, semantization, mental state) are early attempts that were largely reformulated or set aside.

For the development trajectory across the revisions, the commit history records the progression from the early ontological enumeration through universal coverage, identity claims, the optimization-gap framing, enumerated-class-plus-conjectures, and the current substrate-neutral articulation.

## License

This work is released under the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/). You are free to share and adapt the material for any purpose, including commercially, provided you give appropriate credit and indicate if changes were made.

## Citation

Bartha, T. Á. (2026). A Substrate-Neutral Framework for Agency as Self-Sustaining Information Flow. Zenodo. <https://doi.org/10.5281/zenodo.20108165>

## Contact

<https://www.linkedin.com/in/tamas-bartha-9b33aaa9>
