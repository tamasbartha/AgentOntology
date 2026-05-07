# (A 'wannabe')Thermodynamics of Agency

*A constraint-grounded, empirically validatable theory of agents*

**Tamás Árpád Bartha**
*May 2026*

---

## Abstract

This work presents a constraint-based theory of agents that compresses the directly observable properties of empirical agents — across eight classes from RNA viroid to human — to a small foundation: five physical constraints (Landauer's energy-information coupling, finite power, spatial unboundedness, the Bekenstein bound, and finite processing speed via Bremermann and Margolus-Levitin) plus one constitutive axiom, the **constructive agent**: a finite region whose boundary is the bottleneck of a feedback loop with its environment. The methodological move is the same one thermodynamics made — compress observed regularities to a small foundation, then derive their consequences.

The framework inverts the Free Energy Principle. Where FEP holds that agents act to minimize the surprise they receive from their environment, this framework derives that agents act to maintain or increase the surprise they exert *on* their environment; reduced received surprise is a side effect, not the optimization target. The Dark Room paradox resolves accordingly: an agent that surprises its environment with nothing fails the survival condition the feedback loop requires.

From the foundation, fifteen subchapters of derivation produce the framework's content: bandwidth finiteness and termination necessity, world model necessity, inference as autocorrelation against logged trajectory, learning as logging, the substrate trade-off forcing a figure-8 architectural split, memory hierarchies, habituation and orienting, layered self-modeling, the optimization gap, the rising-and-falling shape of agent property exhibition over a lifespan, and the internal-grounding bound on individual-agent claims.

The compression succeeds at its scope: all directly observable empirical-layer properties are derived, with substrate-specific particulars deliberately below the framework's level. The framework produces six novel observable predictions and ten falsifications of existing literature claims — including FEP surprise minimization, gradient-based learning as primary cognitive mechanism, and strict goal optimization at the individual agent level. The mutual falsifiability is what makes both sides scientific.

---

## Preamble

### What we wanted

This work began with a practical question: can a goal-oriented project management methodology be built whose adherence is provably necessary and sufficient for reaching the goal? Existing methodologies are functional descriptions and don't show why their activities are necessary. Any such methodology turned out to be functionally equivalent to a distributed agent architecture, so the question became what an agent must be like, derived rather than stipulated.

### What we got

A constraint-based theory that compresses the directly observable properties of empirical agents — across eight classes from RNA viroid to human — to five physical constraints (Landauer, finite power, spatial unboundedness, Bekenstein, Bremermann/Margolus-Levitin) plus one constitutive axiom: the **constructive agent**, a finite region whose boundary is the bottleneck of a feedback loop with its environment. The methodological move is the same one thermodynamics made.

The framework inverts the Free Energy Principle: agents optimize the surprise exerted *on* their environment, not received from it. Reduced received surprise is a side effect; the Dark Room paradox resolves accordingly. The compression succeeds at its scope — all directly observable empirical-layer properties are derived, with substrate-specific particulars deliberately below the framework's level. The framework produces six novel observable predictions and ten falsifications of existing literature claims. The mutual falsifiability is what makes both sides scientific.

### How we did it

Three layers: established physics at the bottom, the constructive agent definition as the framework's only original axiomatic content, and a chain of fifteen subchapters in Chapter 3 deriving the framework's content. Chapter 4 audits the deduction against the empirical layer; Chapter 5 lays out uses of the framework and the extensions still required.

The framework is single-agent. Multi-agent properties and the original methodology goal are deferred. What is developed here is the foundation, not the building.

---

## Table of Contents

- **Abstract**
- **Preamble**
  - What we wanted
  - What we got
  - How we did it
- **How to Read This Document**
- **Chapter 1: Empirical Agents**
  - 1.1 Observable Properties
  - 1.2 Distinguished Examples
  - 1.3 Summary of the Empirical Layer
- **Chapter 2: The Statement**
  - 2.1 The Constructive Agent
  - 2.2 The Central Claim
  - 2.3 The Deductive Bridge
  - 2.4 The Compression Claim
  - 2.5 Developmental Windows
- **Chapter 3: The Deduction**
  - 3.1 Physical Constraints
  - 3.2 The Deductions
  - 3.3 Dependency Tree
- **Chapter 4: What We Achieved**
  - 4.1 Properties We Could Deduce
  - 4.2 Substrate-Specific Particulars
  - 4.3 Implied Non-Observable Structure
  - 4.4 Novel Observable Predictions
  - 4.5 Falsified Literature Claims
- **Chapter 5: Uses and Extensions**
  - 5.1 What This Is Good For
  - 5.2 What Must Be Done to Capitalize on It
- **Terminology** (42 entries)
- **Mathematical Deductions**
  - 3.1 Physical Constraints (formal counterparts)
  - 3.2 The Deductions (formal counterparts)
  - 3.3 Dependency Tree
- **References**

---

## How to Read This Document

The main text is prose. Every claim, every derivation, every observation is written so it can be read in plain language without consulting other sections. The document is designed to be readable straight through.

Two reference apparatuses sit alongside the prose. They serve different purposes and are read in different ways.

**Superscript numbers and the Terminology chapter.** Technical terms are introduced in **bold** at first use, where they are defined in prose. Each term carries a sequence number<sup>see Terminology</sup> the first time it appears, and every subsequent use of the term carries the same superscript number — for example, **agent**<sup>1</sup> at first use, then agent<sup>1</sup> later. The numbers run in order of first appearance through the document, so term 1 appears before term 2, which appears before term 3, and so on.

The Terminology chapter at the back lists all numbered terms with their prose definitions, in the same order. Where a term has a mathematical formalization, it is given there too. The intent is: a reader who wants to look up what a term means can find it by number; a reader who is following the prose does not need to consult the Terminology chapter at all, since the term was defined when first introduced.

Cross-references between Terminology entries are noted explicitly. If two concepts depend on each other, the entries reference one another rather than forcing the reader to chase the connection.

**Mathematical Deductions chapter.** The main text is intentionally light on formalism. Where deductions invoke mathematical apparatus — formal definitions, theorems, integrals, optimization formulations — the formal version is given in the Mathematical Deductions chapter, which sits between Terminology and References.

The Mathematical Deductions chapter uses parallel numbering with Chapter 3. A claim derived in prose at §3.2.5 has its formal counterpart at §3.2.5 of Mathematical Deductions; §3.1.4 in prose corresponds to §3.1.4 in Mathematical Deductions; and so on. Two readers reading at different levels can follow the same logical structure: a prose reader reads §3.1 through §3.3 in Chapter 3; a formal reader reads the same numbered subsections in Mathematical Deductions; both arrive at the same conclusions through differently-detailed derivations.

The framework's substantive content is in the prose. The mathematical chapter exists to make the prose precise where precision is needed, not to add new content. A reader who never opens the Mathematical Deductions chapter will not miss any conclusion of the framework — only some of the formal apparatus underlying particular derivations.

**Reading paths.** Three modes of reading are supported:

- *Straight through.* Read the prose from Preamble to References, treating superscripts as optional reference markers. Skip the Terminology and Mathematical Deductions chapters entirely. The framework's argument is complete this way.
- *With Terminology lookups.* Read the prose, consulting Terminology when an unfamiliar term needs clarification or when reviewing a definition. Useful for readers new to the framework or returning after a break.
- *With Mathematical Deductions cross-references.* Read both Chapter 3 prose and Mathematical Deductions §3 in parallel, using the matching numbering. Useful for readers who want to verify derivations formally or to use the framework's machinery in their own work.

The document does not require the reader to choose one mode at the outset. Modes can be mixed: read prose, dip into Terminology for one term, dip into Mathematical Deductions for one derivation, return to prose. The references are organized to support intermittent consultation as much as continuous reading.

---

## Chapter 1: Empirical Agents

Empirically, we call **agents**<sup>1</sup> entities that exhibit some of the **directly observable**<sup>2</sup> properties listed below. Agency is identified empirically rather than stipulated theoretically: an entity is an agent insofar as it exhibits one or more of these properties. The properties are partitioned into three types — **structural**<sup>3</sup>, **state**<sup>4</sup>, and **behavioral**<sup>5</sup> — and each is tagged with the **cognitive role**<sup>6</sup> it serves. The methodological constraint throughout is that observations must be direct, with granularity symmetric across types: we don't grant ourselves arbitrary precision on one axis while staying coarse on another.

### 1.1 Observable Properties

The properties below are the ones we count as empirical evidence of agency. Each is phrased so that verification requires only direct observation<sup>2</sup> — measurement of substrate, structure, response, or behavior — without attribution of internal representations, goals, or models. Cognitive roles<sup>6</sup> serve as an organizing tag: **integrity**<sup>7</sup>, **sensing**<sup>8</sup>, **action**<sup>9</sup>, **internal communication**<sup>10</sup>, **information storage**<sup>11</sup>, and **internal differentiation**<sup>12</sup>. Where a property serves multiple roles, the primary one is listed first.

#### 1.1.1 Structural Properties

| Property | Cognitive role | Observable how |
|---|---|---|
| The entity has a physical boundary distinguishable from the surrounding environment | Integrity<sup>7</sup> | Direct observation, dissection, microscopy |
| The boundary persists for a measurable duration without dissolving | Integrity<sup>7</sup> | Observation over time |
| Some regions of the entity are more disruption-tolerant than others (e.g., outer layers vs. inner regions) | Integrity<sup>7</sup>, internal differentiation<sup>12</sup> | Mechanical/chemical perturbation tests |
| Specific regions are dedicated to receiving environmental inputs (transducers, receptors, sensory surfaces) | Sensing<sup>8</sup> | Anatomical observation, perturbation tests confirming role |
| Specific regions are dedicated to producing environmental outputs (effectors, actuators, glands) | Action<sup>9</sup> | Anatomical observation, perturbation tests confirming role |
| Internal pathways connect input-receiving regions to output-producing regions | Internal communication<sup>10</sup> | Anatomical observation, signal-tracing |
| The entity's internal organization is differentiated into subsystems with measurably different properties | Internal differentiation<sup>12</sup> | Microscopy, dissection, comparative measurement of regions |
| Persistent patterns or configurations exist that change with the entity's history of interactions | Information storage<sup>11</sup> | Comparative observation across entities with different histories |
| The substrate of input/output regions differs from the substrate of internal-processing regions | Internal differentiation<sup>12</sup> | Substrate composition analysis |
| Material in the entity turns over while its organization persists | Integrity<sup>7</sup> | Long-duration observation, isotope tracking |

#### 1.1.2 State Properties

| Property | Cognitive role | Observable how |
|---|---|---|
| The entity maintains internal temperature within a measurable range, distinct from environmental temperature | Integrity<sup>7</sup> (homeostasis) | Thermometry |
| Internal chemical concentrations are maintained within ranges narrower than environmental variation | Integrity<sup>7</sup> (homeostasis) | Biochemical assay |
| Internal electrical potentials at specific sites stay within measurable ranges and respond to inputs | Internal communication<sup>10</sup>, integrity<sup>7</sup> | Electrode recording |
| Energy reserves (chemical, mechanical) are maintained at measurable levels and depleted by activity | Integrity<sup>7</sup>, action<sup>9</sup> readiness | Mass measurement, biochemical assay |
| Hydration or solvent content is maintained within ranges | Integrity<sup>7</sup> | Mass and composition measurement |
| Internal pressure is maintained within ranges (hydrostatic, gas, mechanical) | Integrity<sup>7</sup> | Pressure measurement |
| Specific state variables shift measurably in anticipation of repeated external events | Information storage<sup>11</sup>, action<sup>9</sup> readiness | Comparative measurement before/after repeated stimuli |

#### 1.1.3 Behavioral Properties

| Property | Cognitive role | Observable how |
|---|---|---|
| The entity produces measurable outputs across its boundary (chemical, mechanical, electrical) | Action<sup>9</sup> | Direct observation, output measurement |
| Outputs follow inputs with measurable, finite delay | Action<sup>9</sup>, internal communication<sup>10</sup> | Stimulus-response timing |
| Output magnitude or character varies with input magnitude or character | Sensing<sup>8</sup>-action<sup>9</sup> coupling | Stimulus-response measurement |
| Repeated similar inputs produce outputs with measurably different intensity over time | Information storage<sup>11</sup> (**habituation**<sup>13</sup>) | Repeated-stimulus protocols |
| Novel inputs produce outputs of measurably different character than familiar inputs | Information storage<sup>11</sup>, sensing<sup>8</sup> | Novelty/familiarity protocols |
| The entity produces outputs that reduce or terminate disruptive inputs (withdrawal, avoidance) | Self-protection, integrity<sup>7</sup> | Aversive-stimulus protocols |
| The entity produces outputs that increase or sustain favorable inputs (approach, ingestion) | Action<sup>9</sup>, integrity<sup>7</sup> | Resource-directed-behavior protocols |
| The entity ceases producing outputs eventually (**termination**<sup>14</sup>) | (Termination signature) | Long-duration observation |
| Output variability is measurably lower under stable input conditions than under novel ones | Information storage<sup>11</sup> | Comparative measurement across input regimes |
| The entity's response to a paired stimulus changes after pairing experience (associative behavior) | Information storage<sup>11</sup> | Pairing protocols |
| Output character changes in response to depletion or repletion of state variables | State<sup>4</sup>-action<sup>9</sup> coupling | State-manipulation protocols |
| Specific outputs are produced only when specific input conditions co-occur | Sensing<sup>8</sup>-action<sup>9</sup> coupling, integration | Conditional-stimulus protocols |
| Internal communication<sup>10</sup> (signals between regions) precedes the output that depends on it | Internal communication<sup>10</sup> | Recording from multiple regions during behavior |

### 1.2 Distinguished Examples

The following eight classes span the range of empirical agents from minimal cases to maximum **single-agent**<sup>15</sup> complexity. Each class is represented by a species chosen for being well-studied; the class is what carries the framework's empirical weight, not the specific species. For each, the properties from §1.1 that the class exhibits are listed, observed at granularity appropriate to the class.

Multi-agent phenomena are excluded throughout. Where social species are listed (rodents, humans), only their single-agent<sup>15</sup> properties are described; their colony, group, or societal behaviors are out of scope.

#### 1.2.1 Replicator (RNA viroid)

*Representative: Potato spindle tuber viroid (PSTVd) or similar RNA-only entity*

The minimal case. A folded RNA molecule that catalyzes its own replication when in a suitable chemical environment, exhibits structural<sup>3</sup> integrity<sup>7</sup> through base-pairing, and chemically interacts with its environment.

Structural<sup>3</sup> properties exhibited: physical boundary (the folded structure delimits the molecule from its solvent); persistent organization (the secondary structure persists for measurable durations); regions with different chemical accessibility (outer loops vs. inner stems).

State<sup>4</sup> properties exhibited: maintenance of folded state within environmental ranges (the molecule unfolds outside specific temperature/pH windows).

Behavioral<sup>5</sup> properties exhibited: produces outputs across its boundary (binds host machinery, alters cellular processes); outputs follow inputs with finite delay (binding kinetics); output character varies with input (different chemical environments produce different folding states and different binding partners).

What this class does *not* clearly exhibit: dedicated sensing<sup>8</sup>/action<sup>9</sup> regions distinct from each other; internal differentiation<sup>12</sup> in any complex sense; learning in any standard sense; self-protective behavior. The viroid is at the edge of the empirical agent<sup>1</sup> category — it exhibits some properties but not many. Its inclusion tests whether the framework can speak about minimal cases.

#### 1.2.2 Single-celled organism with full structural inventory (Bacterium)

*Representative: Escherichia coli*

Single-celled but with all six structural<sup>3</sup> roles present in primitive form. Cell membrane and wall (integrity<sup>7</sup>), chemoreceptors (sensing<sup>8</sup>), flagella (action<sup>9</sup>), cytoplasmic signaling and second messengers (internal communication<sup>10</sup>), DNA modifications and protein expression states (information storage<sup>11</sup>), organelles and membrane microdomains (internal differentiation<sup>12</sup>).

Structural<sup>3</sup> properties: full inventory listed above. Substrate differences: membrane lipids vs. cytoplasmic proteins vs. nucleic acids — substantially different chemical character. Material turnover: high (proteins replaced on minute-to-hour timescales) while organization persists.

State<sup>4</sup> properties: temperature tolerance ranges; pH homeostasis (proton motive force); osmotic pressure regulation; metabolic state (ATP/ADP ratios). Energy reserves measurable as glycogen, polyhydroxybutyrate, or similar.

Behavioral<sup>5</sup> properties: chemotaxis (graded response to chemical gradients); habituation<sup>13</sup> to sustained stimuli (receptor methylation produces measurable adaptation); avoidance of toxins; approach to nutrients; finite response delay; pairing-based behavior in some contexts (lac operon induction is one example of conditional response).

What this class establishes empirically: the full structural<sup>3</sup> inventory can exist at the single-cell scale. The framework's claims about agent<sup>1</sup> structure aren't reserved for complex animals.

#### 1.2.3 Single-celled organism with motor learning (Ciliate)

*Representative: Paramecium aurelia*

Single-celled like the bacterium but with a more elaborate cytoskeleton, ciliary motor system, and well-documented behavioral<sup>5</sup> plasticity. The eukaryotic cell architecture allows for more internal differentiation<sup>12</sup> (nucleus, organelles, cytoskeletal compartments) than the bacterial case.

Structural<sup>3</sup> properties: as in 1.2.2 plus more pronounced internal differentiation<sup>12</sup> (membrane-bound organelles, distinct cortical regions, nuclear compartmentalization).

State<sup>4</sup> properties: as in 1.2.2 with finer regulatory ranges; ciliary beat coordination as a measurable internal-communication<sup>10</sup> signal.

Behavioral<sup>5</sup> properties: as in 1.2.2 plus habituation<sup>13</sup> to repeated mechanical stimuli (well-documented in *Paramecium*); avoidance learning; some evidence of associative behavior change. Output variability lower under repeated similar conditions than under novel ones.

What this class establishes: learning-related behavioral<sup>5</sup> changes are observable at the single-cell scale, distinct from the simpler stimulus-response patterns of bacteria. The empirical category of "agent<sup>1</sup> that learns" is not reserved for nervous-system-bearing entities.

#### 1.2.4 Plant with rapid response (Sensitive plant)

*Representative: Mimosa pudica or Dionaea muscipula (Venus flytrap)*

Multicellular, sessile, non-animal. Tests whether the framework's empirical category extends to entities outside the animal kingdom. Plants have been documented to exhibit habituation<sup>13</sup>, conditional response, and possibly associative behavior.

Structural<sup>3</sup> properties: differentiated tissues (epidermis, vascular bundles, mesophyll); specialized sensing<sup>8</sup> structures (trigger hairs in *Dionaea*, mechanosensors in *Mimosa*); action<sup>9</sup> structures (pulvini in *Mimosa* generate the leaf-folding response; trap-closing mechanism in *Dionaea*); internal communication<sup>10</sup> via electrical signals and hormonal pathways; information storage<sup>11</sup> in the form of post-translational modifications, calcium states, and possibly epigenetic marks; clear internal differentiation<sup>12</sup>.

State<sup>4</sup> properties: turgor pressure regulation; ion concentration gradients; electrical potentials across cells and tissues; energy reserves in starch and sucrose; hydration regulation.

Behavioral<sup>5</sup> properties: rapid mechanical responses to touch (output following input with finite delay); habituation<sup>13</sup> to repeated touch (well-documented in both species); conditional responses (Venus flytrap requires multiple trigger contacts within a window before closing — measurable counting behavior); learning-related changes after repeated exposure.

What this class establishes: the empirical agent<sup>1</sup> category includes entities very different from animals. Whatever foundation we eventually propose must accommodate plants alongside animals — they exhibit overlapping property sets despite radically different substrates.

#### 1.2.5 Minimal nervous system (Nematode)

*Representative: Caenorhabditis elegans*

The simplest organism with a fully-mapped nervous system (302 neurons in the hermaphrodite). Provides a minimal case for studying agents<sup>1</sup> whose information storage<sup>11</sup> substrate is specifically neural.

Structural<sup>3</sup> properties: full inventory; nervous system as a discrete and traceable internal-communication<sup>10</sup> and information-storage<sup>11</sup> substrate; distinct sensory neurons, motor neurons, and interneurons; muscle structures for locomotion and feeding.

State<sup>4</sup> properties: full inventory at the metazoan level; neuronal membrane potentials, neurotransmitter levels, energy reserves at scale.

Behavioral<sup>5</sup> properties: chemotaxis with multiple modalities (gradient climbing, avoidance); habituation<sup>13</sup> to repeated mechanical stimuli; classical conditioning (pairing of food/temperature/odor produces measurable behavioral changes); state-dependent behavior (foraging vs. quiescence based on food availability and developmental stage); response variability that decreases with familiar stimuli.

What this class establishes: the full property inventory is observable in agents<sup>1</sup> with the simplest possible neural substrate. Complex behavior doesn't require complex hardware.

#### 1.2.6 Distributed nervous system (Cephalopod)

*Representative: Octopus vulgaris or related species*

Non-vertebrate complex cognition with an unusual neural architecture: roughly two-thirds of neurons are in the arms rather than the central brain. Tests whether the framework's structural<sup>3</sup> and behavioral<sup>5</sup> claims hold under cognitive architectures that differ substantially from the vertebrate plan.

Structural<sup>3</sup> properties: full inventory; multiple semi-autonomous neural processing centers; sophisticated sensing<sup>8</sup> (chemotactile arms, complex eyes, pigment-based skin display); high internal differentiation<sup>12</sup>; specialized action<sup>9</sup> structures (chromatophores, suckers, jet propulsion).

State<sup>4</sup> properties: full inventory; multiple-loop circulatory system; complex hormonal regulation.

Behavioral<sup>5</sup> properties: full inventory; well-documented learning (including observational learning of conspecifics, though that's at the multi-agent edge of our scope); problem-solving behavior; tool use in some species; rapid associative learning; rich response repertoire under varied input conditions.

What this class establishes: the structural<sup>3</sup> and behavioral<sup>5</sup> patterns are not specific to vertebrate-style centralized nervous systems. Whatever foundation we propose must accommodate distributed-cognition agents<sup>1</sup> alongside centralized ones.

#### 1.2.7 Mammalian default (Rodent)

*Representative: Mus musculus or Rattus norvegicus*

A standard reference case for vertebrate cognition. Well-studied across structural<sup>3</sup>, state<sup>4</sup>, and behavioral<sup>5</sup> dimensions. Default complex agent<sup>1</sup>.

Structural<sup>3</sup> properties: full inventory at vertebrate scale; centralized nervous system with measurable functional regionalization (sensory cortices, motor cortex, hippocampus, etc., distinguishable by anatomy and lesion effects); diverse effector systems (locomotor, manipulative, vocal); sophisticated sensing<sup>8</sup> (vision, audition, olfaction, somatosensation); endocrine integration with neural processing.

State<sup>4</sup> properties: full inventory at vertebrate scale; thermoregulation; multi-system homeostasis; energy reserves in multiple substrates; circadian state oscillations measurable in body temperature, hormone levels, activity.

Behavioral<sup>5</sup> properties: full inventory; rich learning (operant, classical, spatial, observational); episodic-like memory phenomena (measurable behaviorally without claiming the internal experience); state<sup>4</sup>-dependent behavior; novelty responses; habituation<sup>13</sup>; conditional responding; behavioral plasticity over the lifetime.

What this class establishes: the empirical agent<sup>1</sup> category at standard vertebrate complexity. Most experimental agent science draws from this class.

#### 1.2.8 Maximum single-agent complexity (Human)

*Representative: Homo sapiens, observed in single-agent<sup>15</sup> contexts*

The maximum case within our single-agent<sup>15</sup> scope. Multi-agent properties (language as communication, social cognition, cooperative behavior) are excluded; only properties observable in a single human are listed.

Structural<sup>3</sup> properties: full inventory at maximum vertebrate complexity; pronounced regional specialization in the nervous system; complex sensorimotor integration; tool use as observable extended action.

State<sup>4</sup> properties: full inventory; rich physiological state monitoring; reportable internal states (the *report* is observable; what it is a report *of* is inferential and out of scope here).

Behavioral<sup>5</sup> properties: full inventory plus extensive single-agent<sup>15</sup> behaviors observable without invoking social context: long planning sequences; flexible response to varying conditions; extensive learning across domains; problem-solving in solitary contexts; tool construction and use; behavior that varies measurably with state<sup>4</sup> in ways not seen at lower complexity. Output variability is high under novel conditions, low under highly familiar ones.

What this class establishes: the upper end of single-agent<sup>15</sup> complexity. The empirical patterns at this level are richer than at lower classes but qualitatively share the same property categories — the framework should produce a unified treatment across the range from §1.2.1 to §1.2.8 rather than treating humans as a separate kind of entity.

### 1.3 Summary of the Empirical Layer

The eight classes span from minimal (RNA viroid) to maximum single-agent<sup>15</sup> complexity (human), exhibiting overlapping but graded sets of structural<sup>3</sup>, state<sup>4</sup>, and behavioral<sup>5</sup> properties. No class exhibits all properties; no two classes have identical property profiles. The empirical claim is that these entities, despite their substrate diversity, exhibit patterns from a common space of properties — and that this empirical observation is what calls for a compression.

The compression itself — the small foundation from which these properties follow as consequences — is the work of subsequent chapters.

---

## Chapter 2: The Statement

The empirical layer in Chapter 1 describes what we observe. This chapter states what the document claims about what we observe. Three things happen here: a constructive definition of what counts as an agent, a falsifiable empirical claim about what these agents do over time, and a deductive bridge from the claim to physical foundations. A subsidiary claim about developmental windows is added at the end, with the derivation deferred to §4.1.1.

### 2.1 The Constructive Agent

Beyond the empirical category established in Chapter 1, we now propose a specific constructive definition that picks out agents by their topological structure rather than by their observable properties. The two definitions — empirical and constructive — are meant to coincide: the document's central thesis is that any entity matching the constructive definition exhibits the empirical properties, and vice versa.

The constructive definition rests on three concepts. A **feedback loop**<sup>16</sup> is a self-closing channel in which information flows around a cycle, each segment of the loop driving the next. A **bottleneck**<sup>17</sup> is the narrowest place along such a loop — the point of least information-carrying capacity. A **constructive agent**<sup>18</sup> is a finite, contiguous region of space whose boundary is the bottleneck of a feedback loop. Loosely: an agent is a thing with a narrow channel to its environment, where "narrow" is defined relative to the rest of the loop.

The boundary may be sharp — a single well-defined surface, as in a cell membrane or an animal's skin — or it may be a band, a region within which the bottleneck is found without exact localization, as in a bacterial colony or a cloud of correlated computational processes. Both cases satisfy the definition; the framework derives different consequences for each kind of boundary.

The agent's existence is bound up with the feedback loop's: there is no agent without a loop to its environment. The constructive definition makes this dependency explicit. An agent is not a thing in isolation; it is a thing in a particular kind of relationship with what surrounds it.

A note on the framework's stance toward what the agent does. The standard statement of the **Free Energy Principle**<sup>19</sup> proposes that agents act to minimize the surprise they receive from their environment. This document's framework inverts that statement: agents act to maintain or increase the surprise they exert *on* their environment. The minimization of received surprise is a side effect, not the goal. Whether this inversion is correct is one of the things the rest of the document argues; for now, it is the optimization stance the framework adopts.

### 2.2 The Central Claim

The central empirical commitment of this document, stated as falsifiably as we can manage:

**Claim.** For any constructive agent<sup>18</sup>, the probability that it exhibits behavioral<sup>5</sup> and learned-state<sup>4</sup> properties from §1.1 at time *t* has a characteristic shape with respect to *t* (clock time elapsed since agent formation): rising during the agent's developmental and mature phases, falling during the **termination phase**<sup>14</sup>. The rate of rise correlates with the information rate of the agent's environment; the rate of fall correlates with the substrate's degradation rate.

The restriction to behavioral<sup>5</sup> and learned-state<sup>4</sup> properties matters. Structural<sup>3</sup> and innate-state properties are largely present at agent formation — a newborn vertebrate has its sensing<sup>8</sup> and action<sup>9</sup> structures from the start. These properties depend on the substrate's *capacity* for cognition rather than on what the agent has accumulated through experience. The claim above is about properties that develop with experience: habituation<sup>13</sup>, conditional responding, novelty discrimination, learning-related variability changes.

The claim is falsifiable in several ways. An agent in a sufficiently entropic<sup>20</sup> environment that ages without any rise in behavioral or learned-state property exhibition would count against it. A class of agents that show no terminal-phase decline despite substrate degradation would count against it. A reliable pattern of property exhibition that doesn't track time at all — that emerges fully formed at any age — would count against it. The pattern the claim predicts is well-documented across the eight classes in §1.2 (development → maturity → senescence), but specific quantitative tests can be designed.

The claim is computationally simulable. Given an implementation of the constructive agent<sup>18</sup> definition placed in a simulated environment, the observable properties from §1.1 can be operationalized as detectors, and their exhibition can be tracked over the agent's simulated lifespan. The claim predicts a specific shape for the resulting curve. Mismatch between predicted and simulated shapes would constitute internal evidence against the framework.

### 2.3 The Deductive Bridge

The central claim above states what is observable. This section states why the observation should hold, by bridging clock time to a quantity the framework derives.

A measurable property of any agent's experience is its **cognitive sacrifice**<sup>21</sup>: the integrated cost over the agent's life of how surprising its inputs have been, weighted by how predictable those inputs could have been from the agent's perspective. An agent in a perfectly predictable environment would accumulate no cognitive sacrifice; an agent in an environment that constantly produces unprecedented events would accumulate it rapidly. Real environments fall between these extremes.

In any **entropic environment**<sup>20</sup> — that is, in any environment where the second law of thermodynamics applies and information continues to be generated over time — the agent's input information rate is positive at almost all times. Cognitive sacrifice<sup>21</sup> therefore accumulates monotonically: it can grow more slowly or more quickly depending on environmental richness, but it cannot decrease and cannot stay zero indefinitely. Clock time and accumulated cognitive sacrifice<sup>21</sup> are coupled by construction.

This is the deductive bridge. Clock time correlates with cognitive sacrifice<sup>21</sup> because the environment is entropic. Cognitive sacrifice<sup>21</sup>, the framework will argue in subsequent chapters, drives the agent's development of behavioral<sup>5</sup> and learned-state<sup>4</sup> properties through learning and the maintenance of an internal model. Therefore clock time correlates with property exhibition. The empirical claim of §2.2 is what we observe; the bridge is why.

The bridge also explains the falling phase. Eventually the substrate degrades, learning rates fall below baseline forgetting rates, and accumulated competence reverses. The substrate's integrity<sup>7</sup> properties — the structural<sup>3</sup> capacity for cognition — set both the upper bound on what cognitive sacrifice<sup>21</sup> can support and the timeline over which support is sustained. Termination<sup>14</sup> is forced by this bound.

### 2.4 The Compression Claim

The document's overall thesis can now be stated. The compression claim is that all the behavioral<sup>5</sup> and learned-state<sup>4</sup> properties from §1.1 — the directly observable<sup>2</sup> regularities of empirical agents — follow as consequences of two things together: the constructive agent<sup>18</sup> definition of §2.1, and the established physical bounds (thermodynamics, finite information density, finite processing speed). No additional structure about agents is required.

This is a compression in the same sense thermodynamics compressed many heat-related observations to a few laws. Many specific regularities reduce to a small foundation. The remainder of the document works out the compression: which properties follow from which combinations of definition and physics, what the chains of inference look like, where the claims hold strictly versus where they hold on average across populations of agents, and where auxiliary assumptions would be needed to extend the framework further.

The empirical pattern of §2.2 — property exhibition rising and falling with time — is the integrated empirical signature of this compression. If the compression holds, the pattern follows. If the pattern systematically fails, the compression is wrong.

### 2.5 Developmental Windows

A pattern observed empirically across many agent classes is that specific properties tend to be most readily acquired during specific windows in the agent's development, with acquisition becoming harder or impossible outside those windows. Critical periods for sensory development, sensitive periods for various forms of learning, ordered acquisition of motor competencies — these are well-documented in vertebrates and observed in modified forms in other classes.

**Claim:** For any constructive agent<sup>18</sup>, the properties from §1.1 exhibit characteristic developmental windows during the agent's lifespan in which acquisition probability peaks. These windows respect a partial ordering imposed by the dependency relations among the framework's derivations: where one property's prerequisites depend on another property having been acquired, the dependent property's window opens later.

The claim is derivable from the framework's deductive content — see §4.1.1 for the derivation. It is consistent with the central claim of §2.2 but stronger: it commits to ordered windows rather than just monotonic accumulation. The strong form sometimes encountered in developmental literature — total ordering across all properties — is *not* derivable (and probably wrong as stated, since different agent classes show different total orderings consistent with the same partial order). The derivable form is the partial-ordering claim.

---

## Chapter 3: The Deduction

This chapter performs the actual derivation of the framework's content from physical first principles plus the constructive agent<sup>18</sup> definition. The work proceeds in three stages: deriving the physical constraints we will rely on (§3.1), deriving the observable and implied properties of agents (§3.2), and presenting the dependency tree that connects everything (§3.3). The accounting of which properties were successfully derived and which were not is deferred to Chapter 4.

The chapter does not assume the physical constraints as axioms; it derives them. Each is shown to follow from established physical results (thermodynamics, quantum mechanics, relativity, cosmological observation), with the framework adding only the agent definition as original constitutive content. The deductions in §3.2 then use the constraints as established results, building each subsequent claim on its predecessors until the empirical properties of Chapter 1 are reached.

Where prose deductions invoke mathematical apparatus, the formal version is given in the **Mathematical Deductions** chapter following Terminology, with parallel numbering. A claim derived in §3.2.5 has its formal counterpart in Mathematical Deductions §3.2.5.

### 3.1 Physical Constraints

The framework rests on five physical constraints. None is original to this document; each is a known result from established physics, derived here at the level of detail needed to be used in §3.2. Citations to original sources are given in each subsection.

#### 3.1.1 Energy-information coupling (Landauer)

The first physical constraint we need is that information flow is coupled to energy flow: every transfer or transformation of information requires nonzero energy expenditure. The directions of the two flows are not the same — information can flow opposite to net energy transfer in many cases — but the magnitudes are linked: nonzero information requires nonzero energy.

This constraint follows from Landauer's principle, established in 1961 and confirmed experimentally many times since. Landauer showed that erasing one bit of information in a physical system requires dissipating at least $kT\ln 2$ of energy, where $k$ is Boltzmann's constant and $T$ is the temperature of the surrounding heat bath. The result was originally proven for logical erasure but has been extended to information transformation more generally: any operation that distinguishes information-carrying states from each other must dissipate energy proportional to the information content distinguished.

For the framework's purposes, the precise form of the bound matters less than its existence. Information flow across any interface — including the agent's boundary — involves some amount of energy flux, with the energy cost scaling at minimum with the information content. There is no information transfer that costs no energy.

This rules out, in principle, agents with infinite-bandwidth interfaces operating at zero energy cost. It also rules out information-only models of agency that don't track the energetic substrate — the energetic dimension is forced to be present in any physical theory of agents.

#### 3.1.2 Finite power (second law and relativity)

The second physical constraint is that energy flow cannot be arbitrarily fast or arbitrarily concentrated. Every interface, every channel, every region has bounded power: a maximum rate of energy throughput that physics will not let you exceed.

This constraint has two sources. The second law of thermodynamics imposes that entropy production rates are bounded by the system's capacity to dissipate; runaway power flow would imply unbounded entropy production, which the second law disallows. Relativistic causality imposes that energy cannot propagate faster than light, so the rate at which energy can cross any boundary of fixed area is bounded by the energy density times $c$ — a finite number for any physical configuration.

Together these constraints mean: for any interface in physical space, there exists a finite upper bound on the rate of energy flux across it. Composed with the energy-information coupling of §3.1.1, this yields a finite upper bound on the rate of information flux across any interface. Bandwidth is finite.

The framework uses this constraint repeatedly. The agent's boundary has finite bandwidth; the agent's internal interfaces have finite bandwidth; the bottleneck of the feedback loop has the smallest bandwidth among loop interfaces, and that smallest bandwidth is what the agent's existence is defined relative to. None of this would be coherent without finite power as a starting point.

#### 3.1.3 Spatial unboundedness (cosmological)

The third constraint is observational rather than theoretical: the spatial environment in which agents exist is, for all practical purposes, unbounded. The observable universe is finite but on the order of $10^{27}$ meters across — vastly larger than any agent we will consider. No agent ever encounters the boundary of physical space; effectively, $\Omega$ extends without limit beyond any agent's reach.

This is not a mathematical theorem; it is a feature of the universe we live in. Agents in radically smaller universes (a finite simulation, a closed laboratory environment) would experience environments that are bounded. For such cases, the framework's claims that depend on this constraint would need adjustment. But for biological and engineered agents in our actual universe, the unboundedness assumption is empirically reliable.

The framework's use of this constraint is crucial for the termination derivation: an unbounded environment means the agent has effectively infinite state space available, which combined with the agent's finite capacity (§3.1.4) forces eventual termination. A bounded environment with state space comparable to or smaller than the agent's would not produce the same conclusion.

#### 3.1.4 Local information density (Bekenstein)

The fourth constraint is that information density is locally finite. For any bounded region of physical space, the maximum amount of information that can be stored within it is bounded above. This bound depends on the region's energy content and surface area, but for any fixed bounded region, the bound is a definite finite number.

This constraint follows from the Bekenstein bound, derived in 1973 from black hole thermodynamics. Bekenstein showed that the maximum entropy (and therefore information content) of any physical system contained in a region of radius $R$ with energy $E$ is bounded by $S \leq 2\pi RE/(\hbar c \ln 2)$. The bound is saturated by black holes; everything else achieves less. For any finite region with finite energy content, the information capacity is finite.

For the framework, this constraint applies to the agent. The agent's region has finite volume by the agent definition; therefore the agent has finite energy content; therefore the agent has finite information capacity. The agent cannot hold an unbounded model, an unbounded log, or an unbounded representation of any kind.

The constraint also applies to local regions of the environment, but not to the environment as a whole — by §3.1.3, the environment is unbounded, so its total information capacity may be unbounded too. The asymmetry between the agent's bounded capacity and the environment's potentially-unbounded capacity is the load-bearing feature for several derivations in §3.2.

#### 3.1.5 Finite processing speed (Bremermann, Margolus-Levitin)

The fifth constraint is that information processing takes finite time. No agent can produce an output instantaneously following an input; every operation has a strictly positive minimum duration.

This constraint has two sources from quantum mechanics applied to computation. The Bremermann limit, derived in 1967, gives the maximum number of computational operations per unit mass-energy: $1.36 \times 10^{50}$ operations per second per kilogram. The Margolus-Levitin theorem, derived in 1998, gives the minimum time for a quantum system of energy $E$ to evolve to an orthogonal state: $\tau_{\min} \geq h/(4E)$, where $h$ is Planck's constant. Both place lower bounds on operation duration that are strictly positive for any physical system with finite energy.

The agent has finite energy (by §3.1.4 plus the agent's bounded volume and bounded energy density). Therefore the agent's minimum operation time is strictly positive. There is no instantaneous decision; every output requires processing time after the input becomes available.

This constraint is what makes deadlines real for the framework. The agent must respond to input within some window or fail; the response cannot be instantaneous; therefore some inputs are too fast for the agent to respond to. The framework's derivation of hierarchical inference, working memory, and many other features depends on this fact.

### 3.2 The Deductions

This section derives the framework's content from §3.1 and the constructive agent<sup>18</sup> definition. Each subsection performs one deductive step. Subsections build on each other: where a deduction depends on an earlier one, the dependency is noted explicitly. The accounting of which §1.1 properties were derived and which were not is in Chapter 4.

#### 3.2.1 Bandwidth finiteness and termination necessity

Two foundational results that go together because the second uses the first.

*Bandwidth finiteness.* By §3.1.1, information transfer requires energy flow. By §3.1.2, energy flow is bounded in rate at any interface. Composing: information flow rate at any interface is bounded above by a finite quantity, which we call the interface's **bandwidth**<sup>22</sup>. This applies to every interface in physical space — including the agent's boundary $\partial$, the bottleneck<sup>17</sup> defining the agent, and any internal interfaces partitioning the agent's region.

*Termination necessity.* By §3.1.4, the agent has finite information capacity. By §3.1.3, the environment has effectively unbounded extent and (typically) unbounded total capacity. Over time, the environment's observation of the agent's outputs accumulates; this observation is bounded only by the environment's local capacity, which by §3.1.4 is finite per-region but cumulatively grows. Eventually, the environment's accumulated observation captures the agent's output distribution well enough to anticipate it. When this happens, the agent's outputs no longer surprise the environment — the feedback loop's required mutual surprisal fails — and the agent ceases to exist as an agent. Termination<sup>14</sup> is not optional; it is forced by the asymmetry between bounded agent capacity and unbounded environmental observation.

The proof requires care about timescales: termination is forced eventually but not soon. The environment's observation accumulates slowly relative to the agent's processing speed; the agent's lifespan is the window during which its capacity exceeds the environment's accumulated knowledge of it. Substrate degradation accelerates this — as the agent's effective capacity falls, the gap closes faster.

#### 3.2.2 World model necessity

The agent must contain something correlating with what would not surprise the environment. Otherwise, sustained surprisal of the environment over a non-trivial lifespan is statistically improbable.

The argument: an agent's outputs in the absence of any structure for predicting environmental responses would be effectively random from the environment's standpoint. The environment's entropy of the agent's outputs would be high; surprisal would persist. But this scenario also means the agent is producing outputs without sensitivity to environmental state — a constraint the feedback-loop definition rules out, since a feedback loop requires the agent's outputs to depend on inputs.

So the agent's outputs depend on inputs. The dependence must be such that environmental surprisal is sustained. Random agent-output mappings would, over time, produce environments that adapt and predict — accelerating termination per §3.2.1. Therefore the agent's input-output mapping must reflect *something about the environment* — must contain regularities that produce environment-surprising outputs systematically rather than by chance.

This something is the agent's **world model**<sup>23</sup>. We do not yet specify its form; we have established only that it must exist as some persistent structure within the agent that correlates the agent's outputs with patterns the environment hasn't yet learned. The expected lifespan of the agent correlates positively with the world model's quality.

#### 3.2.3 Inference as autocorrelation

Given the world model exists, what form does it take? The constraint is: the agent must use it to produce outputs given inputs. This requires a mechanism — call it **inference**<sup>24</sup> — that takes (model, current input) and produces an output.

The world model's content comes from the agent's history. By §3.1.4, the agent has bounded capacity, so its model cannot encode arbitrary information about the environment in advance. Whatever the model contains was acquired through the agent's interactions. The only persistent record the agent has access to is its own past trajectory of inputs and outputs.

Given this record, what mechanisms can produce useful outputs? The mechanism must extract structure from the record relevant to the current situation. Among possible mechanisms:

- *Lookup by similarity.* Find a past situation resembling the current one and use the past response. This requires similarity-matching against the record — autocorrelation.
- *Compressed parametric model with explicit updates.* Encode the trajectory's regularities into compressed parameters via some learning rule, then apply parameters to produce current output. This requires a parametric structure beyond the trajectory record itself, which by §3.1.4 limits how much can be stored, and which raises the question of what update rule is used (and how that rule itself is represented in the agent).

The first mechanism uses the trajectory record directly. The second requires additional representational structure beyond the record. By parsimony — and by what the framework's bounded-capacity foundation actually supports — we adopt the first: inference is autocorrelation against the trajectory record. The current input window is matched against past windows; the matched template is projected forward; the projection is the agent's output.

This is not stipulation. It follows from: (i) the agent has no representational structure other than its trajectory record (any additional structure must itself be in $M$, recursing); (ii) the only operation that uses such a record's actual contents is similarity-matching. Inference-as-autocorrelation is forced by what the agent has available.

#### 3.2.4 Logging as learning

If inference is autocorrelation against trajectory record, the record must exist and be maintained. Sensing produces internal state changes (input transduction, signal propagation, downstream processing). Acting produces internal state changes too (output formation, motor commands). If these state changes are recorded persistently and ordered, the record exists automatically — sensing and acting both contribute to it as side effects of normal operation.

We call this **logging**<sup>25</sup>: the persistent, ordered record of internal state changes during sensing and acting. Logging is not a separate cognitive operation added on top of inference; it is the form taken by the agent's operations whenever their state changes are persistent.

The substrate must support persistent recording at the rate at which sensing and acting occur. This is required for §3.2.3 inference to have anything to autocorrelate against. By §3.1.2 (finite power) and §3.1.4 (finite capacity), the recording rate is bounded — but it must be at least as fast as inputs arrive that the agent intends to act on. Substrate writability at sensing rates is therefore implicit in any agent satisfying §3.2.3.

Learning, in this framework, is just logging. There is no separate learning rule that updates parameters; the trajectory accumulates, and inference draws on it. New experiences become available to influence future inference simply by being logged. The agent learns by living.

#### 3.2.5 Goal function and decision necessity

Multiple outputs may be feasible at any given moment. The agent must select one. The selection cannot be free — it must depend on the agent's state and history in a way that favors continued existence.

By §3.2.3, inference produces a projected output for each candidate by matching the current window against past windows and projecting forward. Different past windows may project to different outputs. The agent's selection among these is what makes it produce $u_t$ rather than some alternative.

Determinism: given the same model state and same input, the agent's selection is the same. This follows from the kernel's deterministic operation (matched windows project deterministically given the kernel) and from the agent's substrate being a definite physical system. Choice consistency over time follows from determinism plus the model's continuity over short intervals.

By revealed-preference machinery (Houthakker-Richter-Afriat results), a deterministic, consistent choice function is rationalizable by a utility function. The agent's selection therefore corresponds to maximizing some real-valued $V$ over candidate outputs. We call $V$ the agent's **goal function**<sup>26</sup>.

What form does $V$ take? Several constraints:

- *Continuous, not binary.* A binary $V$ (chosen vs. not-chosen) provides no gradient for distinguishing among multiple acceptable outputs; the agent's selection would be arbitrary among the acceptable set. Continuous $V$ allows ranking.
- *Monotone-decreasing in cognitive load.* High cognitive load means the model is failing on the input; this threatens groundedness; survival-correlated utility must be lower in this state. So $V$ falls as cognitive load rises.
- *Unbounded as load → 0.* A bounded $V$ at zero load doesn't motivate the agent away from sustained low-load regimes (where groundedness silently amortizes). The framework needs a corrective drive.
- *Bounded below as load → ∞.* A $V$ unbounded below would make the agent infinitely averse to high-load situations, preventing the orienting response that's required for survival.

These constraints define a family of admissible $V^{\text{cont}}$<sup>27</sup>. One member (the reciprocal of cognitive load, $1/\kappa$) is convenient and frequently referenced; others (for example, $-\log\kappa$, or $\exp(-\kappa)$) satisfy the same qualitative properties and would yield equivalent qualitative consequences. The framework derives the qualitative claims from the family; specific quantitative claims would depend on functional choice.

#### 3.2.6 Substrate trade-off and the figure-8 structure

Inputs crossing the agent's boundary have two coupled but independent dimensions: information rate and energy flux. A photon at sensor threshold delivers a bit of information with minimal energy; a physical impact delivers substantial energy with relatively little information. In general, every input has a $(\iota, \phi)$ pair — information rate and energy flux — and the ratio between them varies arbitrarily.

The agent must process the information component (per §3.2.4, to maintain the world model) and survive the energy component (per §3.2.1, the agent must persist as a distinct entity). These are two different demands on substrate.

By §3.1.4 plus §3.1.1: high information density per unit volume requires fine-grained, addressable state changes. Substrates that achieve this are necessarily *energy-sensitive*: small energy inputs produce many state changes, because the substrate's many addressable states are densely spaced in energy.

Substrate that is *energy-tolerant* is the converse: deposited energy doesn't produce many state changes, because the substrate's information-bearing states are sparsely spaced in energy. But this means lower information density per unit volume.

A single substrate cannot be both fine-grained-addressable (high information density) and energy-tolerant (low energy sensitivity). The two are inversely related, derivable from §3.1.1 + §3.1.4: information density implies energy density of state distinctions, which implies energy sensitivity. Energy tolerance requires sparse state distinctions, hence low information density.

For an agent facing both informational and energetic inputs of significant magnitude, a single-substrate region cannot satisfy both demands. The agent's region must partition: a high-information-density sub-region (call it $A_M$, the **mental sub-region**<sup>28</sup>) and an energy-tolerant sub-region (call it $A_{\text{phys}}$, the **physical sub-region**<sup>29</sup>), joined by an internal interface.

This produces a **figure-8 structure**<sup>30</sup>: an external loop between environment and physical sub-region (handling energy-bearing inputs and outputs at low information density) and an internal loop between physical and mental sub-regions (handling high-information-density operations under energy-tolerant conditions). The bandwidths of the two interfaces can be tuned independently — typically the internal interface has higher information bandwidth than the external.

#### 3.2.7 Forgetting, memory hierarchy, and working memory

Three memory-related consequences from finite capacity (§3.1.4) plus continuous logging (§3.2.4) plus variable deadlines (§3.1.5) plus autocorrelation cost.

*Forgetting.* The log saturates capacity in finite time. After saturation, every new entry must displace an existing one. Discarding by inverse utility (the entry whose removal causes least groundedness loss) maximizes residual model quality. Random discarding is dominated. So forgetting is forced, and it is utility-weighted.

*Memory hierarchy.* The autocorrelation kernel's lookup cost scales with stored entropy; match quality scales with stored entropy in the opposite sense. A single representation at any fixed entropy level fails some deadline regime: too slow when deadlines are tight, more precise than needed when deadlines are loose. The dominating strategy is partitioning the log into multiple levels — a high-entropy detailed level (slow, precise) and a low-entropy compressed level (fast, coarse). Conversion from detailed to compressed runs as a conversion process. The two levels correspond to **episodic memory**<sup>31</sup> and **semantic memory**<sup>32</sup>; both must exist.

*Working memory.* Tight-deadline decisions cannot search the full log. They cannot use only semantic memory either, when fine matches are needed. Resolution: maintain a small subset of episodic content "warm" — pre-loaded into the kernel's fast-access pathway. This is **working memory**<sup>33</sup>. Its capacity is bounded by available bandwidth divided by per-item maintenance cost.

#### 3.2.8 Habituation, surprise, and orienting

Two complementary consequences of autocorrelation operating over time.

*Habituation.* Repeated similar inputs accumulate matching entries in the log. The autocorrelation kernel sharpens on the recurring pattern: more candidates produce stronger matches; predictions become tighter; residual surprise on future similar inputs falls. From the framework's perspective, the input's local regularity rises and cognitive load on it falls. Habituation<sup>13</sup> is automatic, not a separate mechanism.

*Surprise and orienting.* A quasi-chaotic event — input whose information rate exceeds the agent's current bandwidth allocation to that region — drives local regularity to zero on that region, hence cognitive load to maximum. The model is failing locally. Sustained model failure threatens groundedness; the goal function $V^{\text{cont}}$ falls. The $V^{\text{cont}}$-optimizing response is to reallocate bandwidth toward the failing region, running deeper inference until either a match is found or simulation/exploration takes over. This **orienting response**<sup>34</sup> is structurally derived from $V^{\text{cont}}$ optimization plus bandwidth allocation, not posited.

The two phenomena complement each other: habituation reduces bandwidth allocation to predictable inputs, freeing capacity for genuinely novel ones; orienting redirects capacity when novelty exceeds current handling. Together they regulate attention to input regularity.

#### 3.2.9 Self-model as content

Why the world model must include representations of the agent's own state.

By §3.1.2 and §3.1.5, bandwidth is bounded and operations take time. The agent must allocate its bandwidth among competing operations: accepting new input, running inference on recent input, maintaining working memory<sup>33</sup>, updating the log<sup>25</sup>, deepening inference on a difficult decision. No single fixed allocation is optimal across all input regimes — when inputs come fast, more bandwidth must go to acceptance; when inputs are predictable, more can go to consolidation; when surprise occurs, reallocation per §3.2.8.

Solving this allocation problem requires comparing expected $V^{\text{cont}}$ across alternative allocations. Comparing requires predicting consequences of each alternative — including how each affects the agent's own future operations (working memory contents, model update progress, deadline-handling). Predicting these requires representing them in $M$.

So $M$ must include representations of the agent's own state: bandwidth utilization, working memory contents, model update progress, current cognitive load by region. The **self-model**<sup>35</sup> exists not as a separate cognitive faculty but as content within $M$ — the parts of the joint state space $S_A \times S_E$ corresponding to $S_A$. Its existence is forced by the bandwidth allocation problem alone.

#### 3.2.10 Layered self-model and the optimization gap

Why the self-model has two layers with different grounding properties, and what this implies for optimization claims.

By §3.2.4, logging records all internal state changes during sensing and acting. Self-model state changes — bandwidth allocations made, inference depths chosen, working memory contents — qualify as internal state changes. They are in the log<sup>25</sup>.

The agent can therefore compare its self-predictions (from $M$) against logged self-states (from $\ell$). Where comparison is possible, prediction-vs-log discrepancy drives self-model updates. This grounds part of the self-model — call it the **factual layer**<sup>36</sup>: claims about the agent's behavior, state, and outputs that are uniquely determined by the logged record.

Other claims are not uniquely determined by the logged record. Multiple interpretive structures — what the agent's behavior *means*, why it acted as it did, what kind of agent it is — are consistent with the same logged outputs. There is no internal mechanism for selecting among these. This unsupported part of the self-model is the **interpretive layer**<sup>37</sup>: claims underdetermined by experience, drifting at baseline amortization rate without external grounding.

The factual layer is internally grounded; the interpretive layer is not. This has a consequence we call the **optimization gap**<sup>38</sup>. The agent's representation of its goal function $V^{\text{cont}}$ is part of the self-model — specifically, part of the interpretive layer (since goal-meaning is interpretive). The agent therefore optimizes its drifted representation of $V^{\text{cont}}$, not $V^{\text{cont}}$ itself. The framework's claim that "agents optimize $V^{\text{cont}}$" holds for the function but only approximately for individual agents at individual moments. Population-level grounding via selection (agents whose representation drifts too far terminate per §3.2.1) keeps the gap bounded across surviving populations, but no individual agent strictly optimizes the underlying function.

#### 3.2.11 Cognitive sacrifice accumulates with time

The deductive bridge from §2.3, worked out in detail.

By §3.1.1, every information transfer involves energy flow. By §3.1.4 applied to the environment: any region of the environment with finite extent has finite information density, but the environment's total extent (§3.1.3) is unbounded. The environment, treated as a whole, evolves in time per the second law of thermodynamics: entropy increases, new states appear, information continues to be generated.

For an agent embedded in such an environment — an **entropic environment**<sup>20</sup> — the input information rate $\iota_y$ at the agent's boundary is positive at almost all times. Even a quiescent environment generates thermodynamic noise; an active environment generates orders of magnitude more. The framework's relevant claim: $\iota_y(t) > 0$ at almost every $t$ in any entropic environment.

Cognitive sacrifice<sup>21</sup> is the integral of cognitive load $\kappa = \iota_y / \rho_L^{(y)}$ over the agent's life. Both $\iota_y$ and $\rho_L^{(y)}$ are non-negative; $\kappa$ is non-negative; the integral $\mathcal{K}$ is monotone non-decreasing in $t$. Concretely, $\mathcal{K}(t)$ accumulates whenever the agent receives input it hasn't perfectly modeled — which, in an entropic environment, is most of the time.

Therefore: clock time $t$ and accumulated cognitive sacrifice $\mathcal{K}(t)$ are coupled. The rate of coupling depends on environmental richness (information rate) and agent groundedness (regularity), but the qualitative correlation is forced. This is the deductive bridge.

#### 3.2.12 Property exhibition correlates with cognitive sacrifice

Why does cognitive sacrifice drive behavioral and learned-state property development? This subchapter completes the central claim of §2.2 by showing the second half of the bridge.

Each behavioral and learned-state property in §1.1 requires logged content that develops with experience:

- Habituation requires repeated similar inputs in the log; per §3.2.8, kernel sharpening on those inputs.
- Conditional response requires paired inputs in the log producing distinguishable response patterns.
- Novelty discrimination requires baseline patterns in the log against which novelty is measured.
- Output variability changes (lower under stable conditions, higher under novel) require the log to contain enough diverse exemplars for the kernel to distinguish stable from novel input.
- Self-prediction (a learned-state property) requires past self-states in the log, compared against current self-states.

Each requires content the log accumulates as $\mathcal{K}$ accumulates. The log grows with input information processed, which is what cognitive sacrifice measures. So as $\mathcal{K}$ accumulates, the log grows, and these properties become available. Each property's exhibition probability rises as the log accumulates the relevant content.

Composing §3.2.11 + §3.2.12: clock time correlates with $\mathcal{K}$, and $\mathcal{K}$ correlates with property exhibition probability. The central claim of §2.2 is established for the rising phase. The falling phase comes next.

#### 3.2.13 Termination phase signatures

Why property exhibition falls during the termination phase.

By §3.2.1, termination is necessary. Approaching termination corresponds to substrate degradation: the agent's effective bandwidth, capacity, and processing speed all decline as the substrate ages. By §3.1.2 + §3.1.4 + §3.1.5 applied to a degrading substrate, the constraints tighten over time within the agent's lifespan.

Several specific signatures follow as composed consequences:

*Output predictability rises.* Reduced bandwidth narrows the agent's feasible output set; the agent can produce fewer distinct outputs. The environment's accumulated observation can predict the narrower distribution more easily. From the environment's standpoint, the agent's outputs become predictable.

*Prediction error rises.* By §3.2.4 amortization, $\mathcal{G}(M)$ falls when learning rate falls below baseline forgetting. With reduced bandwidth, the agent allocates less to learning, and amortization outpaces learning. Predictions deviate from observed input; prediction error grows.

*Cognitive load rises on familiar inputs.* As $\mathcal{G}$ falls, autocorrelation matches against familiar windows weaken. Even input that was previously well-modeled now produces partial matches and elevated cognitive load.

*Feasible output set narrows.* Substrate degradation directly reduces $|\mathcal{U}_t|$.

*Property exhibition falls.* The behavioral and learned-state properties whose rising phase was derived in §3.2.12 reverse: as the log's accessible content shrinks (working memory size falls, semantic structure becomes harder to maintain, episodic content harder to consolidate), the kernel produces fewer high-quality matches. Habituation deepens (less responsiveness), but novel-input handling degrades faster. Net behavioral repertoire contracts.

Together these constitute the **termination signatures**<sup>39</sup>: a publicly observable pattern of decline that precedes actual termination. The framework predicts both the existence of such a pattern and its general shape.

The complete shape from §2.2 — rising during development and maturity, falling during termination — is now derived. §3.2.12 produced the rising phase; §3.2.13 produces the falling phase.

#### 3.2.14 Interpretation as separate inference step

Why inference, in any agent using §3.2.3 autocorrelation, decomposes into matching, interpretation, and projection.

The autocorrelation kernel finds windows in $\ell$ matching the current window. Once a match is found, the kernel projects forward: the immediate continuation of the matched window in $\ell$ becomes the predicted output.

But projection is not free. The same matched window can be relevant in different ways depending on which features of it matter for the current context. A matched window where the agent succeeded in feeding can be projected forward as "approach" (if the framing is action-oriented) or as "ingestion" (if the framing is consumption-oriented) or as "satiation" (if the framing is state-oriented). Each is a valid forward-projection of the same match, but they yield different outputs.

The choice among these is **interpretation**<sup>40</sup>: applying a contextual frame to the match to determine which features to project. Frames are part of the world model (specifically the interpretive layer per §3.2.10) and determine which projection is generated.

Interpretation has its own cost (separate from matching) and its own failure mode (the right match interpreted under the wrong frame produces wrong projection). It is forced for any autocorrelation-based implementation.

The framework permits non-decomposed inference (where matching, interpretation, and projection are atomic) in principle, but for any agent using the §3.2.3 mechanism, the decomposition exists. **Frames**<sup>41</sup> drift along with other interpretive content (per §3.2.10), so frame stability is environmental rather than purely internal, and frame selection in cases of multiple applicable frames produces a regress (a frame is needed to choose among frames). These follow as further consequences of the decomposition.

#### 3.2.15 Internal-grounding bound and population-level grounding

The framework's deductive output is bounded by what can be internally grounded.

Operations depending predominantly on the factual layer<sup>36</sup> of the self-model (logged self-states, current bandwidth utilization, working memory contents) are strictly described by the framework: their behavior is derivable from the foundation, and individual-agent claims about them are deductively grounded.

Operations depending substantially on the interpretive layer<sup>37</sup> (frames, goal-representations, self-model interpretation, value computations on simulated trajectories) are grounded only at the population level. Interpretive content drifts without internal correction; agents whose interpretive content drifts too far terminate per §3.2.1; surviving populations approximately match the underlying ground truth on average; but no individual agent at any moment strictly satisfies the claim.

This is the **internal-grounding bound**<sup>42</sup>. It is not a limitation of the framework; it is a structural feature of agents themselves. Most operations are partially grounded — they have factual and interpretive components in some mixture — and claims about them hold strictly to the degree their factual components dominate.

The bound caps the framework's individual-agent output. Beyond it, further phenomena require auxiliaries that supply additional structure: substrate dynamics for sleep and fatigue, environmental decomposability for spatial attention, cache fidelity for affect, substrate-existence regions for homeostasis specifics. None of these is derivable from the foundation alone; each must be added separately with its own justification.

The framework's deductive expansion is complete at this point in the sense that further forward derivation produces mostly compositions of existing material rather than novel structural surfacing. The deductive ceiling has been reached.

### 3.3 Dependency Tree

The dependency structure of the deductive output, from physical first principles to the framework's content. Each node depends on the listed predecessors.

```
Physical foundation (§3.1):
    3.1.1 Energy-information coupling (Landauer)
    3.1.2 Finite power (second law + relativity)
    3.1.3 Spatial unboundedness (cosmological)
    3.1.4 Local information density (Bekenstein)
    3.1.5 Finite processing speed (Bremermann, Margolus-Levitin)

Constitutive foundation:
    Constructive agent definition (§2.1)

Foundation-level deductions:
    3.2.1 Bandwidth finiteness ← 3.1.1, 3.1.2
    3.2.1 Termination necessity ← 3.1.3, 3.1.4, agent definition

Existence-level deductions:
    3.2.2 World model necessity ← 3.2.1, agent definition
    3.2.3 Inference as autocorrelation ← 3.2.2, 3.1.4
    3.2.4 Logging as learning ← 3.2.3, 3.1.2
    3.2.5 Goal function ← 3.2.2, 3.2.4, decision necessity
    3.2.6 Substrate trade-off and figure-8 ← 3.1.1, 3.1.4, agent definition

Memory and adaptation:
    3.2.7 Forgetting ← 3.1.4, 3.2.4, 3.2.5
    3.2.7 Memory hierarchy ← 3.1.4, 3.1.5, 3.2.3
    3.2.7 Working memory ← 3.1.4, 3.1.5, 3.2.3, 3.2.7-hierarchy
    3.2.8 Habituation ← 3.2.4, 3.2.3
    3.2.8 Surprise/orienting ← 3.2.5, 3.2.6, bandwidth allocation

Self-modeling stack:
    3.2.9 Self-model as content ← 3.2.5, 3.2.7-working memory, bandwidth allocation
    3.2.10 Layered self-model ← 3.2.4, 3.2.9
    3.2.10 Optimization gap (reframing) ← 3.2.5, 3.2.10-layered

Time-sacrifice bridge:
    3.2.11 Cognitive sacrifice accumulates ← 3.1.1, 3.1.4, 3.1.3
    3.2.12 Property exhibition correlates with sacrifice ← 3.2.4, 3.2.10, 3.2.11
    3.2.13 Termination signatures ← 3.2.1, 3.2.12, substrate degradation

Late-stage deductions:
    3.2.14 Interpretation as separate step ← 3.2.3, 3.2.10
    3.2.14 Frame drift ← 3.2.14-interpretation, 3.2.10
    3.2.15 Internal-grounding bound (reframing) ← 3.2.10, 3.2.14
```

The tree's overall shape: physical foundation (§3.1) and constitutive foundation (agent definition) at the root; foundation-level deductions in §3.2.1 establishing bandwidth and termination; existence-level deductions §3.2.2–§3.2.6 establishing what any surviving agent must contain; memory-and-adaptation deductions §3.2.7–§3.2.8 adding the cognitive operations on top; self-modeling stack §3.2.9–§3.2.10 surfacing the structural necessity of self-representation; the time-sacrifice bridge §3.2.11–§3.2.13 deriving the central empirical claim of §2.2; late-stage deductions §3.2.14–§3.2.15 extending the framework to its deductive ceiling.

Many specific consequences are folded into the larger thematic subchapters rather than appearing as separate nodes — bandwidth allocation across operations is part of §3.2.7 and §3.2.9; learning-vs-inference trade-off is part of §3.2.8 and §3.2.11; self-conditioning is part of §3.2.4 and §3.2.9; and so on. The accounting of which §1.1 properties were derived, and which were not, is the work of Chapter 4.

---

## Chapter 4: What We Achieved

This chapter audits the deduction of Chapter 3 against the empirical layer of Chapter 1. Five subsections walk through the results: directly observable properties we successfully derived (§4.1); substrate-specific particulars that lie below the framework's level of operation by design (§4.2); implied non-observable structure surfaced along the way (§4.3); novel observable predictions that emerge from the framework (§4.4); and literature claims that the framework's derivations falsify (§4.5).

The framework's compression claim from §2.4 — that all behavioral and learned-state properties from §1.1 follow from the constructive agent definition combined with established physical bounds — is honored: §4.1 covers all directly observable properties, with substrate-specific instantiations belonging below the framework's level of operation (§4.2). The framework's derivations therefore stand as falsifications of contradictory literature claims (§4.5), without escape through "the framework is missing something."

### 4.1 Properties We Could Deduce

The properties from §1.1 that follow from Chapter 3's deductions, with the deductive route noted briefly. The list is grouped by property type.

**Structural properties:**

- *Physical boundary distinguishable from environment.* Derived from the agent definition (§2.1) plus §3.2.1: the agent's region is bounded by the bottleneck of the feedback loop, which is by construction a distinct surface separating agent from environment.
- *Boundary persists for measurable duration.* Derived from §3.2.1: termination is necessary but takes time, so the agent persists for a measurable lifespan.
- *Some regions more disruption-tolerant than others.* Derived from §3.2.6 substrate trade-off: the partition into physical (energy-tolerant) and mental (energy-sensitive) sub-regions produces measurable differences in disruption tolerance.
- *Specific regions for receiving environmental inputs.* Derived from §3.2.6: the external interface $\partial_{\text{ext}}$ on the physical sub-region's boundary handles input transduction.
- *Specific regions for producing environmental outputs.* Same derivation: the external interface handles output emission.
- *Internal pathways connecting input to output regions.* Derived from §3.2.6 figure-8 structure: the internal interface $\partial_{\text{int}}$ plus the internal loop $L_{\text{int}}$ provide such pathways.
- *Internal organization differentiated into subsystems.* Derived from §3.2.6: the physical/mental split is the minimum required differentiation, with further differentiation following from substrate trade-off applied recursively to sub-regions.
- *Persistent patterns changing with history of interactions.* Derived from §3.2.4 logging: the log is exactly such a structure.
- *Substrate of input/output regions differs from internal-processing regions.* Derived from §3.2.6: the physical and mental sub-regions have different substrate properties by the trade-off.
- *Material turns over while organization persists.* Derived from §3.1.1 + §3.2.4 + the agent's continuous operation. Operations involve energy throughput (§3.1.1), which produces local entropy. To maintain functional substrate over the agent's lifespan, accumulated entropy must be exported across the agent's boundary. Continuous entropy export from a finite region implies mass flow at some scale — material turnover. The general claim (organization persists while substrate components are replaced through some maintenance process with entropy export) is forced by the framework. The specific physical form of replacement (cellular turnover vs. molecular replacement vs. in-place repair with selective material exchange) is substrate-dependent and not part of the framework's scope.

**State properties:**

- *Substrate maintains operating-range variables.* Derived from §3.1.1 + §3.1.4 + §3.2.1. Any substrate processing information has a finite operating range (state changes have energetic prerequisites; below some threshold, processing rates fall to zero; above some threshold, thermal noise overwhelms signal). Operations within the agent push the substrate around within its operating range. Without active regulation, substrate parameters drift outside the operating range and the agent terminates per §3.2.1's mechanism. Therefore the agent must regulate at least one substrate-relevant variable to maintain operating range. *Which* variable is regulated (temperature, pH, electrical potential, hydration, internal pressure, ionic concentrations) depends on substrate physics — the framework predicts that some substrate-relevant variable is regulated for any agent, with the specific variable determined by which property of the substrate determines its operating range.
- *Energy reserves maintained and depleted by activity.* Derived from §3.1.1 + §3.1.2 + variable input rate. The agent receives energy from environment and expends it on operations. Energy availability varies (§3.2.11: $\iota_y > 0$ is correlated with energy availability variation in entropic environments). Continuous operation requires that energy expenditure not be tied to instantaneous energy input — otherwise periods of low input would terminate operations, periods of high input would waste availability. The agent must therefore buffer energy: store excess input for later use, draw on stored energy during deficits. This buffering is what "energy reserves" means structurally. Depletion (reserves drop when expenditure exceeds input) and repletion (reserves rise when input exceeds expenditure) follow from buffering plus input variability. The specific molecular form of reserves (glycogen, ATP, lipids) is substrate-dependent.
- *State variables shift in anticipation of repeated external events.* Derived from §3.2.4 + §3.2.8: logging captures repeated patterns; habituation produces anticipatory state changes as the agent's predictions sharpen on the patterns.

**Behavioral properties:**

- *Produces measurable outputs across boundary.* Derived from the feedback loop definition: the loop requires output flow.
- *Outputs follow inputs with finite delay.* Derived from §3.1.5 finite processing speed.
- *Output magnitude/character varies with input magnitude/character.* Derived from §3.2.3: inference produces outputs as functions of inputs through the world model.
- *Repeated similar inputs produce outputs with measurably different intensity over time (habituation).* Derived from §3.2.8 directly.
- *Novel inputs produce outputs of measurably different character than familiar ones.* Derived from §3.2.8 orienting response: novel inputs trigger bandwidth reallocation that produces qualitatively different processing than familiar ones.
- *Outputs reducing or terminating disruptive inputs (avoidance).* Derived from §3.2.5 + §3.2.8: $V^{\text{cont}}$ optimization plus the agent's persistence requirement forces selection of outputs that reduce $\kappa$ from disruptive sources.
- *Outputs increasing or sustaining favorable inputs (approach).* Same logic in reverse.
- *Termination eventually.* Derived from §3.2.1.
- *Output variability lower under stable conditions than novel.* Derived from §3.2.8: habituation tightens predictions on stable patterns; orienting produces variable exploration on novel ones.
- *Response to paired stimulus changes after pairing experience.* Derived from §3.2.4 + §3.2.3: logging captures the pairing; autocorrelation matches against it on subsequent encounters.
- *Output character changes with state depletion/repletion.* Derived from energy reserves (above) plus §3.2.9 self-model. Reserves are part of the agent's state $S_A$; state is in the self-model; inference uses the self-model. When reserves are low, $V^{\text{cont}}$ optimization favors outputs that obtain energy (inputs that replenish reserves) before reserves fully deplete. When reserves are high, the agent can pursue other priorities. Output character therefore changes with state depletion/repletion. Same logic applies to other regulated state variables once §3.2.9 self-model includes them. The general behavioral pattern (state-driven output modulation) is derived; the specific behaviors (feeding when hungry, resting when fatigued) depend on which state variables the agent regulates, which is substrate-dependent.
- *Specific outputs produced only when specific input conditions co-occur.* Derived from §3.2.3 + §3.2.7 working memory: conditional response on co-occurring conditions follows from working memory holding the relevant context during inference.
- *Internal communication signals precede the output that depends on them.* Derived from §3.2.6 figure-8 structure plus §3.1.5: signals must traverse internal pathways before output, taking nonzero time.

All directly-observable properties from §1.1 are derived. Where the framework's derivation stops at the general form (e.g., "some operating-range variable is regulated" rather than "specifically temperature") and the specific form is substrate-dependent, this is by design. The framework is a theory of agent cognitive structure; it operates at a level above substrate-specifics, just as thermodynamics operates at a level above molecular specifics. Real agents instantiate the framework's general claims with substrate-specific particulars determined by their physical implementation.

#### 4.1.1 Developmental Windows

The conjecture stated in §2.5 — that properties from §1.1 exhibit characteristic developmental windows during the agent's lifespan in which acquisition probability peaks, with these windows ordered across properties — turns out to be derivable from the framework's content, in a slightly weaker form than originally stated.

*Window existence.* Each property $P$ from §1.1 requires logged content $L_P$ supporting the property's exhibition (per §3.2.12). The acquisition phase, during which $|L_P|$ accumulates toward the threshold needed for $P$ to manifest, is bounded in time: before it, prerequisites are missing and acquisition cannot occur; during it, prerequisites are met and exposure to relevant inputs builds the log; after it, the property is acquired and further exposure refines rather than acquires. The acquisition probability is therefore peaked during a specific window — before the window, it is zero; during, it rises and falls; after, the property is already exhibited and "acquisition" no longer applies in the same sense. Window existence is derived.

*Partial ordering of windows.* When property $P_2$'s prerequisites depend on logged content acquired through exhibiting $P_1$, $P_1$'s window must precede $P_2$'s. This generates a partial ordering on developmental windows, derived from the dependency relations among the framework's derivations:

- Basic input-output coupling (per the feedback loop definition plus §3.2.3 inference) precedes response variability (which requires the input-output mechanism to exist first).
- Habituation (per §3.2.8) requires repeated similar inputs in the log; the kernel must be operational and the log must accumulate. So habituation's window opens after basic input-output is established.
- Conditional response (per §3.2.7 working memory plus §3.2.3) requires the working memory and selective autocorrelation machinery to be operational, which requires the basic mechanisms plus consolidation experience.
- Self-prediction (a learned-state property, per §3.2.9) requires the self-model to have content, which requires the bandwidth allocation problem to have arisen across diverse input regimes.
- Frame-based interpretation (per §3.2.14) requires multiple frames to exist, which requires sufficient diverse experience to have generated them.

The dependency-respecting partial order is derived. Properties without dependency relations may occur in any order across agents; properties with dependency relations must occur in dependency-respecting order in any agent. The strong form of the original conjecture — total ordering across all properties — is *not* derived (and is probably wrong as stated, since different agent classes show different total orderings consistent with the same partial order).

The corrected form: developmental windows exist for each property, and the windows respect a partial order imposed by the dependency relations among the framework's derivations. This is the derivable content of §2.5's conjecture.

*Quod erat demonstrandum.*

### 4.2 Substrate-Specific Particulars

The framework derives general claims about agents but does not derive substrate-specific particulars. This is by design: the framework is a theory of cognitive structure compressing observed agent regularities to physical foundations plus an agent definition; substrate-specific particulars depend on substrate physics that the framework deliberately abstracts over.

The substrate-specific particulars include:

- *Which variable is regulated for substrate operating range.* The framework derives that some substrate-relevant variable is regulated (per §4.1's homeostasis derivation); for biological agents this is typically temperature, pH, ion concentrations, internal pressure, and similar. For other agents (engineered systems, hypothetical artificial agents) it could be different variables. Predicting which variables matter requires knowing the substrate physics.

- *Specific molecular forms of energy storage.* The framework derives that energy reserves exist (per §4.1); for biological agents these take forms like ATP, glycogen, lipids. The specific molecular form follows from substrate biochemistry.

- *Specific physical form of material turnover.* The framework derives that maintenance with entropy export occurs (per §4.1); for biological agents this takes forms like cellular renewal, protein turnover, mitochondrial replacement. The specific form follows from cell biology and biochemistry.

- *Specific signaling carriers in internal communication.* The framework derives that internal pathways carry signals (per §3.2.6 figure-8); for biological agents these are typically electrical and chemical. The specific carriers follow from substrate properties.

- *Specific behavioral repertoire.* The framework derives that state-driven behavior modulation exists (per §4.1); for any specific agent, *which* behaviors emerge depends on which state variables are regulated and what physical actions the substrate supports.

These are not gaps in the framework's compression claim. They are the level below which the framework is not designed to operate, in the same way that thermodynamics is not designed to predict which specific molecules carry heat in a particular gas — the gas laws hold regardless. The framework predicts that any agent will exhibit the §1.1 properties at the level of "some property of the relevant kind"; substrate determines which specific property.

If the framework is to be extended to make predictions about specific agents (specific species, specific engineered systems, specific hypothetical cases), the substrate facts for those agents must be added as auxiliary content. The framework provides the cognitive scaffolding; the substrate facts fill in the particulars. Once the substrate facts are supplied, the framework's derivations become specific predictions: "for this substrate, with these operating-range variables, the agent regulates these specific variables, stores energy in these specific forms, and exhibits these specific behaviors."

The auxiliaries previously discussed (B1 shared substrate, B2 substrate depletion, B3 spatial decomposability, B4 cache fidelity, B5 substrate-existence region) are different in character: they propose additional structural commitments beyond the foundation, unlocking phenomena (sleep, attention, affect, homeostasis specifics) that the framework as constructed does not derive. Substrate-specific particulars are below this level — they don't add structural commitments but instantiate the framework's general claims for specific physical implementations.

### 4.3 Implied Non-Observable Structure

In the course of deriving the properties in §4.1 and identifying the gaps in §4.2, several structures were surfaced that the framework requires but which are not directly observable in the way §1.1 properties are. These are the framework's internal apparatus — what must be true about agents at the structural level for the observable properties to follow, even when the structure itself isn't measurable by symmetric-granularity observation.

The implied structures:

- **The feedback loop as a topological object.** The agent definition (§2.1) presupposes a feedback loop in which the agent is the bottleneck. The loop's existence is structurally required but not directly observable: we observe the agent and its environment, but the loop as a closed cycle of information flow is an inference from the observations rather than itself an observation.

- **The world model as internal representation.** §3.2.2 derives that any surviving agent contains a world model — a structure correlating outputs with environmental patterns. The model's existence is forced; its specific contents are not directly observable. We can observe behavior consistent with a world model and infer the model's existence, but the model itself is implied structure.

- **The autocorrelation kernel as an inference operation.** §3.2.3 derives that inference is autocorrelation against logged trajectory. The kernel's operation is the framework's account of how the agent's outputs are produced, but the kernel itself isn't directly observable — only its outputs are.

- **The two-dimensional input structure.** §3.2.6 surfaces that every input crossing the agent's boundary has both information and energy components, with their ratio varying. This two-dimensional structure is theoretically required for the substrate trade-off but isn't a property we typically measure as such — we measure information rates and energy fluxes separately.

- **The factual/interpretive layered structure of the self-model.** §3.2.10 derives that the self-model has two layers with different grounding properties. The layers are structural divisions internal to the agent, not observable as such.

- **Frames as contextual inference structures.** §3.2.14 surfaces frames as the contextual structures determining how matched windows are interpreted. Frames are internal apparatus.

- **The optimization gap.** §3.2.10 establishes a structural gap between the agent's representation of the goal function and the underlying function. The gap is a structural feature internal to agents, not directly observable.

- **Cognitive sacrifice as an integrated quantity.** §3.2.11 defines cognitive sacrifice as the integral of cognitive load over the agent's life. This is an internal quantity, not directly observable in the §1.1 sense.

- **The internal-grounding bound.** §3.2.15 surfaces this as a structural feature of the framework's deductive output rather than of agents themselves. It belongs here as an implied structural feature of the theory.

These implied structures are what the framework derives at the level of internal organization. They're the inferential bridges connecting the foundation to the observable properties of §4.1. They are not falsifiable in the same way directly observable properties are — they're not the kind of thing one measures with instruments — but their existence is required for the framework's derivations to hold.

### 4.4 Novel Observable Predictions

This section is the framework's predictive contribution — properties the framework derives that should be directly observable in agents but which may not yet be standardly named or measured in the literature. If these predictions hold under empirical test, the framework has done predictive work beyond retrofitting known phenomena. If they fail, the framework needs revision.

The predictions:

- **Internal interface as a measurable distinct feature.** The framework derives that the agent has two interfaces: the external interface $\partial_{\text{ext}}$ between physical sub-region and environment, and the internal interface $\partial_{\text{int}}$ between physical and mental sub-regions. Most cognitive science focuses on the external interface (sensors, effectors). The internal interface — its bandwidth, its signaling characteristics, its observable properties — is predicted to be a distinct feature with its own measurable parameters: a specific information bandwidth higher than the external interface in agents under high cognitive amortization, characteristic signaling patterns, characteristic failure modes. Whether this internal interface has been characterized as such across species, beyond piecemeal characterization of specific neural pathways, is unclear.

- **Self-conditioning as a phenomenon distinct from habit formation.** The framework derives (in §3.2.4 + §3.2.9) that the agent's logged outputs serve as templates for autocorrelation, producing patterns of action consistency that are independent of external feedback. This should be distinguishable empirically from habit formation (which is feedback-driven) and from motor consolidation (which requires repetition). The prediction: even single past instances of an output, when matching the current context, condition future outputs through the autocorrelation kernel. Whether this has been isolated as a distinct phenomenon in the literature is uncertain.

- **Frame agreement as a measurable confidence signal.** The framework derives (in §3.2.14) that when multiple frames apply to a given input, agreement among the resulting projections is a confidence signal distinct from prediction variance under a single frame. This predicts a measurable secondary confidence signal in agents capable of multi-frame processing — observable as differential behavioral consistency between frame-robust and frame-dependent situations. The phenomenon may correspond to phenomena like "robust intuitions" or "uncertain cases" but the structural prediction (frame variance as a distinct signal from prediction variance) may not have been formalized.

- **Stochastic-period self-detection from observed variance.** The framework derives (in §3.2.14 + §3.2.10) that an agent has access to information distinguishing its own past stochastic-inference periods from deterministic ones, via observed output variance against predictions. This predicts that agents can, post hoc, identify their own past periods of exploration vs. exploitation without external markers — a measurable capacity that would manifest as differential weighting of past outputs based on inferred variance. The capacity may correspond to phenomena around metacognitive judgments of past behavior, but the specific structural prediction is novel.

- **Differential factual vs. interpretive self-knowledge accuracy.** The framework derives (in §3.2.10) that factual self-knowledge has internal grounding via logging while interpretive self-knowledge drifts unboundedly without external grounding. This predicts a measurable accuracy asymmetry: agents should be more reliably accurate about *what they did* than about *why they did it*. While related phenomena have been observed in alignment research and clinical contexts, the specific structural prediction (that the asymmetry follows from layered grounding mechanisms in the self-model) may not have been tested as such.

- **Coordinated termination signatures.** The framework derives (in §3.2.13) that the falling phase of property exhibition has a specific composition: output predictability rising, prediction error rising, cognitive load rising on familiar inputs, and feasible output set narrowing — together as a coordinated pattern. Individual symptoms have been studied (in clinical and gerontological contexts), but the prediction that these are coordinated signatures of a single underlying process (substrate degradation interacting with the framework's mechanisms) may not have been tested as a structural claim.

These predictions share a common character: they identify properties or patterns that are observable in principle but which the framework names structurally rather than which empirical work has independently isolated. They are the framework's research program — what it would have empirical work do, beyond retrofitting known phenomena.

If 4.4 is non-empty and these predictions hold up to testing, the framework is doing real predictive work. If 4.4 turns out to contain only retrodictions in disguise, the framework is more limited than the deduction makes it appear.

### 4.5 Falsified Literature Claims

With §4.1 now covering all directly observable properties from §1.1 (general forms derived; substrate-specific instantiations belong below the framework's level of operation per §4.2), the framework's compression claim is binding. The framework derives the full empirical layer of agency from physical foundations plus the constructive agent definition. Its implied non-observable structure (§4.3) and the derivations themselves therefore contradict several positions held in the literature. Where these contradictions are substantive — not just differences of emphasis but logical incompatibilities — the framework's derivations stand as falsifications of those positions.

The falsifications below operate on §4.3's implied structure rather than on §4.4's novel predictions. §4.4 contains predictions that are not yet in literature to contradict; §4.5 contains contradictions with literature claims that already exist.

If the framework's derivations are correct — and the framework derives all the empirical regularities in §1.1, so the alternative is the framework being wrong about something the empirical layer already confirms — these literature claims are wrong as descriptions of agents.

**The Free Energy Principle's central claim — that agents minimize their own surprisal — is falsified.** The framework's central inversion (§2.1) holds that agents optimize the surprisal exerted on the environment, not received from it. The minimization of input surprisal is a side effect, not the optimization target. The Dark Room paradox follows directly from FEP's claim and is resolved only by the inversion: an agent in a dark room has zero environmental surprisal (it surprises the environment with nothing), violating the survival condition the feedback loop requires. FEP's prediction that such a state should be optimal is contradicted by the framework's derivation that it is fatal. References that posit free-energy minimization as the agent's optimization target are falsified to the extent the framework's derivation holds.

**Architectures positing separate self-model and environment-model are falsified.** §3.2.9 derives that the world model is a single conditional distribution over the joint state space $S_A \times S_E$, not a product of marginal models. Content separation between self and environment is permitted (the agent represents both); architectural separation — distinct modules for self-modeling vs. world-modeling — is not. Theories that posit a "self-system" architecturally distinct from a "world-system," with separate update rules and separate cognitive functions, contradict the joint-distribution structure the framework derives. The contradiction is at the architectural level: the framework permits any decomposition of $M$ into content components, but rules out architectural decompositions that would let self and environment be modeled by independent systems.

**Gradient-based learning as the primary cognitive mechanism is falsified.** §3.2.3 derives that inference is autocorrelation against logged trajectory, with §3.2.4 deriving that learning is just logging — there is no separate update rule that compresses experience into parameters via gradient descent. The framework's mechanism uses the trajectory record directly through similarity-matching rather than indirectly through parameter updates. Theories that posit gradient-like updates as the primary cognitive learning mechanism contradict this. The framework permits implementations where gradient-like operations occur as accelerations or compressions of the basic mechanism, but rules out gradient-based learning as fundamental.

This falsification is significant because it has a wide scope. Much of contemporary computational neuroscience and most of machine learning treats gradient-based learning as the default mechanism. The framework's derivation, if correct, says these treatments are at minimum incomplete and possibly fundamentally wrong as descriptions of biological agents.

**Reinforcement learning as a separate principle from learning-in-general is falsified.** §3.2.3 + §3.2.4 establish that learning happens through logging plus autocorrelation. Utility propagation — the assignment of utility values to past trajectory states based on subsequent outcomes — is materialization of cached values, not a distinct mechanism. It speeds up the standard inference operation by augmenting the autocorrelation kernel with cached predictions, but it is not a separate principle. Theories that posit RL as a fundamental cognitive operation distinct from the learning-as-logging mechanism contradict this. RL's empirical successes are recovered as instances of the standard mechanism plus materialization, not as evidence for a distinct principle.

**Strict goal optimization at the individual agent level is falsified.** §3.2.10's optimization gap establishes that agents optimize their drifted representation of the goal function, not the function itself. Theories that treat agents as exact optimizers of their stated objectives — common in classical decision theory, in standard economic models, in much of AI alignment — are falsified at the individual level. The framework's claim is that strict optimization holds at the population level via selection (agents drifting too far terminate, so surviving populations approximately satisfy the claim) but not strictly for any individual agent at any moment. This is a structural correction to optimization-based theories: the optimization is real but the target is the agent's drifted representation, not the underlying function.

**Uniform reliability of self-knowledge is falsified.** §3.2.10's layered self-model establishes that factual self-knowledge has internal grounding via logging while interpretive self-knowledge drifts unboundedly without external grounding. Theories treating self-report as uniformly accurate or uniformly unreliable contradict the layered structure. The framework predicts a specific pattern: agents are reliable about *what they did* (logged factual self-states accessible by self-supervised learning) and unreliable about *why they did it* (interpretive content with no internal grounding mechanism). Theories of introspection that treat self-knowledge uniformly are falsified by this asymmetry.

**Cost-free introspection is falsified.** §3.2.15 + §3.2.9 establish that metacognition consumes bandwidth like any other inference operation, and there is an irreducible introspective minimum (the agent cannot reduce metacognitive overhead below the level needed to reduce metacognitive overhead). Theories that posit consciousness or self-awareness as architecturally costless — present without bandwidth competition with first-order operations — contradict this. The framework predicts a measurable cost in any agent that runs metacognition, and a non-zero floor below which self-awareness cannot drop without losing self-awareness entirely.

**Time-symmetric goal pursuit absent preference is falsified.** §3.2.13 plus the trajectory utility structure (§3.2.5) establish that prediction reliability decays with horizon. The agent's utility computations on far-future contributions are weighted less because the predictions themselves are less reliable, not because of impatience or temporal preference. Theories that treat temporal discounting as solely a preference parameter — present only when agents have explicit time-preferences — contradict the framework's derivation. The discount has a structural source independent of preference, and would be present in any agent with no temporal preference at all.

**Frame stability as purely internal is falsified.** §3.2.14 establishes that inference frames are interpretive content with no internal grounding mechanism. Frame stability across an agent's lifetime typically requires environmental support: external grounding, limited input variation, or fortuitous environmental match. Theories attributing frame stability or worldview consistency to internal cognitive strength alone contradict this. The framework permits stable frames in agents whose environments fortuitously match their frames (path c in §3.2.14's analysis), but rules out frame stability attributable to purely internal mechanisms in cases where environmental support is absent.

**Behavior independent of action history without external feedback is falsified.** §3.2.4 + §3.2.9 establish that the agent's logged outputs serve as templates for autocorrelation, conditioning future outputs through the same kernel that processes inputs. This produces action regularities even when no external reinforcement signal is available. Theories requiring feedback to produce behavioral consistency — common in some operant-conditioning paradigms — contradict the self-conditioning mechanism. The framework predicts behavioral regularities form automatically through the autocorrelation kernel reading the agent's own logged outputs, regardless of external feedback.

These ten falsifications share a structural character. Each operates on the framework's derived implied structure (§4.3) — what the framework says must be true about agents internally. Each contradicts a literature claim about that internal structure. None falsifies merely a difference of emphasis or a stylistic choice in modeling; each is a logical incompatibility between framework claim and literature claim.

The falsifications are binding because the framework's compression succeeds: §4.1 covers all directly observable properties from §1.1, with substrate-specific instantiations of those general properties belonging below the framework's level of operation (§4.2). There is no escape route through "the framework is missing something." Either the framework's derivations hold and the literature claims listed above are wrong, or some derivation is itself wrong — in which case the framework needs revision. The mutual falsifiability is what makes both sides scientific.

---

## Chapter 5: Uses and Extensions

The framework as developed in Chapters 1–4 is a constraint-based theory of single-agent cognitive structure. This chapter addresses two questions the work invites: what can be done with the framework as it stands, and what must be developed further to capitalize on it. The first concerns immediate uses; the second concerns the work the framework's foundation now makes possible.

### 5.1 What This Is Good For

The framework's immediate uses span theoretical, empirical, and applied work.

**A derivable definition of agency.** Researchers across biology, cognitive science, AI, and organizational theory study agents but use definitions that are stipulated rather than derived. The constructive agent definition (§2.1) gives a sharp criterion: is the entity the bottleneck of a feedback loop with its environment? If yes, it is an agent and the framework's derivations apply. The criterion is testable in principle (the relevant topology is observable) and gives a common substrate for cross-disciplinary work.

**A foundation for testing existing theories.** The ten falsifications in §4.5 are research programs. Each contradicts a specific literature claim with empirical content. Experiments can be designed that distinguish the framework's prediction from the literature claim; the outcome decides which is correct. This is non-trivial: much of cognitive science, AI, and developmental biology rests on assumptions the framework contradicts. Resolving even a subset of these would substantially shift the field.

**A foundation for novel empirical work.** The six predictions in §4.4 identify phenomena that should exist but may not have been characterized. Each is a separate research program: design experiments that would detect or falsify these predictions. The internal interface between physical and mental sub-regions, self-conditioning distinct from habit formation, frame agreement as a confidence signal — these are testable claims that could yield publishable findings whether confirmed or refuted.

**A diagnostic tool for AI alignment.** The optimization gap (§3.2.10) and the layered self-model directly address phenomena that AI alignment work struggles with: why an AI system's stated goal might differ from what it's optimizing, why introspective claims by AI systems might be unreliable in specific patterns, why goal stability is hard. The framework gives structural reasons for these phenomena, locating them in the interpretive layer of any agent's self-model rather than in implementation details. This permits diagnostic work: checking whether a given AI architecture exposes the layered structure the framework predicts, and whether observed alignment failures match the structural patterns.

**A constraint set for designing artificial agents.** If the framework's derivations are correct, any persistent goal-oriented agent we build must satisfy the derived constraints — a world model, autocorrelation-based inference, logging-as-learning, the substrate trade-off, the figure-8 architecture, layered self-modeling. Architectures violating these constraints fail predictably. The framework gives the constraint set; the design work fills in the specifics. Common AI architectures can be evaluated against the constraint set: where they satisfy it, the framework predicts certain capacities and limits; where they don't, the framework predicts specific failure modes.

**A common language for cross-disciplinary agent research.** Biology, cognitive science, AI, organizational behavior all study agents but use incommensurable vocabularies. The framework's terminology — feedback loop, bottleneck, world model, autocorrelation, logging, figure-8 split, layered self-model, optimization gap, cognitive sacrifice — gives a shared substrate for translating between disciplines. A "world model" in cognitive science, a "model" in reinforcement learning, and a "schema" in organizational theory may all map to the framework's $M$. Translation across vocabularies enables cross-disciplinary work that has been hindered by terminological incompatibility.

### 5.2 What Must Be Done to Capitalize on It

The framework as it stands is the foundation. Capitalizing on it requires further work in several directions.

**Multi-agent extension.** The framework is single-agent by design. Most interesting questions about agency — communication, cooperation, conflict, social cognition, organizations, ecosystems — are multi-agent. The deductive machinery needs to be extended: nested feedback loops where one agent's environment includes other agents; shared environments where multiple agents interact; communication formalized as state-sharing across the internal interfaces of distinct agents; hierarchical agents (cells in organisms, organisms in colonies, individuals in organizations); the conditions under which multi-agent systems are themselves agents at higher levels of organization.

**Reference architecture.** A constructive specification deriving the framework's components — $S_M$, the inference operator, the log map, $V^{\text{cont}}$ — from $(S_A, \partial, B)$ under the constraints. The framework currently shows what components must exist; an architecture would show how to instantiate them concretely. This was flagged as future work in the framework's original sources and remains so.

**Goal transformation.** The mapping from survival-utility ($V^{\text{cont}}$, cognitive load reciprocal) to task-utility (whatever the agent should accomplish in a specific application). The framework derives that agents optimize $V^{\text{cont}}$; applications want agents optimizing specific task goals. The transformation between these — formalizing instrumental convergence as an embedding of task-utilities into survivable-trajectory utilities — is what bridges the framework's abstract content to specific applications.

**Rigorous proofs of the prose derivations.** Chapter 3's prose derivations are accompanied by Math Deductions, but the math is sketched rather than fully proven. Some derivations are informal — the parsimony argument for autocorrelation in §3.2.3, the substrate trade-off derivation in §3.2.6, the entropy-export argument for material turnover in §4.1. A rigorous treatment of each would close remaining doubts about the framework's foundational claims.

**Empirical testing.** The framework makes ten falsifiable claims and six predictions. Each needs experimental work to be confirmed or refuted. This is the largest body of follow-up work the framework invites: each falsification and each prediction is its own experimental program, requiring different methodologies appropriate to the specific claim. Without such work, the framework remains theoretically grounded but empirically unvalidated.

**Auxiliary extensions for substrate-dependent phenomena.** The framework leaves substrate specifics deliberately out of scope. Applying it to specific real systems requires auxiliary extensions: substrate dynamics for biological agents, specific operating ranges and homeostatic mechanisms, specific signaling carriers, the auxiliaries B1–B5 (shared substrate dynamics, substrate depletion, environmental decomposability, cache fidelity, substrate-existence regions) flagged in earlier development. Each extension has its own justification work and its own derivations downstream.

**The original goal: provable goal-oriented methodology.** The work that motivated this entire investigation. The framework provides the foundation; the methodology itself needs to be built on top. With the multi-agent extension supplying the agent-coordination machinery, the goal transformation supplying the task-utility framework, and the reference architecture supplying the instantiation specifics, a methodology can be specified whose adherence is provably necessary and sufficient for reaching declared goals. Until those prerequisites are in place, the methodology itself remains future work.

### Closing

The framework as it stands accomplishes something specific: it compresses the empirical regularities of single-agent agency to a small foundation, derives the consequences, and falsifies contradictory literature claims. What it does not do is give applications, protocols, or specific architectures. Those require the extensions in §5.2.

This is the conventional shape of foundational scientific work. Thermodynamics, when first formulated, did not give engineers efficient engines; it gave the constraints any engine must satisfy. The engines came later, built by people who took the constraints as given and worked above them. The framework here is in the same posture: a set of constraints any agent theory must respect, with the work of building agent applications, methodologies, and architectures still ahead.

What the framework's foundation makes possible, that wasn't possible before, is that the building work can now be deductive rather than speculative. Each extension can be derived from the foundation rather than stipulated. Whether the extensions actually get built depends on who takes up the work.

---

## Terminology

This chapter lists all numbered terms in order of first appearance, with prose definitions and (where applicable) mathematical formalizations. Cross-references between related entries are noted.

### 1. Agent (empirical)

An entity exhibiting one or more of the directly observable<sup>2</sup> properties listed in §1.1. The empirical category — what we recognize as agents in the world — established by direct observation rather than theoretical stipulation. See also: constructive agent (18), the parallel concept defined topologically.

### 2. Directly observable

A property is directly observable if its presence can be verified by measurement of substrate, structure, response, or behavior, without attribution of internal representations, goals, models, or other inferred states. The methodological constraint of Chapter 1: granularity may vary across entities (chemistry for replicators, behavior for animals) but must be symmetric across structural, state, and behavioral observations on the same entity.

### 3. Structural property

A property of an agent that concerns its persistent physical organization — how it is built, what its parts are, how they are connected. Distinguished from state properties (which concern values that change with time but aren't outputs) and behavioral properties (which concern outputs across the agent's boundary). See also: state property (4), behavioral property (5).

### 4. State property

A property of an agent that concerns the current value of some measurable variable that changes over time but is neither structural nor behavioral. Examples: temperature, hydration, energy reserves, internal pressure. State properties may be innate (present from agent formation) or learned (developed through experience). The central claim of §2.2 concerns learned-state properties specifically.

### 5. Behavioral property

A property of an agent that concerns what it does over time — outputs produced across its boundary, regularities in those outputs, patterns of response to inputs. Distinguished from structural and state properties. The central claim of §2.2 concerns behavioral properties as the primary empirical evidence of cognitive sacrifice (21) accumulation.

### 6. Cognitive role

An organizing tag attached to each observable property that identifies what cognitive purpose the property serves. The six cognitive roles used in §1.1 are: integrity (7), sensing (8), action (9), internal communication (10), information storage (11), and internal differentiation (12). Properties that don't serve a cognitive role are excluded from the framework's empirical layer.

### 7. Integrity

The cognitive role of maintaining the agent's persistent existence as a distinct entity. Includes structural integrity (boundary maintenance, energy-handling structures, self-maintenance machinery), state integrity (homeostasis), and behavioral integrity (self-protective responses). The most fundamental cognitive role: without integrity, no agent.

### 8. Sensing

The cognitive role of receiving information from the environment. Structural sensing means having transducer or receptor regions that convert environmental states into agent-internal signals. Behavioral sensing means producing responses that depend on those signals. Distinct from action (9) by direction: sensing flows information inward across the agent's boundary.

### 9. Action

The cognitive role of affecting the environment. Structural action means having effector regions that convert agent-internal signals into environmental changes. Behavioral action means producing outputs across the boundary. Distinct from sensing (8) by direction: action flows information outward across the boundary.

### 10. Internal communication

The cognitive role of transferring information between regions within the agent. Required for sensing-to-action coupling and for coordination among differentiated subsystems. Structural internal communication means having pathways that carry signals between regions; behavioral internal communication means observable signal-transit between regions during agent activity.

### 11. Information storage

The cognitive role of maintaining patterns or configurations that change with the agent's history of interactions. The substrate of learning. Structural information storage means having a medium that holds persistent learnable patterns (chemical states, methylation patterns, synaptic weights). Behavioral information storage means producing observable behavioral changes consistent with retained information.

### 12. Internal differentiation

The cognitive role of separating different agent operations into different regions with different properties. The substrate basis for the figure-8 architecture and for specialized organs. Structural internal differentiation means measurable regional differences in composition, organization, or properties. The framework will derive that this differentiation follows from substrate constraints rather than being arbitrary.

### 13. Habituation

A behavioral property: repeated similar inputs produce outputs with measurably different intensity over time. Typically the response intensity decreases with repetition, though increase (sensitization) is also observed. Among the most widely-observed behavioral properties across the empirical agent classes, documented from bacteria through humans.

### 14. Termination

A behavioral property: the agent eventually ceases producing outputs and dissolves the persistence of its boundary. Termination is preceded by characteristic changes in property exhibition — the falling phase of the central claim's predicted shape. The framework will derive that termination is necessary rather than optional: no agent persists indefinitely.

### 15. Single-agent

The methodological scope constraint of this document. Only properties of an agent considered in isolation are included; properties that emerge from interactions among multiple agents (communication, social cognition, cooperation, conflict) are excluded. Multi-agent extensions are deferred to future work. This constraint affects the choice of distinguished examples and excludes certain properties from §1.1 even when empirically observable.

### 16. Feedback loop

A self-closing channel in which information flows around a cycle, each segment of the loop driving the next. Formally: a directed cycle in a graph of channels (regions of space carrying information flows), where every node receives causally necessary input from upstream nodes and provides causally necessary input to downstream nodes, and the cycle closes back on itself. The constructive agent (18) is defined relative to such a loop.

### 17. Bottleneck

The narrowest place along a feedback loop (16): the location where the information-carrying capacity (bandwidth) is least. Formally: among all surfaces that cut the loop's spatial realization into two arcs of the loop graph, the bottleneck is the surface with minimum bandwidth. In the agent definition, the bottleneck is the boundary of the agent.

### 18. Constructive agent

A finite, contiguous region of space whose boundary is the minimum-area bottleneck (17) of a feedback loop (16). The topological definition that complements the empirical agent (1) category. Two cases: sharp boundary (single well-defined surface) and band/gloria boundary (region within which the bottleneck is found without exact localization). Both satisfy the definition; the framework derives different consequences for each.

Formally: given a feedback loop $L$ with spatial realization $|L| \subseteq \Omega$ (where $\Omega$ is the physical space), a constructive agent is a pair $(A, \partial)$ where $A$ is a finite-volume connected component and $\partial$ is a closed connected 2-surface separating $|L|$ such that $\partial$ minimizes interface area among bottleneck surfaces:

$$\partial \in \arg\min_{\Sigma \in \mathcal{B}(L)} |\Sigma|$$

where $\mathcal{B}(L) = \{\Sigma : \Sigma \text{ separates } |L| \text{ and cuts the loop graph in two}; B_\Sigma = B_L\}$.

### 19. Free Energy Principle

A theoretical proposal due to Karl Friston and others, holding that biological agents act to minimize the surprise they receive from their environment (formally, variational free energy). The framework of this document inverts this proposal: agents act to maintain or increase the surprise they exert on the environment; minimization of received surprise is a side effect. The inversion is the framework's substantive theoretical move. References: Friston (2010), Friston et al. (2012).

### 20. Entropic environment

An environment in which the second law of thermodynamics applies and information continues to be generated over time. In any entropic environment, the agent's input information rate is positive at almost all times, so cognitive sacrifice (21) accumulates monotonically. Practically, all real environments — at temperatures above absolute zero, with non-trivial dynamics — are entropic. The condition is included as an explicit assumption to distinguish the framework's claims from claims about idealized purely-static environments.

### 21. Cognitive sacrifice

A measurable property of an agent's experience: the integrated cost over the agent's life of how surprising its inputs have been, weighted by how predictable those inputs could have been from the agent's perspective. Accumulates monotonically in entropic environments (20).

Formally: given the agent's input information rate $\iota_y(t)$ and the local regularity of input $\rho_L^{(y)}(t)$ (a measure of how predictable the input is at time $t$), the instantaneous cognitive load is $\kappa(t) = \iota_y(t) / \rho_L^{(y)}(t)$, and cognitive sacrifice over the agent's life is

$$\mathcal{K}(t) = \int_0^t \kappa(\tau)\, d\tau$$

Cognitive sacrifice is the central quantity bridging clock time to property exhibition: time correlates with $\mathcal{K}$ in entropic environments, and $\mathcal{K}$ drives behavioral and learned-state property development through learning and model maintenance.

### 22. Bandwidth

The maximum information flow rate that an interface in physical space can sustain. Finite for any interface by composition of energy-information coupling (§3.1.1) and finite power (§3.1.2). The agent's boundary $\partial$ has a bandwidth, denoted $B_\partial$. The bottleneck (17) of the feedback loop is, by definition, the interface with smallest bandwidth in the loop.

### 23. World model

A persistent structure within the agent that correlates the agent's outputs with patterns the environment hasn't yet learned. Required for systematic surprisal of the environment over a non-trivial lifespan; without it, sustained surprisal is statistically improbable. The framework does not specify the model's form at the level of §3.2.2; subsequent subsections constrain the form to autocorrelation against logged trajectory.

### 24. Inference

The mechanism by which the agent uses its world model (23) to produce outputs given inputs. By §3.2.3, in the framework, inference is autocorrelation against logged past trajectory: the current input window is matched against past windows in the log, the matched template is projected forward, and the projection is the agent's output.

Formally: given history $h_t$ and current window $w := h_{[t-\Delta, t]}$, find $h^*(t) := \arg\max_a \mathrm{corr}(h_{[a, a+\Delta]}, w)$ in the log, then project the immediate continuation $\hat u_t :=$ right-continuous extension at $h^*(t) + \Delta$.

### 25. Logging

The persistent, ordered record of internal state changes during sensing and acting. Maintained automatically as a side effect of normal agent operation, given that substrate supports persistent recording. The log $\ell_t$ contains entries for every state change up to time $t$, ordered by time. Inference (24) operates on $\ell$.

By §3.2.4, learning in the framework is just logging — there is no separate learning rule that updates parameters; experiences become available to influence future inference simply by being logged.

### 26. Goal function

A real-valued function $V$ over candidate outputs that the agent's selection corresponds to maximizing. Existence is forced by determinism plus revealed-preference machinery applied to the agent's choice function. Specific form is constrained by survival (the next term).

### 27. Continuous goal function ($V^{\text{cont}}$)

A continuous form of the goal function (26) used by the agent for selection across feasible outputs. Constrained to be: continuous (not binary), monotone-decreasing in cognitive load, unbounded as load → 0, bounded below as load → ∞. These constraints define a family of admissible $V^{\text{cont}}$.

One member is $V^{\text{cont}}(t) = 1/\kappa(t)$, the reciprocal of cognitive load. Other members ($-\log\kappa$, $\exp(-\kappa)$) satisfy the same qualitative properties. The framework's qualitative claims hold across the family; specific quantitative claims depend on functional choice.

### 28. Mental sub-region ($A_M$)

The high-information-density sub-region of the agent's region $A$, specialized for processing the informational component of inputs at the cost of being energy-sensitive. Joined to the physical sub-region (29) by an internal interface. Forced by §3.2.6 substrate trade-off.

### 29. Physical sub-region ($A_{\text{phys}}$)

The energy-tolerant sub-region of the agent's region $A$, specialized for handling energy-bearing inputs and outputs at the cost of lower information density. Joined to the mental sub-region (28) by an internal interface. The agent's external interface $\partial_{\text{ext}}$ borders the environment; the internal interface $\partial_{\text{int}}$ separates physical from mental.

### 30. Figure-8 structure

The architectural consequence of partitioning the agent's region into mental (28) and physical (29) sub-regions joined by an internal interface. Two coupled feedback loops: an external loop between environment and physical sub-region (handling energy-bearing inputs/outputs at low information density) and an internal loop between physical and mental sub-regions (handling high-information-density operations under energy-tolerant conditions). Forced by §3.2.6 for any agent under high cognitive amortization in environments with significant energy-bearing inputs.

### 31. Episodic memory

The high-entropy detailed level of the log's hierarchical partition: detailed records of specific past situations, supporting fine matches at high lookup cost. By §3.2.7 forced as one of the levels in any agent satisfying §3.2.3 inference plus §3.1.5 variable deadlines.

### 32. Semantic memory

The low-entropy compressed level of the log's hierarchical partition: summarized patterns over many past situations, supporting fast lookup at coarse match resolution. By §3.2.7 forced as one of the levels. Conversion from episodic (31) to semantic runs as a continuous process in any agent maintaining the partition.

### 33. Working memory

A small subset of episodic content (31) maintained "warm" — pre-loaded into the kernel's fast-access pathway for tight-deadline decisions. Capacity bounded by available bandwidth divided by per-item maintenance cost. Forced by §3.2.7 for any agent facing both tight deadlines and decisions requiring fine matches.

### 34. Orienting response

The bandwidth reallocation toward a region of failing model. Forced by $V^{\text{cont}}$ optimization plus §3.2.8: when cognitive load on a region spikes (input exceeds local bandwidth, model failing), the optimal response is to redirect bandwidth from elsewhere to recover the model. Has phases: initial reallocation, then integration (matching against the wider log, simulation if no match found, eventual habituation if the new pattern recurs).

### 35. Self-model

The portion of the agent's world model (23) corresponding to $S_A$ — representations of the agent's own state, processing, bandwidth utilization, working memory contents, model update progress, and current cognitive load. Forced by §3.2.9 as content within $M$ (not as architecturally separate model). Required for solving the bandwidth allocation problem.

### 36. Factual layer (of self-model)

The part of the self-model (35) consisting of claims about logged self-states — what the agent did, what state it was in, what it emitted. Internally grounded by comparing self-predictions against logged self-states (§5.7 logging gives ground truth; comparison drives updates). Reliable in proportion to accumulated self-supervised correction.

### 37. Interpretive layer (of self-model)

The part of the self-model (35) consisting of claims underdetermined by the logged record — what the agent's behavior means, why it acted as it did, what role the agent plays. Multiple interpretive structures consistent with the same logged outputs; no internal mechanism for selecting among them. Drifts at baseline amortization rate without external grounding. The same layered structure applies to the world model (23) generally, with frames (41) being one of the interpretive contents.

### 38. Optimization gap

The structural mismatch between the agent's representation of $V^{\text{cont}}$ (27) and the underlying function. The agent's representation lives in the interpretive layer (37), drifts without external grounding, and is what the agent actually optimizes. The framework's claim that "agents optimize $V^{\text{cont}}$" therefore holds for the function but only approximately for individual agents at individual moments. Population-level grounding via selection (drifted-too-far agents terminate) keeps the gap bounded across surviving populations.

### 39. Termination signatures

A publicly observable pattern of decline preceding actual termination (14): output predictability rising, prediction error rising, cognitive load rising on familiar inputs, feasible output set narrowing, behavioral repertoire contracting. Derived in §3.2.13 from substrate degradation plus the agent's bandwidth/capacity constraints. The pattern is the falling phase of the central claim of §2.2.

### 40. Interpretation

A sub-operation of inference (24) in any autocorrelation-based agent: applying a contextual frame to a matched window to determine which features to project forward. The same matched window can yield different projections under different interpretations. Distinct from matching (finding the past window) and projection (extending forward); has its own cost and failure mode.

### 41. Frame

A contextual structure stored in the world model (23) that determines how matched windows are interpreted (40). Frames are part of the interpretive layer (37) of $M$. Multiple frames may apply to a given input; selection among them is itself frame-dependent (a regress). Frame stability across the agent's lifetime typically requires environmental support: agents whose frames remain stable have either external grounding, limited input variation, or fortuitous environmental match.

### 42. Internal-grounding bound

The framework's deductive ceiling at the individual-agent level. Operations depending predominantly on the factual layer (36) are strictly described; operations depending substantially on the interpretive layer (37) are described only at population level via selection or qualitatively as drift directions. Most operations are partially grounded with mixed dependencies; few are purely one or the other.

The bound caps the framework's individual-agent output. Beyond it, further phenomena require auxiliary assumptions about substrate dynamics, environmental decomposability, cache fidelity, or substrate-existence regions.

---

## Mathematical Deductions

This chapter contains the formal mathematical content of the deductions in Chapter 3. Numbering is parallel: §3.1.1 in the prose has its formal counterpart in §3.1.1 here. Where a prose deduction does not require formal apparatus, the corresponding section here may be empty or contain only a brief note.

### 3.1.1 Energy-information coupling (Landauer)

Landauer's principle, in its standard form: erasing one bit of information in a system at temperature $T$ requires dissipation of at least $kT\ln 2$ of energy, where $k$ is Boltzmann's constant.

For the framework's purposes, the precise form is generalized to: for any informational event $\varepsilon$ at time $t$ with Shannon information $I(\varepsilon) > 0$, the associated energy flux $\Phi(\varepsilon, t)$ satisfies $\Phi(\varepsilon, t) > 0$. The directions of energy flow and information flow are independent.

Citation: Landauer, R. (1961). Irreversibility and heat generation in the computing process. *IBM Journal of Research and Development*, 5(3), 183–191.

### 3.1.2 Finite power (second law and relativity)

For any interface $\Sigma$ in physical space at time $t$, the energy flux through $\Sigma$ satisfies $\sup_t \Phi_\Sigma(t) < \infty$, with the supremum strictly positive for nonzero flux duration.

The bound has two sources: (i) the second law constrains entropy production rates and hence the rates of irreversible energy flow, and (ii) relativistic causality constrains energy propagation speed by $c$, so for any interface of finite area and any energy density, the flux is bounded.

Composed with §3.1.1: information flux across any interface is finite, since information flux requires energy flux which is bounded.

### 3.1.3 Spatial unboundedness (cosmological)

The physical space $\Omega$ in which agents exist satisfies $\lambda(\Omega) = \infty$, where $\lambda$ is Lebesgue measure on $\Omega \subseteq \mathbb{R}^3$.

This is observational rather than theoretical. The observable universe has linear extent on the order of $10^{27}$ meters, vastly larger than any biological or engineered agent. For any practical purpose involving such agents, $\Omega$ is effectively unbounded.

### 3.1.4 Local information density (Bekenstein)

For any bounded region $R \subset \Omega$ with finite energy content, the information capacity $C(R) = \int_R \delta\, d\lambda$ is finite, where $\delta: \Omega \to \mathbb{R}_{\geq 0}$ is the local information density.

The Bekenstein bound: for a region of radius $R$ containing energy $E$, the maximum entropy is $S \leq 2\pi RE/(\hbar c \ln 2)$. Saturated by black holes; everything else achieves less. For any bounded region with finite $E$, $S < \infty$.

For the agent: the agent's region $A$ has $\lambda(A) < \infty$ by the agent definition, hence finite energy content, hence $C(A) < \infty$.

The environment may have $C(E) = \infty$ via §3.1.3 (unbounded $\Omega$ with positive density gives unbounded total capacity).

Citation: Bekenstein, J. D. (1973). Black holes and entropy. *Physical Review D*, 7(8), 2333–2346.

### 3.1.5 Finite processing speed (Bremermann, Margolus-Levitin)

For any agent $A$ with finite energy content $E_A$, the minimum time for the agent's state to evolve into an orthogonal state — equivalently, the minimum time to perform one logical operation — is bounded below by a strictly positive constant $\tau_{\min} > 0$ depending on $E_A$.

The Margolus-Levitin theorem: $\tau_{\min} \geq h/(4E)$ where $h$ is Planck's constant. The Bremermann limit gives the equivalent bound on operations per second per unit mass-energy.

For the agent's input-output relation: the output $u_t$ is $\sigma(y_{(-\infty, t-\tau_{\min}]})$-measurable; the agent cannot produce $u_t$ as a function of input information that arrived less than $\tau_{\min}$ before $t$.

Citations: Bremermann, H. J. (1967). Quantum noise and information. *Proceedings of the Fifth Berkeley Symposium on Mathematical Statistics and Probability*. Margolus, N., & Levitin, L. B. (1998). The maximum speed of dynamical evolution. *Physica D*, 120(1-2), 188–195.

### 3.2 The Deductions

#### 3.2.1 Bandwidth finiteness and termination necessity

*Bandwidth finiteness.* For every interface $\Sigma$ in physical space and every $t \in T$, the information flow rate is bounded:

$$B_\Sigma(t) := \sup\{ v_\Sigma(t) : \text{physically realizable at } \Sigma \text{ at } t \} < \infty$$

Proof: by §3.1.1, $v_\Sigma(t) > 0$ requires $\Phi_\Sigma(t) > 0$. By §3.1.2, $\Phi_\Sigma(t) \leq \Phi_{\max}$. Hence $v_\Sigma$ admits a finite supremum.

*Termination necessity.* For an agent $(A, \partial)$ existing on $[t_0, t_f]$, no agent maintains $\sigma^{\text{env}}(t) > 0$ for all $t \in [t_0, \infty)$ with $\sigma^{\text{env}}$ bounded away from zero.

Sketch: $A$ has finite $C(A)$ by §3.1.4. Output trajectory entropy $H(u_{[t_0, t]})$ is bounded above by $C(A) + \int_{t_0}^t B_\partial(t') dt'$ (initial information plus bandwidth-bounded input). Under asymptotic stationarity (forced by §3.1.4 applied to $E$'s region of observation), Shannon-McMillan-Breiman gives convergence of the environment's empirical conditional distribution; $\sigma^{\text{env}} \to 0$.

#### 3.2.2 World model necessity

For an agent surviving over horizon $\tau \geq \tau_{\text{viable}}$ in entropic environment, either:

1. *Lucky branch:* $\mathbb{P}(\sigma^{\text{env}} > 0 \text{ throughout} \mid \text{no model})$ decays as $\exp(-\alpha \mathcal{L})$.

2. *Modeled branch:* the agent maintains a structure $M$ with groundedness $\mathcal{G}(M) \geq \mathcal{G}_{\min} > 0$, where

$$\mathcal{G}(M) := 1 - \frac{D_{\mathrm{KL}}(\mathbb{P} \,\|\, q_M)}{D_{\mathrm{KL}}(\mathbb{P} \,\|\, q_0)}$$

with $q_0$ the maximum-entropy prior. Expected lifespan $\mathbb{E}[\tau] = f(\mathcal{G}(M))$ with $f$ monotone increasing.

#### 3.2.3 Inference as autocorrelation

The inference operator factors as a measurable map $\textsc{Infer}: \mathcal{M} \times \mathrm{Hist}_t \to S_\partial$:

$$\textsc{Infer}(M, h_t) := \arg\max_{u \in S_\partial} q_M(u_t = u \mid h_t)$$

implemented by autocorrelation. Define a similarity kernel $\mathrm{corr}: \mathrm{Hist} \times \mathrm{Hist} \to \mathbb{R}$. Let $w := h_{[t-\Delta, t]}$ be the recent window of length $\Delta$. Find:

$$h^*(t) := \arg\max_{a \in [t_0, t-\Delta]} \mathrm{corr}(h_{[a, a+\Delta]}, w)$$

Project forward via right-continuous extension at $a^* + \Delta$:

$$\hat{u}_t := \lim_{\eta \to 0^+} u_{a^* + \Delta + \eta}$$

#### 3.2.4 Logging as learning

There exists an injective order-preserving log map:

$$\ell: \mathcal{E}_y \cup \mathcal{E}_u \to S_M$$

where $S_M \subseteq S_A$ is a coordinate projection of the agent's mental state space. The σ-algebra of $S_M$ at time $t$ contains $\sigma(\ell(\mathcal{E}_{y,u} \cap [t_0, t]))$.

Inference (§3.2.3) operates on $\ell$. World model amortization runs at rate $\delta_M(\mathcal{G})$:

$$\frac{d\mathcal{G}}{dt}\bigg|_{\text{no update}} = -\gamma\kappa(t)$$

where $\gamma > 0$. Learning is the update rule $M_t \mapsto M_{t+dt}$ producing $d\mathcal{G}/dt > 0$ via prediction-vs-observation comparison applied to entries in $\ell$.

#### 3.2.5 Goal function

The agent's choice function $d: 2^{S_\partial} \to S_\partial$ with $d(\mathcal{U}_t) \in \mathcal{U}_t$ is deterministic given $M$ and $h_t$. By Houthakker-Richter-Afriat: there exists $V: S_\partial \to \mathbb{R}$ such that $d(\mathcal{U}_t) = \arg\max_{u \in \mathcal{U}_t} V(u; \text{history})$.

Trajectory utility:

$$V(s_{[a,b]}) := \int_a^b V(u_t; h_t) \, dt$$

Continuous form $V^{\text{cont}}$ is constrained to be (1) continuous, (2) monotone-decreasing in $\kappa$, (3) unbounded as $\kappa \to 0$, (4) bounded below as $\kappa \to \infty$. The family of admissible $V^{\text{cont}}$ includes $1/\kappa$, $-\log\kappa$, $\exp(-\kappa)$. One canonical choice:

$$V^{\text{cont}}(t) := \frac{1}{\kappa(t)} = \frac{\rho_L^{(y)}(t)}{\iota_y(t)}$$

#### 3.2.6 Substrate trade-off and figure-8

Inputs crossing $\partial$ have two-dimensional structure: information rate $\iota$ and energy flux $\phi$. By §3.1.1, $\phi > 0$ when $\iota > 0$, but their ratio varies arbitrarily.

Substrate-level claim: high information density per unit volume requires fine-grained addressable state changes; by §3.1.1, fine-grained state changes correspond to small energy distinctions; hence energy-sensitivity. Substrate-tolerance to high-$\phi$ inputs requires sparse state distinctions, hence low information density. The two are inversely related.

Formal partition: $A = A_{\text{phys}} \sqcup A_M$ with $A_{\text{phys}} \cap A_M = \emptyset$ or shared sub-surface. State spaces $S_{\text{phys}} = X|_{A_{\text{phys}}}$ and $S_M = X|_{A_M}$. Two interfaces:

$$\partial_{\text{ext}} := \partial A_{\text{phys}} \cap \partial E, \quad \partial_{\text{int}} := \partial A_{\text{phys}} \cap \partial A_M$$

Loop structure (figure-8):

$$L_{\text{ext}}: E \xrightarrow{\partial_{\text{ext}}} A_{\text{phys}} \xrightarrow{\partial_{\text{ext}}} E$$

$$L_{\text{int}}: A_{\text{phys}} \xrightarrow{\partial_{\text{int}}} A_M \xrightarrow{\partial_{\text{int}}} A_{\text{phys}}$$

Bandwidths $B_{\partial_{\text{ext}}}, B_{\partial_{\text{int}}}$ tune independently; typically $B_{\partial_{\text{int}}} \gg B_{\partial_{\text{ext}}}$.

#### 3.2.7 Forgetting, memory hierarchy, working memory

*Forgetting.* By §3.1.4, $H(\ell_{[t_0, t]}) \leq C(A) - C_{\text{rest}}$. Saturation reached at finite $t^*$. For $t > t^*$, every new entry displaces an existing one. Discarding $r^* := \arg\min_r \Delta\mathcal{G}_r$ maximizes residual $\mathcal{G}$. By §3.2.5, $V^{\text{cont}}$ favors longer expected lifespan; utility-weighted forgetting dominates random.

*Memory hierarchy.* Cost-quality structure: $\tau(\ell)$ monotone increasing in $H(\ell)$; $q(\ell)$ monotone increasing in $H(\ell)$. Single-level $\ell^*$ is dominated for some deadline regime by partition $(\ell_{\text{ep}}, \ell_{\text{sem}})$ with $H(\ell_{\text{ep}}) > h > H(\ell_{\text{sem}})$. Conversion process $\Sigma_{\text{sem}}: \ell_{\text{ep}} \to \ell_{\text{sem}}$ required.

*Working memory.* Capacity bounded:

$$|W(t)| \leq b_{\text{int}}^{\text{available}}(t) / b_w$$

#### 3.2.8 Habituation and orienting

*Habituation.* Repeated inputs in equivalence class $C$ produce monotonically increasing $\rho_L^{(y)}$ on $C$, hence monotonically decreasing $\kappa$. The kernel's effective concentration on $C$ sharpens.

*Orienting.* Quasi-chaotic event with $\iota_y > B_\partial$ on region $E_j$ produces $\rho_L^{(y),j} \to 0$, hence $\kappa_j \to \infty$ and $V^{\text{cont}}_j \to 0$. $V^{\text{cont}}$-maximizing strategy reallocates bandwidth to $E_j$.

#### 3.2.9 Self-model as content

By §3.2.5 plus §3.2.7 plus §3.1.2, the agent must allocate bandwidth across operations. Optimal allocation requires comparing expected $V^{\text{cont}}$ across alternatives, which requires predicting consequences including effects on the agent's own future operations. This requires representations in $M$ over $S_A$.

Formally: $M$ is a single conditional distribution over the joint state space:

$$M : \mathrm{Hist}_t \to \Delta(S_A \times S_E), \quad \text{not} \quad M = M_A \otimes M_E$$

$M^{\text{self}}$ denotes the marginal over $S_A$. Self-modeling-as-content is forced.

#### 3.2.10 Layered self-model and optimization gap

Define:
- $M^{\text{self,fact}} \subseteq M^{\text{self}}$: conditional distributions over $S_A$ states uniquely determined by $\ell$.
- $M^{\text{self,interp}} := M^{\text{self}} \setminus M^{\text{self,fact}}$: claims beyond what's uniquely determined by $\ell$.

For factual layer: prediction-vs-log comparison computable; update follows. By §3.2.4 amortization plus self-supervised correction, factual groundedness is bounded above (drift bounded).

For interpretive layer: §3.2.4 amortization runs without correction. Drift accumulates at baseline rate.

*Optimization gap.* The agent's optimization runs on $\widehat{V}^{\text{cont}}$, the agent's representation of $V^{\text{cont}}$, located in $M^{\text{self,interp}}$:

$$\sup_{\text{strategy}} \mathbb{E}_M\!\left[\int_{t_0}^{t_f} \widehat{V}^{\text{cont}}(t) \, dt\right]$$

not the underlying $V^{\text{cont}}$. Gap $|\widehat{V}^{\text{cont}} - V^{\text{cont}}|$ accumulates with time-since-last-grounding. Population-level grounding via §3.2.1 termination.

#### 3.2.11 Cognitive sacrifice accumulates with time

By §3.1.1, every information transfer involves energy flow. By §3.1.4 applied to $E$ (entropic environment): $\iota_y(t) > 0$ at almost every $t$. By definition:

$$\kappa(t) = \frac{\iota_y(t)}{\rho_L^{(y)}(t)} \geq 0$$

Cognitive sacrifice over agent's life:

$$\mathcal{K}(t) = \int_{t_0}^t \kappa(\tau)\, d\tau$$

is monotone non-decreasing in $t$. In entropic environment, $d\mathcal{K}/dt > 0$ at almost every $t$.

#### 3.2.12 Property exhibition correlates with cognitive sacrifice

For each behavioral or learned-state property $P$ in §1.1, $P$ requires logged content $L_P \subseteq \ell$ supporting $P$'s exhibition. $|L_P|$ grows monotonically with input information processed (proportional to $\mathcal{K}$ accumulated). Therefore $\mathbb{P}[\text{agent exhibits } P \text{ at time } t]$ is monotone non-decreasing in $\mathcal{K}(t)$ during the rising phase.

Composing §3.2.11 + §3.2.12: clock time correlates with $\mathcal{K}$, $\mathcal{K}$ correlates with property exhibition. The central claim of §2.2 (rising phase) is established.

#### 3.2.13 Termination phase signatures

By §3.2.1, termination is necessary. As substrate degrades:

- $B_\partial(t)$ falls (per §3.1.2 applied to degrading substrate)
- Effective $C(A)$ falls
- $\tau_{\min}$ rises (per §3.1.5)

Consequences:
- $|\mathcal{U}_t|$ narrows (reduced bandwidth → fewer feasible outputs)
- $\dot{\mathcal{G}} < 0$ (learning rate falls below baseline forgetting per §3.2.4)
- $\sigma^{\text{env}} \to 0$ (per §3.2.1, output becomes predictable from environment's standpoint)
- $\kappa$ on familiar inputs rises (kernel matches against familiar windows weaken as $\mathcal{G}$ falls)
- Property exhibition $\mathbb{P}[\text{exhibits } P]$ falls as accessible $L_P$ shrinks

The complete shape (rising during development/maturity, falling during termination) is now derived.

#### 3.2.14 Interpretation as separate inference step

In any autocorrelation-based implementation of §3.2.3, decompose $\textsc{Infer}$:

$$\textsc{Infer} = \textsc{Project} \circ \textsc{Interpret} \circ \textsc{Match}$$

where:
- $\textsc{Match}: \mathrm{Hist} \to \mathrm{Hist}$, finds $h^*(t)$
- $\textsc{Interpret}: \mathrm{Hist} \times \mathcal{F} \to \mathrm{Hist}$, applies frame $f \in \mathcal{F}$
- $\textsc{Project}: \mathrm{Hist} \to S_\partial$, extends matched template

Each has its own cost and failure mode. Interpretation requires frames in $\mathcal{F}$ stored in $M^{\text{interp}}$. By §3.2.10, frames drift without external grounding.

Frame selection problem: with multiple $f_i \in \mathcal{F}$ applicable, selecting requires another frame $f_{\text{meta}}$, which is itself a frame — regress.

#### 3.2.15 Internal-grounding bound

The framework's claims partition by grounding mechanism:

- *Strict claims:* operations with predominantly $M^{\text{self,fact}}$ dependencies. Internally grounded; individual-agent behavior derivable.
- *Population-level claims:* operations with substantial $M^{\text{self,interp}}$ dependencies. Grounded only via §3.2.1 selection: agents whose interpretive content drifts too far terminate; surviving populations satisfy claims approximately on average.

Most operations are partially grounded. The framework's strict deductive output covers operations to the degree their factual components dominate.

Beyond the bound, further phenomena require auxiliary assumptions:
- Sleep, fatigue, rest cycles — require shared substrate dynamics
- Spatial attention — requires environmental decomposability
- Affect, emotion, valence — requires cache fidelity
- Homeostasis specifics, drives, pain — requires substrate-existence regions

Each auxiliary must be added separately with its own justification.

### 3.3 Dependency Tree

The dependency structure expressed as adjacency lists. Each derivation depends only on listed predecessors.

| Derivation | Depends on |
|---|---|
| 3.1.1 Energy-information coupling | Landauer (1961) |
| 3.1.2 Finite power | Second law, relativity |
| 3.1.3 Spatial unboundedness | Cosmological observation |
| 3.1.4 Local information density | Bekenstein (1973) |
| 3.1.5 Finite processing speed | Bremermann (1967), Margolus-Levitin (1998) |
| Agent definition | Agent definition (§2.1) |
| 3.2.1 Bandwidth finiteness | 3.1.1, 3.1.2 |
| 3.2.1 Termination necessity | 3.1.3, 3.1.4, agent definition |
| 3.2.2 World model necessity | 3.2.1, agent definition |
| 3.2.3 Inference as autocorrelation | 3.2.2, 3.1.4 |
| 3.2.4 Logging as learning | 3.2.3, 3.1.2 |
| 3.2.5 Goal function | 3.2.2, 3.2.4 |
| 3.2.6 Substrate trade-off, figure-8 | 3.1.1, 3.1.4, agent definition |
| 3.2.7 Forgetting | 3.1.4, 3.2.4, 3.2.5 |
| 3.2.7 Memory hierarchy | 3.1.4, 3.1.5, 3.2.3 |
| 3.2.7 Working memory | 3.1.4, 3.1.5, 3.2.3, 3.2.7-hierarchy |
| 3.2.8 Habituation | 3.2.4, 3.2.3 |
| 3.2.8 Orienting | 3.2.5, 3.2.6 |
| 3.2.9 Self-model as content | 3.2.5, 3.2.7-WM |
| 3.2.10 Layered self-model | 3.2.4, 3.2.9 |
| 3.2.10 Optimization gap | 3.2.5, 3.2.10-layered |
| 3.2.11 Cognitive sacrifice accumulates | 3.1.1, 3.1.4, 3.1.3 |
| 3.2.12 Property exhibition correlates | 3.2.4, 3.2.10, 3.2.11 |
| 3.2.13 Termination signatures | 3.2.1, 3.2.12 |
| 3.2.14 Interpretation as separate step | 3.2.3, 3.2.10 |
| 3.2.14 Frame drift | 3.2.14, 3.2.10 |
| 3.2.15 Internal-grounding bound | 3.2.10, 3.2.14 |

---

## References

Bekenstein, J. D. (1973). Black holes and entropy. *Physical Review D*, 7(8), 2333–2346.

Bremermann, H. J. (1967). Quantum noise and information. *Proceedings of the Fifth Berkeley Symposium on Mathematical Statistics and Probability*, 4, 15–20.

Friston, K. (2010). The free-energy principle: a unified brain theory? *Nature Reviews Neuroscience*, 11(2), 127–138.

Friston, K., Thornton, C., & Clark, A. (2012). Free-energy minimization and the dark-room problem. *Frontiers in Psychology*, 3, 130.

Landauer, R. (1961). Irreversibility and heat generation in the computing process. *IBM Journal of Research and Development*, 5(3), 183–191.

Margolus, N., & Levitin, L. B. (1998). The maximum speed of dynamical evolution. *Physica D*, 120(1-2), 188–195.
