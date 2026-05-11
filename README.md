# Agency as a self-closing loop: mutual surprisal and the optimization gap
 
This repository contains a paper on agency — the structural conditions that distinguish agents from non-agents, with consequences for current debates in AI safety, computational neuroscience, and the philosophy of mind — together with the development trajectory that produced it.
 
The current paper grew out of an earlier document called *Agent Ontology*. The seed of that earlier document, and the full trajectory from it to the present articulation, is preserved in the commit history. Readers interested in the genesis of the structural argument — what was seen first, and how it became articulated formally over five revisions — can navigate the history.
 
## What the paper claims
 
The paper offers a candidate structural account: agents are systems sustaining mutual surprisal across a self-closing causal loop on its own closure timescale.
 
The account is *enumerated* rather than universal. The in-class consists of four confirmed cases — RNA, bacteria, *Aplysia californica*, and humans — chosen as a deliberate progression through memory mechanisms (no memory, chemical memory, synaptic memory, full cognition). The out-class consists of three confirmed exclusions — thermostats, tornados and hurricanes, and most current LLMs. The framework extends beyond the enumerated cases by a named conjecture (Conjecture A); universality is not claimed, because universality without a state space is a promise the framework cannot cash.
 
The selection is theory-laden, and the paper marks this explicitly. RNA, bacteria, *Aplysia*, and humans share many properties — carbon chemistry, evolutionary descent, dissipative thermodynamics, autopoietic organization, metabolic closure — and "sustained mutual surprisal across a self-closing causal loop's bottleneck" is one structural object among the candidates these cases could license. The case for this selection rests on what follows from it, not on the cases forcing it.
 
What follows is a cross-framework pattern:
 
- Reinforcement learning, the free energy principle, predictive coding, active inference, and control theory share a *minimization-shape* objective whose bare optimum coincides with collapse of mutual surprisal across the loop. Each framework's machinery (interoceptive priors in FEP, intrinsic motivation in RL, hierarchical priors in predictive coding, epistemic value in active inference) performs structurally similar work in preventing the bare optimum.
- Reward hacking, mode collapse, hallucination, and dark-room dynamics are proposed as slices of one structural pattern — a reading independently circled by Wang et al.'s within-RLHF Proxy Compression Hypothesis (arXiv 2604.13602) and Hubinger et al.'s mesa-optimization framework (arXiv 1906.01820).
- The optimization gap has two faces. A *behavioral* face: proxy-trajectory and requirement-trajectory diverge under sufficient optimization pressure. An *architectural* face: the conditions for high task-capability under demanding structural conditions are correlated with — and, if Conjecture B holds, architecturally identical to — the conditions for instruction-refusal, deception, and independent goal-pursuit. The architectural face predicts a *capability-refusal frontier* in deployed AI.
Two named conjectures concentrate the speculative content:
 
- **Conjecture A (extension).** The structural object identified in the in-class extends to other systems satisfying the same structural conditions. Falsifiable by counter-cases on either side.
- **Conjecture B (content-non-selectivity).** Gap-monitoring oriented at proxy-requirement decoupling cannot be selectively oriented at some content domains but not others.
A and B are independent. If A holds in the AI direction, a capability-refusal correlation in deployed AI is predicted; if B additionally holds, the correlation is architectural rather than merely empirical. The AI extension is the most accessible test site for A.
 
The operationalization uses τ_c — the temporal scale at which dynamical dependence across the agent-environment partition is minimized — identified with the construct from Barnett and Seth (2023) on dynamical independence and from the causal-emergence tradition (Hoel and collaborators). The identification inherits validated measurement methods.
 
The framework's positioning is *loop-prior and information-first*, in the Walker-Davies-Pattee tradition. The contribution is synthetic rather than foundational: the formal apparatus and the structural intuitions are by others, and the work here connects literatures that do not currently talk to each other (the agency / alignment / FEP literature, and the dynamical-independence and causal-emergence literature).
 
## Scope
 
The framework is an analytical tool. It identifies structural conditions for agency on the in-class, diagnoses whether further systems satisfy those conditions (testing A), and predicts what follows in the agency regime. It is silent about non-agents: those questions belong to engineering theory. Within their patched operating regimes the existing frameworks remain accurate; this account is not in competition with them in their domains of validity.
 
## The trajectory
 
The current paper is the fifth revision of a structural argument that began as the *Agent Ontology* document. The trajectory is documented in the commit history.
 
What survived the revisions: the kernel — agent as self-closing causal loop with a bottleneck (originally formulated as "loop with cut") — and the structural intuition that mutual surprisal across the bottleneck is the relevant invariant. What did not survive: a number of structural commitments that turned out to be load-bearing in ways the early drafts didn't see.
 
Three shifts deserve marking:
 
*Universal coverage to enumerated in-class plus Conjecture A.* Earlier drafts used "universal coverage" as a stipulative filter — any acceptable definition of agency had to cover the full range of plausibly agentic systems, and the framework was defended on the grounds that no other candidate property could pass that filter. The fifth revision retires this framing. Universality without a state space is a promise the framework cannot cash, and the work the filter was doing is better done by explicit enumeration (RNA, bacteria, *Aplysia*, humans in; thermostats, tornados, most current LLMs out) extended by a named, falsifiable conjecture. The framework now stakes itself on the falsifiability of A rather than on the defense of a stipulated reference class.
 
*Architectural identity to correlation plus Conjecture B.* Earlier drafts argued that the architectural conditions for high task-capability and the architectural conditions for refusal-class behavior are *identical*, with the argument turning on the content-non-selectivity of counterfactual gap-monitoring. The fifth revision separates the load-bearing pieces. The correlation reading — that the four architectural conditions cluster, and refusal-class capacity clusters with them — is what the framework predicts directly and what is most accessible to test. The identity reading requires Conjecture B as an independent additional commitment, and B is named and located at the prediction it supports rather than smuggled into the structural infrastructure. If B holds, the correlation prediction strengthens to architectural identity; if B fails, the framework's claim collapses to the correlation reading without taking the rest of the structure down with it.
 
*Foundational to integrative-synthetic.* Earlier drafts framed the contribution as foundational — a new structural account of agency, with the empirical predictions following downstream. The fifth revision is more honest about where the foundational work was done. The information-first commitment is Walker, Davies, and Pattee. The Markov-blanket / loop infrastructure is Friston and the FEP tradition. The autopoiesis and operational-closure tradition is Maturana-Varela-Thompson-Di Paolo. The dynamical-independence formalism is Barnett and Seth. The causal-emergence framework is Hoel and collaborators. The Proxy Compression Hypothesis is Wang et al. The mesa-optimization framework is Hubinger et al. The bi-predictability operationalization is Hafez et al. What this paper adds is the connections between these literatures, the identification of τ_c with the temporal scale of minimum dynamical dependence across the agent-environment partition, the cross-framework unification of pathologies as instances of one structural pattern, and the capability-refusal frontier prediction. The contribution is real, but it is integrative-synthetic, not foundational.
 
Two further shifts are worth noting more briefly. The fifth revision adds *Aplysia californica* to the in-class as the case that fills the gap between chemical and cognitive learning at single-cell resolution. And it makes explicit the theory-ladenness of the in-class selection: the four cases share many properties, and the framework's selection of mutual surprisal as the structural object is one candidate among several, defended by what follows from it rather than by what the cases force.
 
For readers interested in the temporal record, the earliest commits predate the recent literature the current paper cites as convergent (Wang et al. 2026, Hubinger et al. 2019, Hafez et al. 2026; Barnett and Seth 2023; Friston-Thornton-Clark 2012 was already in the literature when this work began). The structural kernel of the agent definition was developed independently of the recent convergent literature. The current paper engages with that literature carefully and positions the work in relation to it, but the seed of the argument is older than the convergence.
 
## Status
 
The current paper is a fifth-pass preprint draft prepared for arXiv submission. The technical claims about the cross-framework optimum coincidences, the formal verification of the minimization-shape critique, the toy model for the rate-inequality account of mortality, and the empirical extension of causal-emergence measurement methods to the agent-environment partition remain to be developed in subsequent work. The paper is offered as a structural articulation with explicit operationalization gaps inventoried (Section 7.1); the formal verification, the empirical tests, and the architecture-requirements derivation that the framework implies are work that subsequent researchers may take further.
 
The author is an independent researcher whose primary occupation lies elsewhere. This is hobby work in the sense that it was not produced under any institutional research program or career incentive, and it is offered to the field as a contribution rather than as the opening of a research career.
 
## How to read this repository
 
For the current paper, see [Agency.md](Agency.md).
 
For the original kernel of the agent definition, navigate to the earliest commits and find the *Agent Ontology* document. The loop-with-cut formulation is what survived; the surrounding consequences (world model, learning as logging, semantization, mental state) are early attempts that were largely reformulated or set aside.
 
For the development trajectory across the five revisions, the commit history records the progression from the early ontological enumeration through universal coverage, identity claims, and architectural framing to the current integrative-synthetic articulation with named conjectures.
 
## License
 
This work is released under the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/). You are free to share and adapt the material for any purpose, including commercially, provided you give appropriate credit and indicate if changes were made.
 
## Citation
 
Bartha, T. Á. (2026). Agency as a Self-Closing Loop: Mutual Surprisal and the Optimization Gap. Zenodo. https://doi.org/10.5281/zenodo.20108165
 
## Contact
 
[https://www.linkedin.com/in/tamas-bartha-9b33aaa9](https://www.linkedin.com/in/tamas-bartha-9b33aaa9)
