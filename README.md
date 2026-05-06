# Agent Ontology: A Constraint-Based Approach
This document outlines an agent ontology and the subsequent requirements for agents efficient in survival.

**UPDATE 2026.05.06 08:16 CET**: ChatGPT found a new falsifyable statement based on the ontology, and was kind enough to create a paper and a Python test suite to validate it. I don't understand much of it (yet), so I uploaded it AS-IS as neurips_gamma_project.zip. **The statement**: Complex adaptive systems undergo a measurable phase transition from stable subsystem structure to dynamically generated subsystem structure when the rate of interaction reconfiguration exceeds the rate at which stable partitions can form—that is, when Γ = flow reconfiguration rate / structural stabilization rate approaches 1.

A key innovation of this ontology and deduction is the inversion of the core postulate of Karl Friston’s Free Energy Principle (FEP). While the FEP suggests that agents act to minimize the surprise (variational free energy) received from their environment [Friston, 2010], this framework proposes the opposite: the primary driver of an agent is the optimization (but not necessarily maximization) of the surprise exerted upon the environment. In this model, the minimization of internal surprise is merely a necessary byproduct of successful environmental perturbation—a shift that effectively resolves the 'Dark Room' paradox.

## Introduction
The original objective was to create a goal-oriented IT project management methodology, the adherence to which — provable even to skeptics — is necessary and sufficient for the realization of an information goal. The rationale for this was that available methodologies are generally functional descriptions that fail to present the underlying constraints; thus, their effectiveness is difficult to prove.

During the development of the methodology, it soon became clear that any goal-oriented management methodology is essentially suitable for the task, which led directly to the necessity of a (distributed) agent architecture. 
Currently known agent architectures are also functional descriptions: they model - considerably well - how agents operate but do not provide exhaustive answers to the constraints that make certain functions necessary. This ontology was born to approach the ideal architecture from the perspective of constraints.

While the original goal of a complete architecture has not (yet) been realized, a significant portion of the constraints has been identified and may be of interest to the community.


## Definitions

### Concepts Related to Information Flow

**State Trajectory** – A function mapping time to state; in the discrete case, a temporal sequence of states. It represents the change of state over time and can be interpreted as a starting state plus a sequence of changes/functions.

**Information Rate** – A function that determines how quickly new information is generated at a given point of a state trajectory; i.e., to what extent the state change deviates from previously observed patterns. It is the differential of the Shannon entropy of the trajectory segment defined up to that point.

**Local Regularity** – The differentiability order of the information rate at a given point in time. If the information rate is singular (discontinuous), the local regularity is 0. If it is smooth (no derivative is discontinuous), it is infinite.

**Event** – A point in time (and the associated state change) where local regularity is not infinite.

**Event Regularity** – The local regularity at the moment an event occurs; by definition, not infinite.

**Chaotic Event** – An event with a regularity of 0.

**Event Trajectory / Process** – A discrete function mapping time to events; a temporal sequence of events. A state trajectory can be reconstructed from a starting state using an event trajectory.

**Global Regularity** – The reciprocal of the integral of the reciprocal of local regularity. It defines the average regularity of the entire trajectory. If a trajectory contains a chaotic event, its global regularity is 0. Since a trajectory can be losslessly represented as a superposition of changes in different orders of derivatives, global regularity can be viewed as the compressibility of the trajectory representation.

**Information Flow** – A process that is causally ordered, meaning for every event, the occurrence of the preceding event is a necessary (but not necessarily sufficient) precondition.

**Channel** – The space/path of information flow; the physical or logical medium (a part of space) whose state changes constitute the events of an information flow. A channel can be decomposed into sub-channels by partitioning its space.

**Interface** – A plane partitioning a channel; it can be interpreted as a stateless channel where the state change is the difference between the state changes on its two sides.

**Information Flow Velocity** – The information rate of the trajectory defined by the state changes of an interface.

**Bandwidth** – The maximum information flow velocity of the spaces delimited by an interface, dictated by external (e.g., physical) constraints. It may change over time but is not part of the interface's state, rather a derived property.

**Bottleneck** – The interface with the smallest bandwidth regarding a given channel; also the bandwidth of the channel itself.

**Channel Topology** – The system of various, potentially overlapping channels in space.

**Node** – The location where channels overlap in space; at a node, an event occurs not just as a necessary condition, but as a consequence of all sufficient conditions being met.

**Feedback Loop** – A self-closing channel where every point functions as a node (i.e., the information flow forms a self-sustaining causal chain), and any cut at an arbitrary point results in a two-way interface.

**Residual Uncertainty of Node Output** – The additional informational entropy characteristic of a node, representing the information content of the outgoing (output) event trajectory that cannot be causally derived from the incoming (input) event trajectory.

**Output Surprisal** – The differential of the node's residual uncertainty; the information rate.

### Agent

**Agent** – A contiguous, finite part of space whose boundary surface is exactly the smallest area among the bottlenecks of a feedback loop (the agent-loop). The part of the feedback loop outside the agent is called the agent's environment. The agent and its environment are two distinguished nodes of the loop, and the boundary surface is the interface.

### Concepts Related to the Agent

**Instantaneous Surprisal of the Environment** – The surprisal of the agent's output.

**Instantaneous Surprisal of the Agent** – The surprisal of the environment's output (i.e., the agent's input).

**Life Experience** – The integral of the input information rate over the agent's entire lifespan; it determines the total amount of new information the agent has encountered.

**Experience Intensity** – Life experience averaged over the lifespan.

**Instantaneous Cognitive Load** – The ratio of the input information rate to its local regularity. The higher it is, the more the agent is facing an event unlike anything seen before.

**Cognitive Sacrifice** – The integral of the instantaneous cognitive load; the ratio of the agent's life experience to its global regularity.

**Mental Amortization Rate** – Cognitive sacrifice averaged over the lifespan.

**Agency** – The agent's tendency to surprise its environment.

**Groundedness** – The correlation between a dynamic model (e.g., world model) and the function (e.g., the workings of the world).

## Assumptions

*   Information flow involves energy flow, even if not necessarily in the same direction.
*   Energy flow cannot occur in zero time, nor with infinite power.
*   The space partitioned by the agent and its environment is (practically) infinite.
*   The information density of any finite space is finite, but the state space of an infinite space (the environment) can be infinite, while remaining locally finite.
*   Information processing speed is finite; thus, generating the agent's output takes $>0$ time following the availability of the input.

## Deductions

### Physical Constraints and Limits

**The Finiteness of Bandwidth**
Bandwidth is finite on any physical channel and any cut, including an agent's interface, as the opposite would assume infinite power energy flow. Consequently, a perfectly chaotic event cannot occur in a physical system; however, quasi-chaotic events may exist that exceed the agent's physical limits, thus appearing chaotic from the agent's perspective.

**The Determinism of Bandwidth**
The bandwidth of the interface changes deterministically based solely on the mutual effects of the agent's output and the environment's input on each other's state.

**Constraints on the Agent and Environment**
Neither the agent nor its environment can be omnipotent or omnicognizant, given their finite volume and information density; however, the environment is by definition potentially omnicognizant due to its infinite volume.

**The Necessity of Termination**
An existing agent cannot maintain the surprisal of its environment indefinitely. Since its state space is finite, the environment will eventually "learn" the agent, causing the feedback loop to cease. The agent's survival is possible only because the environment's local cognitive capacities are finite, and the involvement of the global environment takes time due to the finite speed of information flow.

### Absolute Constraints on a Surviving Agent

**The Constraint of Agency**
The existence of the agent's boundary surface and the feedback loop are equivalent (a non-existent feedback loop has no cut, while an existing one always has a cut corresponding to the agent definition).

The maintenance of the feedback loop — and thus the agent — requires continuous mutual surprisal (since no surprise means no information, thus no information flow).

Since the environment (having infinite state space) will statistically always surprise the agent, the agent's survival depends primarily on its own Agency: maintaining bandwidth $>0$ and the ability to surprise the environment.

**The Constraint of a Grounded World Model**
An agent can systematically surprise its environment if:
1.  It is consistently lucky (statistically improbable over time, measured in life experience).
2.  The agent possesses a **World Model** (its state correlates with the input and output trajectories), so that it would "know" what would **not** surprise the environment.

The expected lifespan of an agent correlates positively with the groundedness of its world model. A minimum level of groundedness is a necessary condition for the emergence of an agent.

**Decrease of Surprise received from the Environment as a Side Effect**
The surprise of the input naturally decreases with the groundedness of the world model, but this is merely a side effect; the agent does not survive because it reduces its own surprise, but because it increases the surprise of its output. The latter brings the former with it, as the environment increasingly moves along the path forced upon it by the agent.

**The Necessity of Decision**
If multiple outputs are possible within bandwidth and agency constraints, the agent must decide.

**The Constraint of Goal-Orientedness**
Decision-making is deterministic based on the world model and inputs, thus, from an external observer's perspective/ex-post, a deterministic utility can be assigned to possible outputs (even if only a binary one, eg. 1 for being chosen, 0 for not). Thus, a goal function can be derived that assigns utility to trajectory segments.

**The Inference of the World Model as a Decision Function**
Decision-making can be logically decomposed into enumerating possible outputs, calculating utility, and selecting the output with maximum utility.

The world model itself however contains all information required to do both; inferencing it simply selects the proper output.

Its inference is based on the autocorrelation of past trajectory segments with the current trajectory, and projecting forward on that past trajectory found, eventually finding a survivable/long enough path, also - indirectly - selecting the output required/chosen (the direct continuation of the past trajectory).

**Constraint to Maintain and Develop Physical Structure**
The agent must possess a physical structure (bandwidth) that allows for observation and agency while protecting against physical impacts. This creates a trade-off between sensitivity+actionability (high bandwidth) and protection (low bandwidth), which can be optimized with interface partitioning.

## Constraints on Agents Surviving High Mental Amortization Rates

**The Constraint of Learning**
The world model is never perfectly grounded due to the finite state space of the agent versus the infinite environment; also the (value of the) world model naturally amortizes if the environment or the agent's operation shifts into a phase for which the model is not calibrated; the speed of amortization is proportional to the mental load.

Calibration is maintained through learning (expanding the world model - input and output - trajectories).

**Logging as Learning**
For the world model to change, state changes naturally happening within the agent while sensing and acting (or at least a replica of them) must be permanent and ordered (log-like). This way, sensing and acting automatically - and actually - constitute learning.

**Reciprocal of Momentary Cognitive Load as a Non-Binary Objective Function for Learning**
The problem with a binary goal function is that in case of inaccuracies in the World Model — exactly where learning is most relevant — the agent would only "learn" from its own death.

Instead, the agent must apply a continuous goal function that is proportional to its expected remaining lifespan (measured not in temporal terms, but in the domain of cognitive sacrifice); a trivial choice for this is the reciprocal of momentary cognitive load.

**Proactivity**
While World model-based inference is natively suited for predictions (by following forward the autocorrelated past segment), in the absence of learning, this appears for the external observer as a hard-wired decision or reactive behavior.

With a continuous goal function and learning however, model-based inference becomes true proactivity. Additionally, with reciprocal of momentary cognitive load as the goal function, long-term utility can be "cheaply" calculated on a trajectory.

**Simulation/Exploration**
The inference, necessarily based on a recursive, internal feedback loop (due to autocorrelation) can be supplemented with further recursive inference extending the already extended trajectory segment with further "pieces" — i.e., long-term simulation. The damping of the internal feedback loop's excitation — ensuring the convergence of the simulation — can be provided eg. by temporal discounting (standard or based on life experience); however, none of this is a necessary condition for proactivity.

Such a simulation - driven by the abscense of long correlating past trajectory segments - provides predictions made up of small "bits" of the past, which is naturally ungrounded as a whole; decisions based on such predictions may appear as exploration to an external observer, and is a fundamental tool for recalibrating the world model after experiencing severe cognitivr load. 

**Separation of Mental and Physical State**
High mental amortization requires fast learning (high information density/rapid state change), while physical protection requires the opposite. This necessitates the separation of mental and physical states, forming a **"Figure-8" feedback loop**:
1.  An **External Loop (Interaction)** between the environment and the physical state.
2.  An **Internal Loop (Cognitive)** between the physical state and the mental state.

## Optimization and Heuristics
Agents use several techniques to handle limited capacity which are all based on **Decomposition, Prioritization, Elimination and Materialization.**, eg.:
*   **Abstraction (Lossy compression):** Sacrificing calibration for capacity and processing speed
*   **Semantization:** Abstracting the "log" into semantic memory for faster inference; this necessitates the separation of semantic and episodic memory.
*   **Forgetting:** Deleting less relevant parts of memory, making space for new information
*   **Materialization of Predictions:** Storing utility values within trajectories to allow 1-step predictive lookahead.
*   **Hierarchical Abstraction (Level Of Detail):** Allowing iterative computation that can be halted at any point based on time constraints.
*   **Modularity and Parallelization:** Including goal decomposition, arbitration, and synchronization.

## Interesting Consequences
*   There are no "learned reflexes," only faster autocorrelation due to optimization.
*   There is no "pattern following" as an optimization; rather, everything is pattern following.
*   There is no reinforcement learning, only learning (utility propagation is an optimization speeding up projection, not a separate function; however materialized utility can theoretically be modified afterwards, which can still qualify as RL).
*   There is no separate self-model and environment-model, only a **World Model**.
*   The agent does not minimize its own surprisal; it optimizes (but not necessarily maximizes) the surprisal of the environment. (This resolves the Dark Room Paradox).

## Future Directions
To be complete, this ontology and deduction must be extended with further optimization techniques, their constraints, and application conditions. Furthermore, it should include constraints regarding the behavior, cooperation, and communication (sharing of mental states) of distributed/hierarchical agents.

Subsequently, a "Reference Architecture" for an agent (and agent hierarchy) can be derived. This can then be used for the constructive examination of any agent (e.g., AI, a corporation, biological entities). The basis for this is that an objective function optimized for individual survival (or the survival of a species) can be transformed; an agent architecture good at survival will be efficient in other tasks as well (acknowledging the necessity of survival as well - ie. instrumental convergence, which naturally arises in the form of an objective function assigning utility to trajectories long enough to reach a state goal).

## References
Friston, K. (2010). The free-energy principle: a unified brain theory? Nature Reviews Neuroscience, 11(2), 127-138. doi.org
Friston, K., Thornton, C., & Clark, A. (2012). Free-energy minimization and the dark-room problem. Frontiers in Psychology, 3, 130. doi.org
