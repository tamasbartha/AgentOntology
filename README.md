# Agency, the optimization gap, and the architectural gap

This repository contains a paper on agency and the structural conditions that distinguish agents from non-agents, with consequences for current debates in AI safety, computational neuroscience, and the philosophy of mind.

The current paper is the developed articulation of an idea that began as a document called *Agent Ontology*. The seed of that earlier document, and the trajectory from it to the present articulation, is preserved in this repository's commit history. Readers interested in the genesis of the structural argument — what was seen first, and how it became articulated formally over time — can navigate the early commits to find the original formulation.

## What the paper claims

Working from a constraint we call universal coverage — that any acceptable definition of agency must cover the full range of plausibly agentic systems (RNA, bacteria, humans, corporations) without circular reference to goal-language — the paper derives a structural necessity condition: an agent requires sustained mutual surprisal across its bottleneck, sustained over the loop's own closure timescale, produced by the loop itself rather than by external structure.

From this necessity condition, several structural claims follow:

- The dominant agency-modeling frameworks (reinforcement learning, predictive coding, the free energy principle, active inference, control theory) all share a *minimization shape*: they specify agency as the optimization of some quantity toward zero. The paper argues that each framework's natural optimum coincides with violation of the necessity condition.

- The framework-specific machinery each tradition has developed — interoceptive priors in FEP, intrinsic motivation in RL, hierarchical priors in predictive coding, epistemic value in active inference — does equivalent structural work across frameworks: each provides the structure that the bare minimization formalism lacks. The paper calls the structural relationship between minimization-toward-optimum and necessity-condition-violation the *optimization gap*.

- The optimization gap has two faces. A *behavioral* face, on which proxy-trajectory and requirement-trajectory diverge under sufficient optimization pressure. And an *architectural* face, on which the architectural conditions required for high task-capability under demanding structural conditions are the same architectural conditions that produce capacity for instruction-refusal, deception, and independent goal-pursuit. The architectural face predicts a *capability-refusal frontier* in deployed AI: capability-installation and refusal-prevention are not separable problems because the underlying architecture is shared.

- The framework converges with two recent independent formalizations from different research traditions: Wang et al.'s within-RLHF Proxy Compression Hypothesis (arXiv 2604.13602), and Hubinger et al.'s mesa-optimization framework (arXiv 1906.01820). The three accounts nest: Wang's gap is a within-RLHF manifestation, Hubinger's gap is a within-learned-optimization manifestation, and the optimization gap names the cross-framework structural pattern of which both are instances. The convergence is itself evidence that the structural pattern is real rather than an artifact of any one tradition's vocabulary.

The paper's scope is explicitly marked as analytical: it is a structural theory of agency that diagnoses whether systems satisfy the necessity condition and predicts what follows in the agency regime where the conditions are met, while remaining silent about what is engineerable for systems diagnosed as non-agents.

## The trajectory

The earliest articulation in this repository is the *Agent Ontology* document, which contains the seed of the current paper's structural account: the agent as a self-closing causal loop with a bottleneck (originally formulated as "loop with cut"). This definitional kernel survived the development largely unchanged. What did not survive — or survived only in transformed form — is most of the structure that *Agent Ontology* tried to build on the kernel: a particular account of world model, learning framed as logging, semantization, mental state. Some of these were reformulated in the current paper; most were dropped as the work shifted from ontological enumeration toward structural analysis of what the agent definition actually requires.

A reader navigating to *Agent Ontology* should expect to find the agent definition recognizable, with rough formulations of consequences that the current paper has either reformulated or set aside. The development trajectory is therefore not a clean line from sketch to refinement; it is a kernel that survived and a surrounding structure that was substantially replaced. This is normal in theoretical development: a structural seeing can be right while the early attempts to articulate its consequences are wrong, and progress comes from preserving what was right while replacing what was wrong.

The commit history is preserved in full. Earlier formulations are visible as they were written, including those that have since been superseded. This is intentional: documenting which moves did not work is part of honest theoretical work.

For readers interested in the temporal record, the earliest commits predate the recent publications the current paper cites as convergent (Wang et al. 2026, Hubinger et al. 2019, Hafez et al. 2026; Friston/Thornton/Clark 2012 was already in the literature when this work began). The agent definition was developed independently of the recent convergent literature. The current paper engages with that literature carefully and positions the work in relation to it, but the kernel of the structural argument is older than the current convergence.

## Status

The current paper is a working draft prepared for arXiv submission. The technical claims about the minimization-shape critique, the formal verification of the cross-framework optimum coincidences, and the toy model for the rate-inequality mortality argument remain to be developed in subsequent work. The paper is offered as a structural articulation; the formal verification, the empirical tests, and the architecture-requirements derivation that the framework implies are work that subsequent researchers may take further.

The author is an independent researcher whose primary occupation lies elsewhere. This is hobby work in the sense that it was not produced under any institutional research program or career incentive, and it is offered to the field as a contribution rather than as the opening of a research career.

## How to read this repository

For the current paper, see [Agency.md](Agency.md).

For the original kernel of the agent definition, navigate to the earliest commits and find the *Agent Ontology* document. The loop-with-cut formulation is what survived; the surrounding consequences (world model, learning as logging, semantization, mental state) are early attempts that were largely reformulated or set aside.

For the development trajectory, the commit history records the progression from the early ontological enumeration to the current structural analysis.

## License

This work is released under the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/). You are free to share and adapt the material for any purpose, including commercially, provided you give appropriate credit and indicate if changes were made.

## Citation

While an arXiv preprint is in preparation, the repository can be cited as:

[Tamas Arpad Bartha]. *Agency, the optimization gap, and the architectural gap.* GitHub repository, [2026]. Available at: [https://github.com/tamasbartha/AgentOntology].

When the arXiv preprint is posted, that will become the canonical citation and this README will be updated to reflect it.

## Contact

[https://www.linkedin.com/in/tamas-bartha-9b33aaa9]
