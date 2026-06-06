# W3C Context Graphs Community Group Charter

**Draft — March 2026 · Version 2.0**

---

## Mission

<img src="figures/figure-12.png" alt="Using the word context without a precise definition is like using the word information before the bit was defined. We're changing that." width="35%">

The mission of the Context Graphs Community Group is to develop the **Context Graph Protocol** — a nested protocol stack for observing, measuring, and resolving uncertainty at system boundaries. Each system projects its local codebook onto a shared surface. The projections are compared. The protocol runs on the comparison.

Context, as used by this group, is the information that, when it crosses a boundary, changes how the receiving system interprets what it already has. This is not the casual use of the word. It is a formal object — the unit of resolution for uncertainty at boundaries.

**The Context Graph Protocol** is a recursive decision process for weighing intentions against costs to resolve uncertainty across boundaries. At every step: what do I intend to know, what does it cost to find out, and is the cost justified given the exposure? If yes, Ask — acquire the missing context. If the answer reveals further uncertainty, recurse. If the cost exceeds the value, Act on what you have or Halt. The protocol is designed to be general across digital systems, human interactions, organizational boundaries, and any combination of the two — because uncertainty at boundaries is not a property of software. It is a property of any interaction between parties that do not share a codebook.

**The Outcome of the Protocol is the Context Graph**: The act of running this recursive process is what produces a context graph — the structured, auditable record of every question asked, every resolution reached, and every gap that remains open at a boundary. Not a protocol about context graphs. A protocol that creates them through the act of measuring.

No existing standard bridges semantic systems (ontologies, knowledge graphs, RDF) and non-semantic systems (APIs, databases, spreadsheets, AI agents) under a single protocol for identifying and resolving uncertainty in mutual understanding. Semantic systems have rich representations but require prior agreement on terms. Non-semantic systems have none. Both encounter the same problem at boundaries: the system on the other side may not mean what you think it means, and nothing tells you. The Context Graph Protocol is designed to bridge these worlds — any system that can project onto five columns can participate, whether it carries a full OWL ontology or a flat CSV with no metadata at all.

<img src="figures/figure-6.png" alt="Decisions Under Null Uncertainty taxonomy: Risk, Knightian Uncertainty, Null Uncertainty" width="35%">

The protocol operates where global knowledge representations (organizational knowledge bases, ontologies, policies, shared data models) meet local interpretation contexts (user intent, operational setting, execution constraints, domain-specific framing) in decision systems and human–AI workflows. It standardizes the envelope, not the message: a shared structure for declaring what is required, demonstrating what is known, identifying what is missing, and recording what was decided — at every crossing point, between any two systems, regardless of their internal architecture.

### Why a 'Context Graph Protocol'?

**Context** — because that's the unit we're defining. Context is the information that, when it crosses a boundary, changes how the receiving system interprets what it already has. Without a formal definition of context, every framework that claims to handle it is using the word the way people used "information" before 1948 — casually, imprecisely, and without a way to measure it.

**Graph** — because context isn't a single value, it's a network of dependencies. The meaning of a field depends on its structure, which depends on which system produced it, which depends on when and where. Those dependencies form a graph. And the resolution history — what was asked, what was answered, what remains open — is an append-only log that accumulates over time. A graph is the only data structure that captures both the dependencies and the history.

**Protocol** — because this is a defined sequence of interactions between parties, not a static schema or an ontology. The dependency ordering (Context → Meaning → Structure → Data) is a sequence. The Halt/Ask/Act decision is a sequence. The recursion — where each resolution may reveal further uncertainty — is a sequence. A protocol tells two parties who have never met how to negotiate coherence at a boundary without prior agreement. An ontology tells one party how to represent what it already knows. We needed the first one.

*Theoretical foundations*
The Context Graph Protocol draws on three bodies of work:
- Active Inference (Friston, 2010), which provides the decision-theoretic grounding for selecting which measurement to take next
- Tensor Logic: The Language of AI (Domingos, 2025), which provides the computational grammar for operating on binary measurement outputs
- Unifying Business, Data, and Code: Designing Data Products with JSON Schema (Itelman and Viotti, O'Reilly, 2024), which provides the canonical claim form and the practical framework for codebook projection at system boundaries

The formal results connecting these foundations to the economics of boundary uncertainty are developed in [Liquid Coherence: A Protocol for Codebook Alignment at System Boundaries](https://zenodo.org/records/19005457) (Itelman, 2026) and [Decisions Under Null Uncertainty: The Unit Cost of Ignorance at System Boundaries](https://zenodo.org/records/19192949) (Itelman, 2026). These are working papers, math unverified (actively searching for the pending committee chair role).

Chair's background: The Group Chair's prior work is in computational psychometrics — the measurement of human cognition and decision-making under uncertainty in partnership with AI continuous learning. The protocol's design reflects this background: it treats coherence as a measurement problem, not an engineering problem, and its principles apply to human systems, organizational systems, and digital systems equally.

---

## Introduction

A database can enforce its own schema. An ontology can define its own terms. An AI model can optimize its own outputs. But none of these systems can know what a consuming system requires, what assumptions a producing system embedded, or whether the meaning of a term as defined in one context matches the meaning expected in another. That information does not exist inside either system. It exists only at the boundary between them — in the relationship between what one system declares and what another system needs.

This is why investments in better data quality, richer ontologies, and more capable AI models — however valuable in their own right — cannot solve the coherence problem. A column in a CSV does not know what the dashboard consuming it requires. A dashboard does not know what the CSV assumed. An AI agent retrieving a financial filing does not know which of 27 tagged revenue definitions matches the analyst's intent, and the analyst does not know the definitions exist. Every component can be individually correct and the composite result can still be wrong, because correctness at the boundary was never evaluated.

<img src="figures/figure-5.png" alt="No One Knows Your Intent — Context and Semantic Sovereignty" width="35%">

Two approaches exist for addressing this gap. The ontology approach defines all terms, constrains all schemas, and builds a complete semantic model before systems can interoperate. This works — when it can be done. In practice, only a small fraction of an organization's system boundaries ever receive that treatment. The vast majority operate in the null state — unmodeled, unmeasured, silently assuming alignment.

The protocol approach provides the cheapest possible instrument that any boundary can deploy. String equality on a five-column canonical form. Binary output. O(1) per facet comparison. If 80% of an organization's boundaries are running even a minimal coherence check at minimal semantic precision, that is measurable. It is calibratable. It is a surface that improves over time. Per the formal argument in *Decisions Under Null Uncertainty* (Itelman, 2026), measurable uncertainty at minimal precision is categorically better than null uncertainty at any precision — because null uncertainty is invisible, unpriced, and accumulating.

One of the outcomes of this research is that we hypothesize a direct way to measure the unit cost, with bit-precision, for organizational investment decisions around risk and semantic investment.

This Community Group builds the protocol. More precisely: this Community Group uses the protocol to build the protocol — applying its own methods to its own work as the first test case. The protocol is the minimal set of rules that give all participants shared guarantees of measurement across every boundary in the group's work.

From a technical perspective, the problem of transmitting information along with its structure and metadata is known and well-studied. What this group targets is the verification step that extends beyond structure to include verification of meaning. From an operational perspective, the protocol provides the simplest building blocks to teams, with a small set of principles that guarantee they can come together and share a way to measure uncertainty of coherence across meaning and structure.

The problem is structural: coherence emerges from interaction, not from any participant in the interaction. Therefore the solution must also be structural. It must operate at the boundary, not inside either system.

<img src="figures/figure-8.png" alt="Closed Systems vs Open Systems" width="50%">

It must define a shared standard for declaring what is required, demonstrating what is known, identifying what is missing, and recording what was decided — at every crossing point, between any two systems, regardless of their internal architecture.

The **Context Graph Protocol** is a layered protocol stack comprising four specifications. Each layer addresses a distinct problem that the layers above it cannot solve and defines the contract at its boundary with the layers above and below it.

| Layer | Name | Purpose | Key Operations |
|---|---|---|---|
| 0 | **Tensor Substrate** | Provides the unified mathematical substrate for representing and operating on contextual prerequisites, resolution states, and facet evaluations as tensor equations | Eigensum computation, Tucker decomposition, tensor factorization of multi-facet uncertainty vectors, dimensionality reduction across boundary-crossing state |
| 1 | **Context Graph** | An auditable, append-only hypergraph log of context events at local and global system boundaries, accessible only through the Context Graph Control Plane | Four-facet evaluation (meaning, structure, data, context); gap decomposition; validation report generation; knowledge graph view; authenticated access control |
| 2 | **Coherence Protocol** | Specifies how coherence measurements are made and compared across boundaries: whether representations are identical, whether sufficient information exists to compare them, and how uncertainty is expressed as collapsible pure states | Cross-boundary comparison of representations; gap detection; pure state encoding of uncertainty (e.g. 0,0,0,0,1,0); uncertainty collapse on sampling; resolution trace linking; canonical form reduction (O(N²) → O(N)); Act / Ask / Halt |
| 3 | **Decision Interface** | Consumes coherence measurements and resolution traces to drive downstream decisions | Facet-indexed uncertainty vector ingestion; decision model integration (threshold, Bayesian, utility, etc.); auditable decision replay; policy parameter application |

The Context Graph Specification (Layer 1) is authored by the Group Chair because it defines the shared data model and canonical claim form that all other layer specifications build upon. Steering committees develop specifications, integration strategies, and implementation guidance within their designated layers. No layer prescribes the internal architecture of the systems on either side of a boundary — each standardizes only the contract at its own boundary, leaving practitioners free to apply any compatible framework downstream.

## Scope

Many decision and information systems implicitly assume that a shared knowledge model and the local context at the point of interaction are aligned. In practice, this alignment frequently fails: terms carry different meanings across organizational, temporal, or operational boundaries; assumptions embedded in global models do not hold locally; and key context required to interpret state, policy, or meaning is absent, unavailable, or ambiguous at the point of use. These failures are distinct from data quality or optimization problems. They represent a structural interoperability gap in how context is communicated, validated, and resolved across systems.

The Context Graph Protocol addresses this gap as a protocol — not an ontology, not a vocabulary, and not a replacement for any existing semantic standard. A protocol defines a sequence of structured operations between parties. The Context Graph Protocol defines the operations required to observe uncertainty at a boundary, measure it through facet comparison, and resolve it through the Halt/Ask/Act decision sequence. It is a recursive decision process: each resolution may reveal further uncertainty, triggering further inquiry, until the cost of asking exceeds the value of knowing. This process is not specific to software. A human analyst questioning a data source, an AI agent checking a codebook, a compliance officer verifying a regulatory definition, and two organizations negotiating the meaning of a shared term are all running the same protocol. The parties differ. The process is the same. Existing semantic infrastructure (RDF, OWL, SHACL, SKOS) provides the vocabulary for expressing codebooks. The Context Graph Protocol provides the instrument for detecting whether two codebooks are aligned at a boundary — a capability no existing standard provides.

A Context Graph treats this gap as a first-class, interoperable artifact: a structured representation of the contextual prerequisites required for valid interpretation, their dependencies, and their resolution status. A Context Graph is instantiated on demand at a system boundary, populated during the course of a query or interaction, and produces a resolution trace recording what was checked, what was found, what was ambiguous, and what action was taken.

<img src="figures/figure-7.png" alt="Knowledge Graph (what is known) vs Context Graph (negotiating unknowns)" width="50%">

### In Scope

The Community Group will address the following areas:

#### 1. Context Graph Specification (Layer 1 — Single Boundary)

A core data model for expressing contextual prerequisites and resolution state at any individual system boundary. This includes a minimal vocabulary for describing common categories of contextual mismatch across four facets: meaning, structure, data, and context. The context facet encompasses both operational context (temporal, organizational, and environmental conditions at the point of use) and epistemic context (the actor's domain knowledge, assumptions, and capacity to interpret what a system returns). The specification will define the lifecycle of a Context Graph instance — instantiation, population, evaluation, trace production, and teardown — as an ephemeral, on-demand operation.

These instances carry no assumptions about the scale of the systems involved and can be joined, persisted, or kept ephemeral and in memory.

The Context Graph Specification defines the canonical claim form: the irreducible five-column projection surface (id, source, timestamp, key, value) onto which any system can externalize its codebook at the moment of contact, requiring no prior agreement on terms. The four-facet decomposition (Meaning, Structure, Data, Context), the dependency ordering (Context → Meaning → Structure → Data), and the canonical claim form are binding architectural commitments of the protocol. Implementations must conform to these structures; the semantic content expressed through them is unconstrained.

<img src="figures/figure-2.png" alt="A Protocol for Context Graphs — the four-facet canonical form" width="35%">

#### 2. Intent Map Specification

A declarative format for expressing coherence requirements at a boundary crossing: what must be checked, what rules apply, what thresholds trigger clarification or halt conditions, and what risk tolerance governs action under uncertainty. Intent Maps may be authored by users, inferred by systems, or composed from both. The specification will define a minimal schema that is format-agnostic (JSON, YAML, or other serializations).

#### 3. Coherence Protocol Specification (Layer 2 — Cross-Boundary Composition)

When multiple Context Graphs must relate — for example, when a downstream system consumes outputs from multiple upstream systems, each with its own boundary crossing — the relationships between individual Context Graphs carry information not present in any single graph. The whole is not the sum of its parts. The Coherence Protocol specifies how individual Context Graphs compose: how to detect alignment, conflict, or unknown state across multiple boundary crossings; how to propagate uncertainty; and how to produce a composite resolution trace. This enables coherence evaluation at arbitrary scale — between any two systems, across chains of systems, or within nested decision architectures.

#### 4. Resolution Trace Format

A standard format for recording the decision history of a Context Graph evaluation: what was checked at each facet, what resolution was reached, what actions were taken (act, ask, or halt — with optional flags), and what evidence supported each determination. Resolution traces are the persistent artifact that survives after a Context Graph instance is destroyed. They enable auditability, governance, and post-hoc analysis of boundary-crossing decisions.

#### 5. Protocol Actions

A minimal set of standardized actions available at any boundary evaluation:

- **Act** — alignment is sufficient for the current intent and risk tolerance.
- **Ask** — misalignment is detected but may be resolvable through structured inquiry.
- **Halt** — misalignment is detected and is unresolvable within the current scope.

Inherently, any one of these actions can include:
- **Flag** — alignment state is unknown; action depends on declared risk tolerance.
- **Trace** — all evaluations produce a resolution record regardless of action taken.

<img src="figures/figure-1.png" alt="Semantic Sovereignty — Act, Ask, Halt" width="35%">

#### 6. Coherence Failure Taxonomy for Agentic Systems

A classification of failure modes that arise when autonomous or semi-autonomous agents act on data whose contextual alignment has not been verified. This includes silent misalignment (definitions conflict but pipelines execute without error), semantic drift (meaning shifts between systems or over time without notification), absent context (required prerequisites for valid interpretation were never defined), and cascading incoherence (a coherence failure in one boundary crossing propagates through downstream agent decisions). The taxonomy will define each failure mode, its observable symptoms, its relationship to the four-facet evaluation model, and the protocol actions appropriate to detect or prevent it.

### Out of Scope

The following areas are explicitly excluded from the work of this Community Group:

**Defining ontologies or vocabularies for specific domains.** The Community Group standardizes how systems report what they know and do not know about meaning at a boundary. It does not standardize what meaning is in any particular domain. The protocol's canonical form is domain-agnostic by design: the five columns are fixed; the namespace is open. Any ontology, vocabulary, or schema can project onto the canonical surface. The protocol measures the boundary — it does not prescribe what is on either side of it.

**Replacing or competing with existing semantic web standards.** Context Graphs are complementary to RDF, OWL, SKOS, and similar vocabularies. They operate at the pragmatic layer — meaning in use, in context, by a specific actor — not at the semantic layer where meaning is defined by a system.

**Data quality frameworks.** Contextual misalignment is distinct from data quality. A column may be well-formed, well-typed, and complete, yet carry a definition that conflicts with the consuming system's intent. This is the gap the Context Graph addresses.

**Prescribing internal system architecture.** The specification does not require changes to the internal structure of any participating system. A Context Graph is instantiated at the boundary, not inside the systems on either side.

**Specifying runtime execution environments.** The specification defines the data model, vocabulary, and protocol. It does not prescribe how implementations host, execute, or scale Context Graph evaluations.

## Design Principles

Four principles govern the design of the Context Graph Protocol. These are binding commitments — all layer specifications and committee work must be consistent with them. These principles are not specific to software systems. They describe the structure of coherence at any boundary between parties that do not share a codebook — whether those parties are databases, AI agents, humans, teams, or organizations. The protocol is a theory of boundary coherence that happens to be implementable as software, not a software system that claims generality.

**Self-Organization within Governed Boundaries.** Some structures must be globally controlled: the canonical claim form, the dependency ordering, the four-facet decomposition, the Halt/Ask/Act decision sequence. These are the protocol's guarantees — the floor that makes interoperability possible. Everything above the floor is self-organizing: each committee, each implementation, each domain chooses its own vocabulary, resolution strategies, and decision thresholds. The protocol does not prescribe what meaning is. It prescribes the structure for comparing meanings across boundaries.

**Minimization of Structural Complexity.** The protocol commits to the simplest mathematical structures that can represent the problem. Binary values — match or mismatch — are the native output of every gauge comparison. Tensors organize these binary values across boundaries, fields, and time. Tucker decomposition factors the tensor to reveal structural patterns. Eigensums and eigenvalues identify the principal axes of misalignment. Pure states express uncertainty as collapsible superposition over binary outcomes. No layer introduces representational complexity that the layer below it does not require.

**Combinatorial Automata Logic.** The protocol's rules are recursive and composable. A gauge comparison at one boundary produces a binary vector. That vector is a claim in the canonical form. Claims compose across boundaries. Rules that operate on claims at one boundary can travel to another boundary and operate there, because the substrate is the same everywhere. The recursion of the Context facet — where every resolution may reveal further incompleteness — is the protocol's native mode of operation. The termination condition is economic (value of information goes negative), not logical.

**Minimization of Uncertainty through Projected Measurement.** The protocol's purpose is to minimize uncertainty at boundaries. This requires two capabilities: observing uncertainty as an event (the gauge produces a measurement), and measuring it in a projected space (both systems project their codebooks onto the canonical claim surface). All measurements are local — each system measures from its own perspective. The protocol's meta-surface — the field of Liquid Coherence — is the shared projection space where local perspectives become comparable.

<img src="figures/figure-13.png" alt="Liquid Cognitive Coherence — a gauge for holonic coordinates over time" width="50%">

It is the resolution surface on which every boundary state can be located, every movement can be priced, and the optimal allocation of verification effort can be computed. The field does not exist inside any single system. It emerges at the boundary. This is the mission of the Community Group: not graphs of words, but graphs of systems — open dynamical systems whose coherence is observable, measurable, and improvable across the full scope of an organization and its networks. 100% the language of AI and machine learning. 100% the language of human understanding and human decision-making. End-to-end, with the ability to rotate and zoom perspective from a single local boundary to an organization-wide coherence surface, governed by Intent Maps that give humans control over concepts that scale.

## Operating Culture

This Community Group uses its own protocol as its primary operating method. The Context Graph Protocol is designed to measure and resolve uncertainty at system boundaries. The group's own committees, specifications, and deliberations are system boundaries. We will apply the protocol to ourselves: instantiating Context Graphs at the boundaries between committees, running facet comparisons on our own specifications as they develop, producing resolution traces of our own design decisions, and using the Halt/Ask/Act sequence when our own terms, assumptions, or requirements are ambiguous.

This serves two purposes. First, it produces real test data from the earliest stage of the group's work — before any external pilot, the protocol will have been exercised on the problem of building itself. Second, it establishes the group's culture: this is a space for creative experimentation with new methods, not for enforcing adherence to existing standards.

Participants whose primary interest is in the rigorous application of existing semantic web standards — RDF, OWL, SHACL, SKOS — are welcomed and valued within the Semantic Alignment Committee, whose mission is to bridge those standards to the protocol's specification requirements. That committee ensures the protocol is compatible with the semantic web stack. It does not require the protocol to be built from the semantic web stack.

Participants whose interest is in inventing new instruments for measuring uncertainty, testing new representations, exploring new decision structures, and building things that do not yet exist — this is your group. The only non-negotiable requirement across all committees is that their work meets the Context Graph Protocol specification: projections onto the canonical claim form, binary facet outputs, compatibility with the Tensor Substrate. How each committee achieves that is their creative decision. What they build beyond that is their community's vision.

## Motivating Example

A driver pulls out of a parking lot. The navigation system says turn left. The map is correct. The route is correct. The GPS coordinates are correct. The driver turns left and goes the wrong direction.

The system did not know which direction the driver was facing. Every piece of data was accurate. The road network ontology was sound. The sensors worked. But one missing contextual prerequisite — the driver's orientation relative to the map's frame of reference — turned a correct instruction into a wrong action. The system did not flag the uncertainty. It did not ask. It issued a confident directive based on an incomplete model of the driver's local state. The recovery cost was a U-turn.

<img src="figures/figure-10.png" alt="Data was correct, Decision was wrong" width="35%">

Now consider the same pattern at higher stakes. A junior analyst asks an AI agent to build a revenue dashboard for a publicly traded company. The agent retrieves the company's 10-K filing via XBRL. The filing contains 27 distinct tagged references to revenue — gross revenue, net revenue, revenue from operations, revenue by segment, adjusted revenue, deferred revenue, and others — each with different calculation methodologies and reporting contexts. The agent selects one. It does not disclose which one it selected, that alternatives existed, or that the selection carries interpretive consequences.

The analyst does not know XBRL. They do not know that "revenue" is not a single number but a family of related measures whose differences can materially affect financial analysis. The dashboard looks clean. The numbers are real. The pipeline ran without error.

The analyst sends the dashboard to their manager, who forwards it to a portfolio team. A second AI agent ingests the dashboard to compare the company against peers. That agent pulls peer revenue from a different source using a different revenue definition. The comparison is now incoherent — not because any number is wrong, but because the numbers refer to different things. Nobody involved has visibility into the mismatch. The recovery cost here may not be a U-turn. It may not be recoverable at all.

These scenarios demonstrate four failure modes from the coherence failure taxonomy:

**Silent misalignment.** The navigation system selected a direction without confirming orientation. The financial agent selected one revenue definition from 27 alternatives. Both pipelines executed without error. Both produced plausible outputs that did not correspond to the actor's actual state.

**Absent context.** The navigation system lacked the driver's heading. The financial system never captured the analyst's level of domain expertise — specifically, their understanding that "revenue" is not a single unambiguous measure. In both cases, the system treated the interaction as if a shared understanding existed. It did not.

**Semantic drift.** When the dashboard moved from the analyst to the portfolio team, the implicit meaning of "revenue" shifted. The second agent applied a different definition without detecting that the upstream number carried a specific, undisclosed interpretation.

**Cascading incoherence.** Each boundary crossing — analyst to agent, agent to XBRL, analyst to manager, manager to portfolio team, dashboard to second agent — propagated and compounded the original misalignment. By the final comparison, the incoherence is embedded in a decision artifact that multiple stakeholders treat as authoritative.

A Context Graph instantiated at the first boundary crossing would have detected the unresolved uncertainty. In the navigation case, the system would **Halt** with a **Flag**: orientation is unknown, confidence in directional instruction is insufficient. In the financial case, the system would **Ask**: "revenue" maps to multiple definitions in the source, the analyst's intent does not specify which definition is required, and the analyst's domain expertise is unknown — surface the ambiguity, present the alternatives, and let the analyst make an informed selection. The resolution trace would then travel with the output, so that every downstream consumer — human or agent — can see what was known, what was unknown, and what was decided at each crossing.

## Practical Industry Value

### The scaling constraint

When N systems must interoperate, there are two approaches to ensuring coherence across them.

The first is point-to-point: build a custom translation or validation layer for each pair of systems that exchanges data. Two systems require one integration. Ten systems require 45. One hundred systems require 4,950. One thousand systems require 499,500. The integration cost grows with the square of the number of systems. Every new system added to the ecosystem imposes a burden on every existing system. This is not a resource allocation problem that more investment can overcome; it is a mathematical property of pairwise relationships in a growing network.

The second approach is protocol-based: define a shared canonical form that every system maps to independently. Each system expresses its requirements and evidence once, in terms of a common vocabulary. Coherence evaluation between any two systems then reduces to a comparison — what does the receiver require that the sender has not demonstrated? — without pairwise negotiation. The integration cost is linear: N mappings, one per system, each defined independently. Adding a new system to the ecosystem costs one integration effort regardless of how many other systems exist.

This is the same structural reduction that made the internet possible. Before the adoption of shared protocol stacks, connecting a new computer network to an ecosystem of N existing networks required building N custom translators. The Internet Protocol eliminated this quadratic cost by defining a canonical packet format that every network maps to and from independently. The total integration infrastructure dropped from O(N²) to O(N), and that factorization is why the internet scaled from four nodes to billions.

The Context Graph Protocol performs the same factorization for semantic coherence. The canonical form is not a universal dictionary of definitions — that would require all systems to agree on what terms mean, which is neither feasible nor desirable. The canonical form is a shared structure for expressing what is required and what is known at any boundary. Each system publishes its prerequisites and evidence in terms of that shared structure. Resolution traces produced at one boundary are legible at every other boundary without translation. The protocol standardizes the envelope, not the message.

### What this means in practice

An organization with 50 systems exchanging data today manages semantic coherence — to whatever extent it manages it at all — through a combination of tribal knowledge, manual documentation, and bespoke validation scripts. That is point-to-point integration, whether or not it is recognized as such. Adding a 51st system means understanding its interactions with each of the existing 50.

Under the Context Graph Protocol, adding that 51st system means defining its prerequisite mappings once, in terms of the shared vocabulary. Every existing resolution trace in the ecosystem is already legible to it. Every boundary evaluation it produces is immediately legible to every other system. The protocol-level integration cost of adding a new system is constant — one adapter — not proportional to ecosystem size.

This is not an analogy to internet protocols. It is the same mathematical structure applied to a different domain. The Internet Protocol proved that connectivity scales only when the interoperability contract is defined at the boundary, not inside the systems on either side. The Context Graph Protocol applies that same principle: the interoperability contract for meaning, structure, data, and context must be defined at the boundary, where the gap between systems actually exists.

## Steering Committees

The Community Group organizes its technical and strategic work through steering committees, each responsible for a distinct surface of the specification and its adoption. Committee chairs report to the Community Group Chair and are responsible for soliciting input, coordinating feedback, testing proposals within their domain, and maintaining the interface between their area of expertise and the broader group.

Initial operating expectations for Steering Committee Chairs:

1. One hour for a one-on-one session with the Community Group Chair approximately every six weeks to check alignment.
2. Communicating with general members who wish to participate within their committee.
3. Notifying the Community Group Chair if they are unable or no longer willing to continue in the role.

These expectations may be revised by the Community Group Chair as the group's operational processes develop.

**Coherence Protocol** — Chaired by the Community Group Chair. Owns the core specification for cross-boundary composition: how independent Context Graphs relate, how uncertainty propagates across multiple boundary crossings, and how composite resolution traces are produced. This is the central technical deliverable of the group.

**Tensor Substrate** — Owns the specification for the mathematical representation layer (Layer 0). Defines the canonical mapping from the claim form to tensor representations, the JSON-TL serialization format for Tensor Logic programs, and the operations (Tucker decomposition, eigensum computation, dimensionality reduction) that enable downstream ML and inference frameworks to operate on boundary coherence state. Ensures the substrate is minimal, binary-native, and sufficient to host self-referential models whose weights are stored as canonical claims.

**Syntax & Serialization** — Owns the Intent Map specification and all format-level concerns: how coherence requirements, resolution states, and traces are expressed in concrete serializations (JSON, YAML, and other formats). Ensures the specifications are implementable by developers working in mainstream toolchains without requiring adoption of any single data model.

**Semantic Alignment** — Owns the bridge between the Context Graph Protocol and existing semantic web infrastructure (OWL, RDF, SHACL, SKOS). The committee's deliverable is the mapping that enables semantic systems to meet the protocol's specification requirements: expressing codebook projections in the canonical five-column claim form and producing binary facet comparison outputs compatible with the Tensor Substrate. This ensures that organizations with existing ontologies, knowledge graphs, and constraint languages can participate in boundary coherence measurement without abandoning their current infrastructure. The committee validates that the protocol is compatible with, and does not duplicate, established W3C standards. The committee does not define the protocol's core data model, dependency ordering, or canonical form — those are Layer 1 commitments authored at the Group Chair level.

**Industry Adoption** — Owns the relationship between the specification and real enterprise problems. Responsible for sourcing use cases from active industry engagements, identifying organizations willing to pilot the protocol, validating that the specification addresses problems practitioners recognize, and building the business case required to advance from Community Group to Working Group status.

**Applied Knowledge** — Owns the bridge between specification, deployment, and measuring benefit to users and organizations.

**Decision Interface** — Owns the specification for how coherence measurements interface with decision models. Defines the contract between the measurement layer (the uncertainty vector produced by a Context Graph evaluation) and any external decision model that consumes it: what inputs the decision model receives, what outputs it must return, and what must be recorded in the resolution trace to ensure the decision is auditable and replayable. Ensures the interface is neutral to the choice of decision framework — threshold-based rules, utility models, Bayesian inference, or other approaches — so that the measurement and decision layers remain independently replaceable.

<img src="figures/figure-4.png" alt="The Context Graph Decision Interface" width="35%">

**Agentic / AI** — Owns the specification surface for autonomous and semi-autonomous agents that cross boundaries at machine speed. Addresses how agents implement the protocol, how the coherence failure taxonomy applies to agent behavior, and how the rate of boundary crossing under agent-paced operation affects the accumulation of unpriced exposure.

**Error Analysis & Theory** — *(Pending chair appointment.)* Owns the formal analysis of protocol correctness, failure mode classification, and the theoretical foundations connecting the protocol to decision theory, information theory, and the economics of uncertainty. Maintains the relationship between the protocol's operational behavior and the formal results in *Decisions Under Null Uncertainty* and *Liquid Coherence*.

**Inference & Surprise** — *(Pending chair appointment.)* Owns the connection between the protocol and active inference: how prediction error at boundaries drives the Ask action, how the learning loop (gauge outputs → trained classifiers → improved measurement) formalizes as an active inference policy over the context graph, and how the system learns where coherence breaks.

**Category Theory** — *(Pending chair appointment.)* Owns the compositional mathematics of the protocol: formal proof that composition rules across chains of boundaries preserve the properties each individual boundary measurement guarantees. Connects to functors, natural transformations, and the mathematics of structure-preserving maps across boundaries.

**Economic Theory** — *(Pending chair appointment.)* Owns the VOI decision rule, the resolution surface as a computable optimization problem, the unit cost of context acquisition, the prospect theory connection (why organizations under-invest in verification), and the exposure accumulation rate under agent-paced operation. Prices every question the protocol asks and every question it doesn't.

## Deliverables

### Specifications

The Community Group intends to produce the following Community Group Reports:

1. **Context Graph Data Model** — Core specification for representing contextual prerequisites, resolution state, and the four-facet evaluation model at a single system boundary. Defines the canonical claim form (id, source, timestamp, key, value), the four-facet decomposition, and the dependency ordering. Authored at the Group Chair level as the binding Layer 1 specification.
2. **Intent Map Format** — Specification for declaring coherence requirements, risk tolerance, and evaluation rules at a boundary crossing.
3. **Coherence Protocol** — Specification for composing multiple Context Graphs across system boundaries, including uncertainty propagation, cross-boundary alignment detection, and composite resolution traces. The Coherence Protocol requires all boundary inputs to conform to the canonical claim form as specified by the Context Graph Data Model. Claims not conforming to this form are not evaluable by the protocol.
4. **Tensor Substrate Specification** — Specification for representing and operating on contextual prerequisites, resolution states, and facet evaluations as tensor equations, enabling practitioners to apply any ML or inference framework downstream. Defines the canonical mapping from the claim form to tensor representations and the JSON-TL serialization format for Tensor Logic programs. The specification additionally defines the canonical form for storing converged perceptron weights as claims in the Context Graph, enabling each boundary crossing to contribute to a shared, auditable learning substrate that is retrievable for global inference across holons.
5. **Resolution Trace Format** — Specification for recording and exchanging the decision history of Context Graph evaluations.
6. **Decision Interface Specification** — Specification for the contract between Context Graph coherence measurements and external decision models. Defines the input surface (the facet-indexed uncertainty vector, policy parameters, and boundary metadata), the output surface (a protocol action and optional flags), and the trace requirements for auditable decision replay. The specification is neutral to the choice of decision framework: it standardizes what a decision model receives and what it must return, not how it reasons internally.

### Supporting Documents

The Community Group will also produce:

- **Use Cases and Requirements** — Documented scenarios from knowledge management, enterprise data integration, AI agent orchestration, multi-system decision workflows, and human–AI interaction.
- **Implementation Guidance** — Best practices for implementers, including integration patterns for common architectures (API gateways, data pipelines, agent frameworks, query systems).
- **Test Vectors** — Reference inputs and expected outputs for validating conformance of Context Graph implementations.

## Participation

Practitioners and researchers in knowledge representation, semantic web technologies, ontology engineering, decision science, AI/ML systems integration, enterprise knowledge management, and human–computer interaction. Developers building systems where shared knowledge models must be interpreted across diverse operational contexts are especially encouraged to join. Representatives from standards bodies, regulatory agencies, and organizations deploying autonomous or agentic AI systems in production environments are welcomed as participants or observers.

## Publication Intent

This group intends to publish Community Group Reports, including specification-style documents and supporting notes (use cases, requirements, implementation guidance, and test vectors).

## Dependencies

The Community Group does not have formal dependencies on external groups but will monitor related work and seek alignment where practical.

## Community and Business Group Process

This Community Group operates under the W3C Community and Business Group Process. Terms of participation and contributor licensing are governed by the W3C Community Contributor License Agreement (CLA).

## Transparency

The group will conduct its technical work primarily in its public GitHub repository. Decisions and discussion summaries will be posted to the group's public mailing list. All contributions to specifications will be made under the W3C Community Contributor License Agreement.

## Decisions and Amendments

The group prioritizes iterative development and testable outputs. Decisions will be made through consensus where possible. Where consensus cannot be reached, the Chair may call for a group vote, requiring a simple majority of participants who have expressed a position. The initial Chair is Ron Itelman, as proposer of the Community Group. The founding Chair serves for the duration of the group unless they resign or are removed through the W3C Community Group Process. The founding Chair may appoint co-Chairs. Co-Chairs serve at the founding Chair's discretion.

### Group Chair Authority

The Group Chair maintains the group-level glossary and binding definitions that all committees align to. Committees may extend these definitions internally for their own work, but their public-facing specifications and deliverables must be consistent with the group-level glossary. The Group Chair may update the glossary at any time; substantive changes will be communicated to the group mailing list.

Steering committee chairs are appointed by the Group Chair and serve at the Group Chair's discretion. The Group Chair may remove a steering committee chair at any time if, in the Chair's judgment, the committee's work is not aligned with the charter, the protocol's design principles, or the group's operational needs. Removal will be communicated respectfully and with stated reasoning. The Group Chair may appoint a replacement or leave the position open for recruitment.

### Charter Ratification

This charter is presented in draft form at the group's inaugural meeting and will remain in draft through the initial operating period. The Group Chair may make corrections, clarifications, and refinements to the draft charter during this period — including typographical fixes, structural reorganization, and language improvements — without requiring a vote.

The formal ratification process will begin at the group's first quarterly meeting. At that time, the Chair will call for a 14-day feedback period during which participants may submit principled objections via the group's public mailing list or GitHub repository. If no principled objections are received within that period, the charter is ratified by consensus. If principled objections are received, the Chair will address them through revision or call a group vote, requiring two-thirds of votes cast to approve the charter.

Once ratified, substantive amendments follow the same process: 14-day notice, consensus or two-thirds vote. Non-substantive corrections (typos, formatting, link updates) may be made by the Group Chair at any time.


# RELEASE OF ALPHA CONTEXT GRAPH SPECIFICATION - DRAFT - v0.01 - NOT SUITABLE FOR QUOTATION + ZENODO PAPER UPDATES + GOING FORWARD

## ZENODO PAPERS

I finally have mathematicians with formal published papers, and the math I attempted to, and openly without enough knowledge to validate, finally can be put to rest. Leo Torres will be assisting me as an advisor, so the protocol is grounded in proper mathematical precision.

## GOING FORWARD - the community drives, and I'm here to help. 
Multiple enterprise companies have employees who have asked for support to move this to a working group. I'm imaginging a community driven hackathon of html components. I want to meet everyone. I'm taking a break from any coding for a while, but I do want to meet people.

# FINALLY THE SPEC

# The Observatron

When you wish to draw a boundary over anything, you can add a circle, but what observes what goes in and out of the circle, and the properties of the boundary itself is the *Observatron*

*The unit: a spike anchored at a boundary, with access across its levels. You, reading this, are another bounded observer — your own observatron — which is why you can recognize the structure.*

An Observatron is the act of putting a mathematical boundary around any information in the [“U”] level: Experiential Interaction and Human-observable level cognition that can be geometrically represented, or abstracted to geometry if rendered in a browser (everything ultimately has pixel grid geometry).

When the schema for these comparisons is reduced to the math object “Four Facet Model” of URL referents in Meaning, Structure, and Context as a collection of tables for row by row, url MATCH/NO MATCH comparison.

Each Four Facet object is one “Spike” geometrically represented as a tetrahedron on the boundary of the observatron. It is an imaginary object because it is pointing to [“U”], and imaginary concept as the Observer the Observatron bridges to.

YOU, interacting with if(TRUE) cognitively, can be modeled like this diagram, with the Observatron as Automata to programmatically ensure alignment of intent and mutual understanding from within a function, and without.


`spike @ boundary[0] → access levels [U, -1, 0, +1] → if(facet EMPTY) {dark_counter++}`
<div height="30">&nbsp;</div>
<div align="center">
<img src="https://raw.githubusercontent.com/RonItelman/public-content-url/main/new-img-url/figure-3.png" width="100%"/>
</div>

# Step-by-Step Logic of the Context Graph Protocol
*W3C Context Graph Community Group - Ron Itelman, Chair*

**v0.1** - released May, 2026


This notebook will instantiate an `Observatron`, which observes interactions of a logical step in a `Workflow`. An `Observatron` has configurable levels of precision and granularity technically, and an `Intent Map` binds the logic of each cognitive step towards accomplishing the `Workflow`, labelled a `Task`.

A `Task` example is "Open a CSV", as is "Read the CSV". A `Workflow` contains many `Task`s, such as "Analyze the daily executive report". A `Task` can be marked completed `1` (`TRUE`) or `0` (`FALSE`). A `Workflow` can be marked completed only when all required `Tasks` are completed in its logical chain.

This notebook will demonstrate several intents by binding them to HTML elements in a DOM:

*   Monitor a textarea
*   Upload a CSV

### Filesystem–URL symmetry

A protocol URL and the file it resolves to MUST share the same path. Every character that appears in the URL path after `cgp:/` MUST appear in the filesystem path. No URL-encoding, no character substitution, no case normalization, no extension inference.

The implication: any character used in a protocol URL must be safe in:

- The URL path layer (per RFC 3986, unreserved or carefully chosen reserved).
- The filesystem path layer on Linux, macOS, and Windows.
- Common static-file hosts (GitHub, GitLab, S3) without configuration-dependent rewriting.

Path segments used as protocol markers (e.g., `/c/`, `/i/`) MUST be chosen from characters that are safe in all three layers without escaping. Single lowercase letters and standard alphanumerics meet this bar; characters like `+`, `$`, `&`, `=`, and `?` do not.

- `cgp:/r/keys/i/<name>.md` — **minted-ignore.** Pure bookkeeping. Excluded from `B`, `η`, and Level 2 metrics.
- `cgp:/r/keys/c/<name>.md` — **minted-count.** System-recorded with comparison value. Counted.

| Key URL | Marker | Where minted |
|---|---|---|
| `cgp:/r/keys/c/task.md` | minted-count | observatron activation + spike intent-match |
| `cgp:/r/keys/c/component-type.md` | minted-count | observatron activation + spike intent-match |
| `cgp:/r/keys/c/frame.md` | minted-count | spike intent-match only |
| `cgp:/r/keys/c/gate.md` | minted-count | spike intent-match only |
| `cgp:/r/keys/c/trigger.md` | minted-count | spike intent-match only |

## Creating Observatrons on an Addressable Field
A `System` is the namespace an `Observatron` lives in. It is a bounding box, not an actor.

The host (e.g., the HTML page) instantiates `Observatrons`; the `System` is the address space those `Observatrons` share.

A single `System` can have many `Observatrons`, and there can be many `Systems`. All `Observatrons` across all systems are in a `Field`, meaning an array, of equal hierarchy, with addresses.

The host handles a declaration of an `Observatron`:

```html
<div cgp-id="cgp:/r/components/html/forms/textarea.md"
     cgp-system-id="0"
     cgp-observatron-id="0"
     cgp-target=".textarea"
     cgp-intent="cgp:/r/intents/components/html/forms/textarea.md">
  <textarea class="textarea"></textarea>
</div>
```

The attribute set crosses the boundary verbatim and becomes the observatron's `/data`:

```json
{
  "/data": {
    "value": {
      "cgp-id": "cgp:/r/components/html/forms/textarea.md",
      "cgp-system-id": "0",
      "cgp-observatron-id": "0",
      "cgp-target": ".textarea",
      "cgp-intent": "cgp:/r/intents/components/html/forms/textarea.md"
    }
  }
}
```

## URLs MUST Use a Restricted Character Set

A protocol URL and the filesystem path it resolves to MUST be byte-identical across every layer: the URL layer (RFC 3986), all three OS filesystem layers (Linux, macOS, Windows), and common static-file hosts (GitHub, GitLab, S3). No encoding, no case-folding, no normalization, no host-dependent rewriting. This is what makes URL identity a lossless proxy for referent identity: two equal URLs resolve to the same file on every host, with no silent transformation between layers.

To guarantee this, the available character set is restricted to those characters that survive every layer unchanged.

### Allowed characters

Every character in a `cgp:` path segment MUST be drawn from:

- lowercase ASCII letters `a`–`z`
- digits `0`–`9`
- hyphen `-`
- underscore `_`
- dot `.`

The forward slash `/` separates path segments and MUST NOT appear inside a segment. No other character is permitted.

### Prohibited, and why

- **Uppercase `A`–`Z`** — case-insensitive filesystems (macOS APFS/HFS+ default, Windows NTFS) fold case, so `Task.md` and `task.md` resolve to the same file. Uppercase cannot round-trip between case-sensitive and case-insensitive hosts. Lowercase-only is mandatory across the **entire** path, not only protocol markers.
- **Whitespace and percent `%`** — space forces percent-encoding (`%20`); `%` is the encoding escape itself. Both violate the no-encoding rule.
- **Reserved URL characters** (`? # [ ] @ ! $ & ' ( ) * + , ; =`) — RFC 3986 assigns these syntactic meaning in a URL; they do not survive the URL layer as literal path characters without encoding.
- **Unsafe/unwise characters** (`~ ^ { } | `` ` `` < > " \`) — rejected or rewritten by some hosts; backslash is a path separator on Windows and a literal elsewhere.
- **Colon `:`** — illegal in Windows filenames; reserved for the `cgp:` scheme prefix only, never inside a path segment.
- **Non-ASCII / Unicode** — Unicode normalization differs by OS (macOS stores decomposed NFD, Linux composed NFC), so the "same" filename can be different bytes. The set is ASCII-only by construction; this MUST NOT be relaxed.

### Structural rules

- A path segment MUST NOT be empty (no `//`).
- A path segment MUST NOT be `.` or `..` (path traversal resolves to a different file).
- A path segment MUST NOT begin or end with a dot (`.` ); leading dots are hidden files on Unix, trailing dots are stripped on Windows.
- A dot within a segment separates name from extension (e.g. `task.md`).

### Summary

Permitted per segment: `[a-z0-9._-]`, separated by `/`, ASCII-only, subject to the structural rules above. Any character outside this set is prohibited because it cannot be guaranteed to cross all layers byte-identically — and a character that does not round-trip losslessly would reintroduce, inside the protocol itself, the silent boundary failure the protocol exists to detect.

## Protocol Top-Level Namespaces

A `cgp:/<namespace>/<path>` URL resolves the same way for every namespace:

1. Strip the `cgp:/` prefix.
2. Fetch the rest as a file path on the implementation's host (filesystem, GitHub, S3, any static-file host).

The four namespaces differ in what kind of content lives at their paths:

- `/r` — reference. Static files of any extension. Documentation (`.md`), intent maps (`.json`), handlers (`.js`), and any other canonical artifact the protocol or its components publish.
- `/a` — apps registered on the context graph.
- `/e` — math expressions in expression-tree format.
- `/s` — `System` namespace where Observatrons and their spikes are addressed.

### Examples

| URL | File served |
|---|---|
| `cgp:/r/keys/c/task.md` | `/r/keys/c/task.md` |
| `cgp:/r/components/html/forms/drag-and-drop.md` | `/r/components/html/forms/drag-and-drop.md` |
| `cgp:/r/tasks/intent-matched.md` | `/r/tasks/intent-matched.md` |
| `cgp:/r/policy.json` | `/r/policy.json` |

Resolution works on any static-file host: GitHub, GitLab, S3, raw filesystem.

### No-Parsing Rule

The protocol records what crossed the boundary verbatim. No parsing, no transformation, no normalization.

- If an HTML attribute carries a string, `/data` records that string.
- If an attribute carries a JSON-encoded object as a string, `/data` records the string — not the parsed object.
- If a CSV cell contains the text `"123"`, `/data` records `"123"` — not the number `123`.
- Attribute names cross verbatim. `cgp-intent` in HTML appears as the key `"cgp-intent"` in `/data`.

Whoever consumes `/data` may parse it later — that is the consumer's responsibility, declared via `/structure`. The protocol's only job is to record the raw payload faithfully.

```
cgp:/r/intents/components/html/forms/textarea.md     ← prose declaration of the intent
cgp:/r/intents/components/html/forms/textarea.json   ← the intent map (JSON)
cgp:/r/intents/components/html/forms/textarea.js     ← the handler code
```


## Spikes: Four Facet Model Objects

### Facet #1 — Data

#### `/data`

`/data` carries whatever crossed the boundary as a payload. The wrapper shape is always `{ "value": <payload> }`, where `<payload>` is any JSON value (including empty values like `""`, `[]`, `{}`).

- For an observatron, the boundary is instantiation. The payload is the instantiation parameters that brought the observatron into being. Common shapes: HTML element attributes, an intent map, a configuration object.
- For a spike, the boundary is the observatron's watched interface. The payload is the datum that crossed it.
- One boundary event = one payload.
- Payload shape is unconstrained; `/structure` declares how it could be validated.
- Payload is recorded verbatim. See **No-Parsing Rule** above.

---

### Facet #2 — Meaning

`/meaning` records a human-readable gloss (a plain language explanation) of a referent, not the referent itself. The protocol's claim is only that the gloss is recorded verbatim and attestable — never that it is true or complete. Two /meaning entries are compared by the gauge as pointers: the gauge reports whether they reference the same thing, not whether either gloss is correct.

#### `/meaning`

- MUST have exactly two columns: `key` and `value`.
- MUST contain only human-readable definitions.
- MAY have any number of rows: zero, one, or many.
- MUST NOT contain tags, schemas, or any other column.

**Example**

```json
{
  "/meaning": {
    "key": [
      "peanut butter",
      "chocolate",
      "peanut butter & chocolate"
    ],
    "value": [
      "A spread made from ground roasted peanuts.",
      "A confection made from cacao beans.",
      "A classic flavor pairing — the salty richness of peanut butter complements the sweetness of chocolate."
    ]
  }
}
```

This shape supports:

- A single term being defined (one row)
- Multiple unrelated terms in the same entry (many rows, no relationship)
- Atoms plus their composition (rows for parts, plus a row for the whole)

**Empty** (no definitions yet):

```json
{
  "/meaning": {
    "key": [],
    "value": []
  }
}
```

---

### Facet #3 — Structure

#### `/structure`

- MUST have exactly two columns: `key` and `value`.
- `key` names the schema language (e.g., `json-schema-2020-12`, `regex`).
- `value` carries the schema as a string in the form native to that schema language.
- MAY have any number of rows: zero, one, or many. Multiple rows = multiple schemas (in different languages) declared against the same `/data`.
- MUST NOT contain configuration, descriptions, or runtime behavior.

The protocol provides the slot for declaring a schema; it does not perform validation.

#### Examples

**JSON Schema**
```json
{
  "/structure": {
    "key": ["json-schema-2020-12"],
    "value": ["<schema as string>"]
  }
}
```

**Regex**
```json
{
  "/structure": {
    "key": ["regex"],
    "value": ["^[0-9]{4}-[0-9]{2}-[0-9]{2}$"]
  }
}
```

**Empty** (no constraints declared):

```json
{
  "/structure": {
    "key": [],
    "value": []
  }
}
```

---

### Facet #4 — Context

#### `/context`

- MUST have exactly six columns: `anchor`, `source`, `channel`, `timestamp`, `key`, `value`.
- All six columns are parallel arrays of equal length.
- MUST be a time-ordered log of events.
- MUST NOT contain configuration, schemas, or human-readable descriptions outside the event log.


**Column definitions**

| Column | Plain-English question | Holds |
|---|---|---|
| `anchor` | What entry is this row about? | URL of the entry being described. Invariant across all rows of one entry. |
| `source` | Who wrote this row? | URL of the observatron that emitted the row. In alpha, equal to the owning observatron of the entry; in beta, can differ when one observatron writes into another's `/context`. |
| `channel` | What kind of thing is this row recording? | A `cgp:/r/<path>` URL naming the kind of event. The conduit, in Shannon's sense — the named channel two observatrons agree on for this kind of transmission. |
| `timestamp` | When was this row written? | ISO 8601 UTC, millisecond precision. |
| `key` | What property of the entry is this row asserting? | A key URL under `cgp:/r/keys/`. Externally-registered keys live at `cgp:/r/keys/<name>.md`. System-minted keys live at `cgp:/r/keys/c/<name>.md` (minted-count) or `cgp:/r/keys/i/<name>.md` (minted-ignore). |
| `value` | What is the asserted property's content? | Either a `cgp:/r/<path>` reference or a literal string. |

Read row N as a sentence: *at `timestamp[N]`, observatron `source[N]` recorded — on channel `channel[N]` — that the entry at `anchor[N]` had `key[N]` = `value[N]`.*



---
## Intent Map

An intent map is an in-memory notepad shared by three parties — system, user, and organization — during a session. Each party writes into its own frame. The notepad lives in memory for the duration of the session; persistence, if any, is the concern of other modules.

### The three frames

- **`program-intent`** — the system's section. Engineering-defined behavior at the boundary.
- **`user-intent`** — the user's section. User responses, user-set policies, user-declared intents during the session.
- **`business-intent`** — the organization's section. Compliance, audit, policy concerns.

Each frame can be updated in real time by its owner during the session. The frames coexist — a single boundary crossing may match triggers in any combination of frames.

### The three decision gates

Within each frame, triggers are grouped under three gates that name what the system must do:

- **`halt`** — block the in-flight action.
- **`ask`** — pause and request input from the user.
- **`act`** — proceed and act on the data.



### Canonical intent map

```json
{
  "program-intent": {
    "halt": [],
    "ask":  [],
    "act":  [
      {
        "trigger-url": "cgp:/r/triggers/console-log-on-keyup.md",
        "predicates": [
          { "type": "event", "event": "keyup" }
        ],
        "handler": { "console-log": true }
      }
    ]
  },
  "user-intent":     { "halt": [], "ask": [], "act": [] },
  "business-intent": { "halt": [], "ask": [], "act": [] }
}
```

This is the textarea intent in canonical form: on keyup, console.log the value. One trigger, one predicate, one handler instruction. Every other intent is a richer instance of the same shape.

### How a trigger is evaluated

1. The runtime sees a boundary crossing on an observatron.
2. The runtime walks each frame (`program-intent`, `user-intent`, `business-intent`), each gate (`halt`, `ask`, `act`), and each trigger within.
3. For each trigger, the runtime evaluates every predicate in the `predicates` array.
4. If all predicates return true, the trigger fires.
5. The trigger's `handler` payload is delivered to the intent's handler code at `cgp:/r/intents/<path>.js`.
6. What the handler does is the handler's responsibility — log, mint spikes, update DOM, whatever the intent declares. The runtime witnesses; the handler acts.

### Channel

When a trigger fires and the handler mints spikes, those spikes emit on a single uniform channel:

`cgp:/r/events/intent-matched.md`

The spike's `/context` records which frame, gate, and trigger produced it, so observers can trace the crossing back to the declared intent. Per-event channels like `csv-dropped` are no longer defined as protocol-level events; CSV-drop handling is now expressed as a trigger inside the drag-and-drop intent, and its spikes flow through `intent-matched`.

---

### Trigger shape

Each gate holds an array of triggers. A trigger is a `trigger-url` paired with a predicate-list and a handler payload:

```json
{
  "trigger-url": "cgp:/r/triggers/<name>.md",
  "predicates": [
    { "type": "<predicate-name>", "...": "predicate-specific fields" }
  ],
  "handler": { "...": "handler payload" }
}
```

The `trigger-url` points at the trigger's reference doc, providing a stable name for the trigger that the spike's `/context` records when the trigger fires. The predicates determine when the trigger fires (AND semantics across the predicate array). The handler payload is delivered verbatim to the intent's handler code.

Predicates are opaque to the runtime — any function returning a boolean. Examples: `event` (a named DOM event occurred), `regex` (input matches a pattern), `match` (input contains a string). New predicate types are added by creating new entries under `cgp:/r/predicates/`.

### Intents: how intent maps are stored and referenced

An intent is declared in three parallel files under `cgp:/r/intents/`, all keyed by the same tail path:

| URL | Purpose |
|---|---|
| `cgp:/r/intents/<path>.md` | Prose declaration of the intent. |
| `cgp:/r/intents/<path>.json` | The intent-map JSON (the notepad's initial seed). |
| `cgp:/r/intents/<path>.js` | The handler code that consumes the intent map and acts on it. |

A reader who finds any one of the three files can derive the other two by extension swap.

---
## `/e` — Math Expressions for Counting

The `/e` namespace holds language-neutral specifications for the variables we count and compare across the field. Each variable resolves to one URL whose file defines what the variable means, how to compute it, and three equivalent representations: an expression tree, a Unicode linear form, and a JSONL form.

A consumer in any language (JavaScript, Python, Rust, a spreadsheet, a math notebook) reads the same `/e` file and produces the same number. The math is canonical; the implementation is downstream.

### Variable index

| Variable | URL |
|---|---|
| `total-spike-count` | `cgp:/e/dark-uncertainty/calculators/total-spike-count.md` |
| `total-observatron-count` | `cgp:/e/dark-uncertainty/calculators/total-observatron-count.md` |
| `total-facets-count` | `cgp:/e/dark-uncertainty/calculators/total-facets-count.md` |
| `total-blank-facets` | `cgp:/e/dark-uncertainty/calculators/total-blank-facets.md` |
| `facet-occupancy` | `cgp:/e/dark-uncertainty/calculators/facet-occupancy.md` |
| `facet-cardinality-difference` | `cgp:/e/dark-uncertainty/calculators/facet-cardinality-difference.md` |
| `facet-symmetric-difference` | `cgp:/e/dark-uncertainty/calculators/facet-symmetric-difference.md` |
| `spike-cardinality-difference` | `cgp:/e/dark-uncertainty/calculators/spike-cardinality-difference.md` |
| `spike-symmetric-difference` | `cgp:/e/dark-uncertainty/calculators/spike-symmetric-difference.md` |

Each calculator file follows the same shape:

---

*With the objects defined above, the rest of this notebook computes on them*

---

# Implementing a Single Observatron in Sidereal Navigation Space

### A foundation, and a gauge

*Ron Itelman, W3C Context Graph CG. A runnable foundation to hand to mathematicians.*

This notebook defines a minimal, runnable foundation and is explicit about what it claims and what it hands off. It is **not new mathematics**. It is a **gauge** in the instrument sense: a thing that produces consistent, comparable readings at decision boundaries, so that mathematicians can map those readings into whatever spaces are appropriate (category theory at the single-observatron level; complexity theory at the field level; possibly others — ultrametric, Finsler — that I neither claim nor need to know).

What I claim: the gauge, and the sidereal frame it reads in. What I hand off: the spaces, and whether the frame carries deeper structure.

A note on language, stated up front so it is not mistaken: I use **gauge** in the *instrument* sense (a thing that measures). Whether the frame also carries **gauge structure** in the physics sense (local symmetry, a connection, curvature) is an open question I pose to the mathematician below — not a claim I make.

## The frame: sidereal navigation space

An **observatron** puts a mathematical boundary around a decision `if(<condition>) then {branch}`. It is an eyeball on the boundary: data crosses into it from the interior (the real computation, where the formula evaluates) out into an **imaginary navigation space** — imaginary in the sense imaginary numbers are: a constructed coordinate space that lets real operations be charted somewhere they otherwise have no place to sit.

The field of observatrons is navigated like the night sky. **Sidereal navigation**: there is no global, God's-eye view, and none is needed. You **choose your referent points** — a constellation of observatrons visible from your perspective — and navigate relative to them. Absolute position does not matter. What matters is that there is an addressable coordinate system, and that you may pick which references to navigate by.

This is the load-bearing property, and the reason the frame is **not** a sphere, hypersphere, or any fixed shape: a sidereal frame is honest about having **no global vantage**. Navigation happens from inside, by chosen local references. (This local-frames-with-no-global-view property is also why the physics-gauge question below is worth asking — it is the same shape as a situation with local frames and transport between them.)

## Everything is addressable: the gauge is self-describing

Observatrons, components, and the **four-facet meta-schema itself** are all named by URLs in one namespace (`cgp:/...`). The objects being measured, the instruments doing the measuring, and the definitions of the measurements all live at addresses of the same kind.

- An observatron has an address (e.g. `cgp:/s/0/o/0`).
- Each facet definition has an address (`cgp:/r/...`).
- Each dark-uncertainty calculator has an address (`cgp:/e/dark-uncertainty/calculators/...`).

So the gauge is **self-describing**: how a number is computed is itself a referenceable object in the same space as the things the number is about. This is a concrete design property, not a metaphor.

## The spike and its four facets — data is the base

When data crosses the boundary, the observatron mints a **spike**, owned by the observatron and addressed under it (`[observatron].spikes` — on the observatron, not on the boundary circle). A spike is a tetrahedron with four facets:

- **`/data`** — the base. What crossed. **Present by construction**: a spike exists *because* data crossed, so data is always there. It is the fourth facet and the anchor, not the dark one.
- **`/meaning`**, **`/structure`**, **`/context`** — the other three. These may be present-and-filled, present-and-empty, or absent.

**Dark uncertainty is not a facet.** It is a *calculation over the frame*: count how many of the three non-data facets are blank. Data is given; the dark is measured over what else did or did not come across with it.

The **meaning** and **structure** facets are how two observatrons establish whether they point at the *same referent*. The gauge compares them as pointers — do these two point at the same thing? — and makes **no claim** that either gloss is true. This is the sidereal act: fixing position by relative bearing to chosen reference points, claiming nothing about the stars themselves.

## Tick 1 — `total-facets-count`
The smallest computation: one spike in, one integer out. How many of the four canonical facets are present?

## Core Concepts

**Dark Uncertainty.** `U = B / (3 · |S|)` — where `|S|` is the number of spikes
observed and `B` is the count of blank gauge facets across them (each spike has
3 gauge facets: `/meaning`, `/structure`, `/context`). `U ∈ [0,1]`. `U = 0` means
every gauge facet is filled; `U = 1` means none are. `/data` is excluded — by the
Coupling Rule it is always present, so counting it would credit a guarantee as work.


**Reference URLs:** `cgp:/r/meta/coupling-rule.md`, `cgp:/r/meta/cgp-id-stamping.md`

**Coupling Rule**

An entry on the Context Graph — a spike or an observatron — exists **if and
only if** a payload has crossed a boundary to bring it into being.

- For a **spike**: a datum crossing the observatron's watched boundary mints the spike.
- For an **observatron**: instantiation parameters crossing from the host (e.g. an HTML element's attributes) mint the observatron.

When an entry exists, **all four facets are present.** There is no state in which
an entry exists with `null` facets — if the facets would be null, the entry does
not exist. This is why `/data` is never counted toward the dark-fraction's
verified facets: by the coupling rule `/data` is present whenever the entry is,
so counting it would credit a guarantee as if it were interpretive work. Only
`/meaning`, `/structure`, and `/context` carry darkness.

**cgp-id Stamping**

Any HTML element bearing a `cgp-id` attribute **is** a CGP element. The runtime
queries the DOM for `[cgp-id]`, reads each element's `cgp-id` URL to determine
what kind of component it is, and instantiates the corresponding observatron.

- The element's **tag is the implementer's choice** (`<div>`, `<span>`, `<canvas>`, …) — CGP identity is carried entirely by the `cgp-id` attribute, not the tag name. The protocol is tag-agnostic.
- The URL in `cgp-id` is the **canonical name** for the component. No separate registration, no custom-element definition, no naming convention to translate. The URL points to the component's reference file (e.g. `cgp:/r/components/html/forms/textarea.md`); whatever lives at that URL is what the element is.

```python
FACETS = ('/data', '/meaning', '/structure', '/context')   # data is the base; the four canonical facets

def total_facets_count(spike: dict) -> int:
    """Count how many of the four canonical facets are present (the key exists)."""
    return sum(1 for f in FACETS if f in spike)

spike = {
    '/data':      {'value': '03/05/2026'},                 # the base: what crossed
    '/meaning':   {'key': [], 'value': []},                # present, empty
    '/structure': {'key': [], 'value': []},                # present, empty
    '/context':   {'anchor': [], 'source': [], 'channel': [], 'timestamp': [], 'key': [], 'value': []},
}
print('facets present:', [f for f in FACETS if f in spike])
print('total-facets-count =', total_facets_count(spike))
assert total_facets_count(spike) == 4
print('PASS')

```


**Output:**
```
facets present: ['/data', '/meaning', '/structure', '/context']
total-facets-count = 4
PASS

```

## Tick 2 — `dark-count` (the first dark-uncertainty calculation)

Dark uncertainty over a single spike: of the three non-data facets, how many are **blank**? Data is the base and excluded — it is present by construction. A facet is blank if absent, or present-but-empty.

This is the first measurement that is *about the dark*. It is a count, nothing more — no claim about meaning, truth, or cost. Just: how much of the frame's meaning/structure/context did not come across with the data.

```python
NON_DATA = ('/meaning', '/structure', '/context')   # the three; data is the base, excluded

def is_blank(facet_value) -> bool:
    """Blank if absent (None) or present-but-empty."""
    if facet_value is None:
        return True
    if isinstance(facet_value, dict):
        return all((isinstance(v, list) and len(v) == 0) for v in facet_value.values()) if facet_value else True
    return False

def dark_count(spike: dict) -> int:
    """Of the three non-data facets, how many are blank? Range 0..3."""
    return sum(1 for f in NON_DATA if is_blank(spike.get(f)))

print('dark-count =', dark_count(spike), 'of 3 non-data facets blank')
assert dark_count(spike) == 3

spike2 = {
    '/data':      {'value': '03/05/2026'},
    '/meaning':   {'key': ['format'], 'value': ['MM/DD/YYYY']},
    '/structure': {'key': ['regex'], 'value': ['^[0-9]{2}/[0-9]{2}/[0-9]{4}$']},
    '/context':   {'anchor': [], 'source': [], 'channel': [], 'timestamp': [], 'key': [], 'value': []},
}
print('dark-count (richer spike) =', dark_count(spike2), 'of 3 non-data facets blank')
assert dark_count(spike2) == 1
print('PASS: dark-count measures blanks among the three non-data facets. Data is the base.')

```


**Output:**
```
dark-count = 3 of 3 non-data facets blank
dark-count (richer spike) = 1 of 3 non-data facets blank
PASS: dark-count measures blanks among the three non-data facets. Data is the base.

```

## Tick 3 — dark over a sidereal field (choose your referent points)

The sidereal act: dark uncertainty is computed not over one spike but over a **chosen constellation** of observatrons. You pick the referent points; the gauge sums the dark over exactly those. Different perspective, different constellation, different reading — and that is correct, because there is no global view, only the references you choose.

```python
def field_dark(field: dict, referents: list) -> dict:
    """Sum dark-count over a chosen set of observatron addresses (the constellation).
       field: {address: spike}.  referents: which addresses to navigate by."""
    chosen = {a: field[a] for a in referents if a in field}
    per = {a: dark_count(s) for a, s in chosen.items()}
    return {'referents': list(chosen.keys()), 'per_observatron': per, 'total_dark': sum(per.values())}

field = {
    'cgp:/s/0/o/0': spike,    # 3 blank
    'cgp:/s/0/o/1': spike2,   # 1 blank
    'cgp:/s/0/o/2': {'/data': {'value': 'x'},
                     '/meaning': {'key':['x'],'value':['the letter x']},
                     '/structure': {'key':['regex'],'value':['^x$']},
                     '/context': {'anchor':['a'],'source':['s'],'channel':['c'],'timestamp':['t'],'key':['k'],'value':['v']}},  # 0 blank
}

print('constellation {o/0, o/1}:', field_dark(field, ['cgp:/s/0/o/0','cgp:/s/0/o/1']))
print('constellation {o/1, o/2}:', field_dark(field, ['cgp:/s/0/o/1','cgp:/s/0/o/2']))
print()
print('Same field, different chosen referents, different dark reading.')
print('No global view is computed or claimed. You navigate by the stars you pick.')

```


**Output:**
```
constellation {o/0, o/1}: {'referents': ['cgp:/s/0/o/0', 'cgp:/s/0/o/1'], 'per_observatron': {'cgp:/s/0/o/0': 3, 'cgp:/s/0/o/1': 1}, 'total_dark': 4}
constellation {o/1, o/2}: {'referents': ['cgp:/s/0/o/1', 'cgp:/s/0/o/2'], 'per_observatron': {'cgp:/s/0/o/1': 1, 'cgp:/s/0/o/2': 0}, 'total_dark': 1}

Same field, different chosen referents, different dark reading.
No global view is computed or claimed. You navigate by the stars you pick.

```

## Tick 4 — `outcome` (the one variable that makes the data trainable)

One variable, added to a measurement: the **outcome** observed *after* the decision the spike measured. The spike's `dark_count` is a **feature** measured at decision time; `outcome` is a **label** observed afterward. Pairing them turns a measurement stream into labeled data.

Minimal form: `outcome = 1` (fine) or `0` (a problem followed). Nothing more is added here. The one pairing is the whole step — trivial to record now, impossible to recover later if not recorded.

*(Where this points, for later — not built here: `outcome` is the variable a global model would read across the sidereal space to keep it stable as agents navigate context. That is future work; the only thing introduced now is the single variable.)*

```python
def labeled_observation(spike, outcome):
    """One training row: dark_count measured BEFORE (feature) + outcome observed AFTER (label).
       outcome: 1 = fine, 0 = a problem followed."""
    return {'dark_count': dark_count(spike), 'outcome': outcome}

# the dark spike preceded a problem; the lit spike was fine
row_dark = labeled_observation(spike, outcome=0)    # spike: 3 blank
row_lit  = labeled_observation(spike2, outcome=1)   # spike2: 1 blank
print(row_dark)
print(row_lit)
assert row_dark == {'dark_count': 3, 'outcome': 0}
assert row_lit  == {'dark_count': 1, 'outcome': 1}
print()
print('Feature measured before + label observed after = one training row.')
print('A stream of these IS labeled data. The model learns: does dark_count predict outcome?')

```


**Output:**
```
{'dark_count': 3, 'outcome': 0}
{'dark_count': 1, 'outcome': 1}

Feature measured before + label observed after = one training row.
A stream of these IS labeled data. The model learns: does dark_count predict outcome?

```

## Tick 5 — `preference` (promote a resolution to situation scope)

Tick 4 records what happened *after* a spike. This tick records the *resolution itself* and makes it reusable. When a dark facet is lit by a user — e.g. the "yesterday" spike whose `/context` frame was blank, and the user picks one option from a dropdown — that pick can die with the spike, or it can be **promoted to a preference** so the next matching spike arrives pre-lit.

Two operations:

- `save_preference` — promote a lit resolution to a **situation-scoped, provenanced** record. The scope key is the situation, addressed in the cgp:/who/ namespace (e.g. cgp:/who/jon_at_citi.com). Being a cgp: path, it obeys the path character rules — which is why the email's @ is encoded as _at_: identity values are escaped to legal path characters, not carried raw.

- `resolve_from_preferences` — if a preference matches the situation, **pre-light** the blank facet and mark it `resolved_by='preference'` with a `resolved_from` trail back to the original human source. A preference-resolved spike is auditable, not a re-guess.

Two guardrails fall out of scoping the key to a situation:

1. **No leak.** A preference saved for one situation does not resolve another. This is the failure the protocol exists to prevent — one user's "yesterday = New York" silently answering another user's spike — and scoping is what blocks it.
2. **Still in the outcome loop.** A preference-resolved spike still pairs with an `outcome` (Tick 4), so a preference that goes stale (the situation drifts) shows up as outcomes turning bad. The preference is itself a thing the field can evaluate.

```python
import datetime

def save_preference(store, scope_key, facet_path, resolution, source, options):
    """Promote a spike-scoped resolution to a SITUATION-scoped preference.
       resolution : the {slot: value} that lit the facet, e.g. {'anchor': 'America/New_York'}
       source     : who made the call -> provenance (e.g. 'jon_at_citi.com')
       options    : the bounded answer space the choice was drawn from (the dropdown enum)
       The choice is recorded as one explicit, bounded, timestamped human act."""
    store.setdefault(scope_key, {})[facet_path] = {
        'resolution': dict(resolution),
        'source':     source,
        'options':    list(options),     # the legal resolutions; the pick was not free-form
        'timestamp':  datetime.datetime.now(datetime.timezone.utc).isoformat(),
    }
    return store

def resolve_from_preferences(spike, scope_key, facet_path, store):
    """If a matching preference exists for this situation, PRE-LIGHT the blank facet from it.
       Marks resolved_by='preference' and carries resolved_from -> the original human source,
       so a preference-resolved spike is auditable, not a silent re-guess.
       Returns (spike, hit)."""
    pref = store.get(scope_key, {}).get(facet_path)
    if pref is None or not is_blank(spike.get(facet_path)):
        return spike, False              # no preference, or facet already lit
    facet = dict(spike.get(facet_path) or {})
    for slot, val in pref['resolution'].items():
        facet[slot] = [val]              # light the slot
    facet['resolved_by']   = ['preference']
    facet['resolved_from'] = [pref['source']]   # trail back to the human who first decided
    spike = dict(spike); spike[facet_path] = facet
    return spike, True

# ---- demo: the "yesterday" spike, dark on /context (which frame anchors the day?) ----
def fresh_yesterday_spike():
    return {
        '/data':      {'value': 'yesterday'},
        '/meaning':   {'key': ['relative_day'], 'value': ['the day before the reference day']},
        '/structure': {'key': ['enum'], 'value': [['Asia/Singapore', 'America/New_York', 'UTC']]},  # bounded answer space
        '/context':   {'anchor': [], 'source': [], 'channel': [], 'timestamp': [], 'key': [], 'value': []},  # WHICH frame? blank
    }

store = {}
USER = 'cgp:/who/jon_at_citi.com'

# 1) before any preference exists: nothing to apply, the spike stays dark
s1 = fresh_yesterday_spike()
s1, hit1 = resolve_from_preferences(s1, USER, '/context', store)
print('1) cold start     -> hit:', hit1, '| dark_count:', dark_count(s1))
assert hit1 is False and dark_count(s1) == 1

# 2) user clicks the dropdown, choosing one of the enumerated options -> save as a preference
save_preference(store, USER, '/context',
                resolution={'anchor': 'America/New_York'},
                source=USER,
                options=['Asia/Singapore', 'America/New_York', 'UTC'])
print('2) preference saved for', USER)

# 3) a NEW yesterday spike for the SAME situation arrives -> pre-lit from the preference
s3 = fresh_yesterday_spike()
s3, hit3 = resolve_from_preferences(s3, USER, '/context', store)
print('3) same situation -> hit:', hit3, '| dark_count:', dark_count(s3),
      '| resolved_by:', s3['/context']['resolved_by'], '| from:', s3['/context']['resolved_from'])
assert hit3 is True and dark_count(s3) == 0
assert s3['/context']['anchor'] == ['America/New_York']
assert s3['/context']['resolved_by'] == ['preference']

# 4) the preference does NOT leak to a different situation (different user stays dark)
OTHER = 'cgp:/who/maria_at_bank.sg'
s4 = fresh_yesterday_spike()
s4, hit4 = resolve_from_preferences(s4, OTHER, '/context', store)
print('4) other situation-> hit:', hit4, '| dark_count:', dark_count(s4), '(no leak)')
assert hit4 is False and dark_count(s4) == 1

# 5) a preference-resolved spike still enters the outcome loop, so the preference itself is auditable
row = labeled_observation(s3, outcome=1)
print('5) preference-resolved spike -> training row:', row)
assert row == {'dark_count': 0, 'outcome': 1}

print()
print('PASS: a resolution is promoted to a situation-scoped, provenanced preference;')
print('      matching spikes are pre-lit (with a trail), it does not leak across situations,')
print('      and preference-resolved spikes stay in the outcome loop.')
```


**Output:**
```
1) cold start     -> hit: False | dark_count: 1
2) preference saved for cgp:/who/jon_at_citi.com
3) same situation -> hit: True | dark_count: 0 | resolved_by: ['preference'] | from: ['cgp:/who/jon_at_citi.com']
4) other situation-> hit: False | dark_count: 1 (no leak)
5) preference-resolved spike -> training row: {'dark_count': 0, 'outcome': 1}

PASS: a resolution is promoted to a situation-scoped, provenanced preference;
      matching spikes are pre-lit (with a trail), it does not leak across situations,
      and preference-resolved spikes stay in the outcome loop.

```

```python
import ast

UNDEFINED = None   # shard_count when a slot's answer space was never declared (≠ 0)

def is_blank(v):
    if v is None: return True
    if isinstance(v, dict):
        return all((isinstance(x, list) and len(x)==0) for x in v.values()) if v else True
    if isinstance(v, list): return len(v)==0
    return False

def consulted_names(condition):
    """Names the `if` ACTUALLY consults — parsed from the condition, not assumed.
       Accepts a bare expression ('a and b') or a full statement ('if a and b: foo()').
       Captures dotted chains whole, e.g. 'user.intent.x'."""
    s = condition.strip()
    if s.startswith('if') and s[2:3] in (' ', '('):
        if ':' not in s:               s += ': pass'
        elif s.rstrip().endswith(':'): s += ' pass'
        test = ast.parse(s).body[0].test
    else:
        test = ast.parse(s, mode='eval').body
    names = set()
    class V(ast.NodeVisitor):
        def visit_Attribute(self, n): names.add(ast.unparse(n))
        def visit_Name(self, n):      names.add(n.id)
    V().visit(test)
    return names

def shatter_slots(declared, consulted):
    """declared : {criterion_id: answer_space_list | None}
       consulted: names the condition actually referenced.
       Returns shatter slots (declared-but-not-consulted), each with
       shard_count = |answer_space|, or UNDEFINED if no answer space was declared."""
    consulted = set(consulted)
    out = []
    for cid, answer_space in declared.items():
        if cid not in consulted:
            sc = len(answer_space) if answer_space is not None else UNDEFINED
            out.append({'slot': cid, 'shard_count': sc})
    return out

class ShatterLedger:
    """Put in an arbitrary `if`; per intent frame, declared criteria it did NOT consult
       become shatter slots, each carrying its shard_count (|answer space|, or UNDEFINED).
       The reading is kept PER FRAME (a triple) and never collapsed to a scalar."""
    def __init__(self, frames):
        self.frames = {f: dict(decl) for f, decl in frames.items()}
        self.pile = []   # (condition, frame, slot, shard_count)

    def add(self, condition):
        consulted = consulted_names(condition)
        reading = {}
        for frame, declared in self.frames.items():
            slots = shatter_slots(declared, consulted)
            reading[frame] = slots
            self.pile += [(condition.strip(), frame, s['slot'], s['shard_count']) for s in slots]
        self._report(condition, consulted, reading)
        return reading

    def _report(self, condition, consulted, reading):
        print(f"if: {condition.strip()}")
        print(f"  consulted: {sorted(consulted) or ['—']}")
        for frame, slots in reading.items():
            if slots:
                desc = ", ".join(
                    f"{s['slot']}×{s['shard_count'] if s['shard_count'] is not UNDEFINED else 'undefined'}"
                    for s in slots)
            else:
                desc = "— (no shatter slot)"
            print(f"    {frame:16}: {desc}")
        print()
```

## Observatron System Goal 1: Identify Dark uncertainty
The previous sections have covered Goal 1, however, it is important to state the goal is not resolving what meaning is, but rather, when we use these words, in this context of this task in this workflow, with this HTML element, for this decision communication event propagation in our observatron sidereal constellation navigation network filed: "Are we pointing to the same things, and if so, how can we work together?" The *Decidatron* is that cognitive unit, which has a "Path Bay" approach:

1. Input
2. Decision Unit
3. Output

## Schema, not instance — a `/meaning` matcher as four isomorphic rows

A `/meaning` facet does **not** resolve meaning. It certifies a *shared referent*: given a value `x` and a finite set of candidate referents `M`, it answers **which** referent `x` points at, or that none is shared. That is the gauge — shared pointing, not the thing pointed at.

The schema is the matcher, parametric in `x` and `M`:

$$\mathrm{match}(x, M) = \begin{cases} i & \text{if } x = e(i) \text{ for the enumeration } e:\{0,\dots,n-1\}\to M \\ \bot & \text{if } x \text{ matches no member of } M \end{cases}$$

`⊥` is not an error — it is the third outcome that creates the obligation: *no shared referent fits, so the user must be able to explain.* And offering a finite `M` at all **is** the program-intent — declaring the set is the signal that this facet was deemed important enough to ASK about.



### The four rows

| # | Form | What it is | What it adds over the row above |
|---|---|---|---|
| 1 | **Set** | $M = \{A, B, C\}$ — the bare collection of shared referents. Unordered; only membership is expressible. | — |
| 2 | **Enum** | $M$ **+ a chosen indexing** $e:\{0,1,2\}\to M$. The order is what lets `match` return *which* referent (an index) and makes `⊥` meaningful. | an ordering / index |
| 3 | **JSON Schema** | `{"$schema": "…/2020-12/schema", "enum": [A, B, C]}` — a serialization of the ordered enum. Its verdict is valid/invalid, i.e. the 2-valued indicator $\chi_M$. | a wire encoding |
| 4 | **Instantiation** | $M$ bound to the three concrete referents for `"yesterday"`. | concrete elements |

### What "isomorphic" means here, precisely

What is **preserved** across all four: the same elements, and the same membership verdict on every value. What is **not** identical in richness: JSON Schema's `enum` decides only valid/invalid — exactly $\chi_M \in \{0,1\}$ — whereas `match` returns *which* referent. That index is **recoverable** from the ordering (rows 2–4), so nothing is lost; it simply lives in the order, not the verdict. And the bridge:

$$\bot \;\equiv\; \chi_M = 0 \;\equiv\; \text{JSON Schema "invalid"} \;\equiv\; \text{the ASK branch.}$$

The code cell constructs all four rows, round-trips them, and checks the membership verdict against the **canonical Draft 2020-12 validator** on a battery of inputs (including the two `⊥` cases) — so the JSON Schema row is *verified*, not asserted.

## Observatron System Goal 2: Minimize Dark uncertainty

The `["U"]` layer allows feedback loops to minimize dark uncertainty. This allows for designing that process via an intent map. Judgements, what was the evaluation criteria for *why* a decision was made is important in some instances and not in others. This flexibility is programmable.

intent-user, intent-program, intent-business are the core ways to define what dark uncertainty is permissible, including judgement of how to route between ASK/ACT/HALT.

In the illustration below (the bubble popping), the pin is a single sql slot that has been intentionally corrupted with dark uncertainty: "Yesterday" could refer to NY time or Singapore, but the user was never asked what their intent was. That single assumption collapsed the ability of the decision unit: Text was converted into SQL obscuring that any evaluation was made or not, whether an actual evaluation was made or not at all.

## Decidatrons: Logic Gates for Dark Judgement

Detecting and managing `Dark Judgement` is done in the following way.

We have a computational account of context collapse: the moment a decision commits to a branch, the criteria that selected it are discarded, and because the mapping is many-to-one they cannot be reconstructed from the output. What we can do is detect and address the gap that loss leaves — measure how much structure went dark and name exactly which facet — even though the lost content itself is gone. And because the collapse is many-to-one, the missing frame provably isn't recoverable from inside the system; so the protocol's only sound response is to ask the party who holds it.

## Context Definition

Context, in this operational sense, is the recoverable shared frame a decision depends on; context loss is that frame becoming unrecoverable at the boundary; and asking is the only sound way to restore it.

For example

```js
// "yesterday" depends on a frame (timezone) that the output cannot recover.
function resolveYesterday(word, frame) {
  if (word === "yesterday") {
    return startOfDay(now(), frame);   // the branch
  }
}

const date = resolveYesterday("yesterday", "America/New_York");
// date === 2026-05-21. The frame ("America/New_York") is GONE.
// Reading `date`, you cannot tell it from the UTC or Singapore answer.
// many-to-one: (yesterday, NY) and (yesterday, UTC) can land on the same date.
// To recover the frame, you must ASK — it is not inside `date`.


```

**It is this moment where a "Judgement Shard" a slice of the structure of bubble stability of the decision model, breaks from Dark Uncertainty.**

| MCP / tools | W3C Context Graph proposal |
|---|---|
| A tool is a **named, addressable capability** an agent can call | A decision is a **named, addressable judgment** a workflow can invoke |
| Tool has a **schema** (inputs/outputs) | Observatron has a **facet schema** (data/meaning/structure/context) |
| Calling a tool **does something in the world** (side effect) | Invoking a decision **emits its criteria on the effect channel** (the payload that would otherwise be dark) |
| Tools are **discoverable** from a registry | Decisions are **discoverable** from your `cgp:/` namespace — you already have the catalog |

> **Any decision that doesn't emit its criteria into a read channel is dark — regardless of whether a human or an LLM made it.**

MCP gave models a standard way to take *actions*. We're proposing a standard way to make *judgments* legible.

A tool call answers "what did it do"; an observatron answers "on what grounds did it decide, and what came across vs. went dark." Those are dual. An agent wired to both could, for any step, say:

> *I did X (tool) because user-intent matched and business-intent went dark (observatron).*

That second clause is precisely the payload the `if` throws away by default — and the effect channel exists to carry it.

# The Decidatron is a control unit

The Decidatron is a control unit in the precise control-theory sense: it sits on the decision's feedback path, reads a measured error signal, and outputs a corrective action — it regulates the decision rather than performing it.

## Signals
In Maxwell's governor, the measured signal is speed and the action is throttle. In the Decidatron, the measured signal is the dark metrics — blank-facet count plus the per-frame shatter slots (each with its shard count) — and the action is `ACT` / `ASK` / `HALT`.

That's the whole definition: a control unit is a function from a measured state to a regulating action, placed in a feedback loop. Your three counts are the measured state.

## Actions
*The governor law* is the action. The patch bay is the loop — IN (the value), DECISION (the `if`), OUT (the branch), and the effect channel underneath is the feedback wire carrying the measurement back so the governor can read it.

## Event Control Unit
In protocol terms — the API/event-bus question — the control unit is the thing the bus routes through, not around.

Concretely: every decision event publishes
its measurement (the counts + which criteria went dark) onto the effect-channel topic; the Decidatron subscribes to that topic, applies `govern(measurement) → {ACT, ASK, HALT}`, and publishes the action back; downstream consumers act on the action, not the raw branch.

So the control unit is an event-bus subscriber whose input is the dark-metric event and whose output is a control verdict — a governor wired into the bus exactly where a Maxwell governor is wired into the steam line. The reason it "must be used to decide" is that it's the only component that reads the feedback signal; bypass it and you're
back to the bare `if` that acts on a dark frame.

## Definitions

*   **Control Unit:** is a bus-resident function from the decision's measured dark-state to a regulating action, sitting on the feedback path so that no branch reaches the output without first being gated by the measurement.
*   **Judgment Shard:** is one term in that measured state; the shard-count is how you quantify it; the categories are how the state space learns; and the Decidatron is
the governor that turns the measurement into `ACT` / `ASK` / `HALT`. That's the architecture, end to end, with every piece a count and one feedback law.

<!-- e/core/metrics/shatter-slot.md -->
<div align="center">
<img src="https://raw.githubusercontent.com/RonItelman/public-content-url/main/new-img-url/figure-2.png" width="600" />
</div>

# shatter-slot & shard

**Reference URL:** `cgp:/e/core/metrics/shatter-slot.md`

A `/e` (essence) file: a **meta schema** for two paired counts. It defines
quantities, not an instance.

## Definitions

> A **shatter slot** is a declared criterion that a decision committed past
> **without consulting it** — the fracture point, the position that should have
> held a resolved value and instead held nothing.
>
> The **shards** are the possible values that slot could have been — its declared
> answer space `M`. The **shard count** of a slot is `|M|`.

A blank facet is *missing data*. A shatter slot is a *skipped judgment*. They are
different failures, and the shatter slot is the one that goes dark when a decision
does not emit its criteria.

## Why this is finite

A decision's possible "reasons" are unbounded, but a decision fires (or should)
by consulting a **declared, finite** set of criteria — written in the intent map,
each criterion carrying its own declared answer space. A shatter slot is a
criterion *declared but not consulted*; its shard count is the size of the answer
space *declared for it*. Declaration is what makes both counts finite.

## The metric

- `shatter_slots(frame) = { c declared in frame : c was not consulted }`

- `shard_count(slot)    = |M_slot|`        (the size of the slot's declared answer space)

- `= UNDEFINED`        if the slot declared no answer space

`shard_count` is **UNDEFINED, not zero**, when the answer space was never
declared. "We knew the options and skipped" and "we never enumerated the options"
are different states with different remediations; the metric keeps them apart.

## Counted per intent frame

Each decision carries three intent frames — **user**, **program**, **business** —
and each is an independent surface where a shatter slot can open. The reading is a
**triple**, one entry per frame, and is **never summed to a scalar**: the value is
*which* frame shattered, because that is what routes the response
(`ASK` / `ACT` / `HALT`).

## The pile (audit trail)

The count is the headline; the **pile** is the evidence — a list of
`(condition, frame, slot, shard_count)` rows, so you can point at exactly which
decision shattered which slot, in which frame, across how many possible values.

## Reference implementation

The runnable, tested `ShatterLedger` (with `consulted_names`, `shatter_slots`,
`is_blank`) is defined in the code cell above. Tested: `yesterday` declared across
three frames (user `{NY,Singapore}`, program `{MDY,DMY}`, business undeclared) and
consulted by none yields shatter slots of shard count 2, 2, and UNDEFINED
respectively; consulting a frame's criterion removes its shatter slot; dotted
names like `user.tz.frame` parse as whole references; the reading stays a per-frame
triple.

```python
# "yesterday" declared across the three intent frames, each with its own answer space.
# (business-intent declares a slot but NO answer space -> shard_count UNDEFINED, not 0.)
frames = {
    'user-intent':     {'tz_frame':         ['NY', 'Singapore']},   # width 2
    'program-intent':  {'date_rule':        ['MDY', 'DMY']},        # width 2
    'business-intent': {'trading_calendar': None},                  # answer space UNDECLARED
}
led = ShatterLedger(frames)

# bare collapse: the `if` consults none of the declared criteria -> all three frames shatter
led.add("if yesterday: show_trades()")

# consult the program rule -> program-intent no longer shatters; user & business still do
led.add("if date_rule == 'MDY': show_trades()")
```


**Output:**
```
if: if yesterday: show_trades()
  consulted: ['yesterday']
    user-intent     : tz_frame×2
    program-intent  : date_rule×2
    business-intent : trading_calendar×undefined

if: if date_rule == 'MDY': show_trades()
  consulted: ['date_rule']
    user-intent     : tz_frame×2
    program-intent  : — (no shatter slot)
    business-intent : trading_calendar×undefined


```


**Output:**
```
{'user-intent': [{'slot': 'tz_frame', 'shard_count': 2}],
 'program-intent': [],
 'business-intent': [{'slot': 'trading_calendar', 'shard_count': None}]}
```

```python
# the pile is the audit trail: (condition, frame, slot, shard_count)
print("PILE (condition, frame, slot, shard_count):")
for row in led.pile:
    print("  ", row)

# the reading is a per-frame triple, never a scalar sum; UNDEFINED is not zero
last = led.add("if unrelated_flag: show_trades()")
assert set(last.keys()) == {'user-intent', 'program-intent', 'business-intent'}
assert last['business-intent'][0]['shard_count'] is None        # UNDEFINED, not 0
assert last['user-intent'][0]['shard_count'] == 2               # |{NY, Singapore}|
print("\nPASS: per-frame triple; shard_count = |answer space|; UNDEFINED != 0.")
```


**Output:**
```
PILE (condition, frame, slot, shard_count):
   ('if yesterday: show_trades()', 'user-intent', 'tz_frame', 2)
   ('if yesterday: show_trades()', 'program-intent', 'date_rule', 2)
   ('if yesterday: show_trades()', 'business-intent', 'trading_calendar', None)
   ("if date_rule == 'MDY': show_trades()", 'user-intent', 'tz_frame', 2)
   ("if date_rule == 'MDY': show_trades()", 'business-intent', 'trading_calendar', None)
if: if unrelated_flag: show_trades()
  consulted: ['unrelated_flag']
    user-intent     : tz_frame×2
    program-intent  : date_rule×2
    business-intent : trading_calendar×undefined


PASS: per-frame triple; shard_count = |answer space|; UNDEFINED != 0.

```

## Context loss and dark judgment: one collapse, two organs

A decision is a many-to-one map. The `if` takes a frame and a value on the way
in, takes a branch on the way out, and the output carries less information than
the input did. That is not a flaw to be fixed — it is what a decision *is*. The
question is *what* gets dropped, and whether the drop can be recovered.

Two things get dropped at the boundary, and they are the same event applied to
two different parts of the decision.

### Context loss — the collapse on the inputs

The **frame** a decision depended on becomes unrecoverable from the result.
`yesterday` resolves to a date only relative to a frame — a timezone, a
definition of "day" — and once it has collapsed into a single SQL slot, the
frame is gone. The mapping from (frame, value) to result is many-to-one, so it
has no inverse: no amount of reading the output recovers which frame produced
it. The information is not in the system to be computed.

### Dark judgment — the collapse on the criteria

The **why** — the criteria that selected the branch — becomes unrecoverable from
the branch taken. A bare `if (condition) { … }` emits the branch and discards the
condition that chose it. Reading the output tells you *what* was decided, never
*on what grounds*. The criteria are not in the system to be computed.

### Same disease, two organs

| | Context loss | Dark judgment |
|---|---|---|
| Collapses the decision's… | **inputs** (the frame) | **criteria** (the why) |
| Lost quantity | which frame the value was read against | why this branch was selected |
| Recoverable from the output? | no — the map is many-to-one | no — the map is many-to-one |
| Recoverable at all only by… | asking the party who holds the frame | asking the party who holds the criteria |

Both are **irreversible, many-to-one collapse at a decision boundary**, applied
to two different things. The frame cannot be inverted out of the result; the why
cannot be inverted out of the branch taken. This is the claim that survives a
hostile question, because it is the same fact that explains why each is
recoverable *only by asking*: in both cases the information provably is not in
the system, so reconstruction requires a source outside it.

### Dark judgment is what conceals context loss

They are not identical, and the difference is the load-bearing part. A decision
can be dark in its judgment with **no** context loss at all — the rock-and-roll
player who knows the rule perfectly but never says it has lost nothing on the
input side; the listener simply never receives the why. That is a dark judgment
with zero context loss, and it is the *acceptable* kind: we do not always need
the reason.

But when context **is** lost, dark judgment is the thing that hides it. The
doctor case is the proof: the system lost the context (the patient's immune
sensitivity) *and* did not emit its criteria — and it is the second failure that
made the first invisible. Had it emitted *"prescribing because I assumed no
immune sensitivity,"* the patient catches the lost frame at the boundary and
restores it. Surfacing the judgment is therefore the very thing that reveals
whether context was lost.

> **Dark judgment is what conceals context loss.** A decision that does not emit
> its criteria cannot reveal whether it also lost its context — so the criteria
> must be emitted onto a read channel (the *effect channel*), and any required
> frame that has gone dark must be recovered by **asking** the party who holds
> it. That is the whole job of the Decidatron: detect the collapse, and route to
> `ASK` rather than let the `if` act on a frame no one supplied.

### Computational Definition of `Judgement Shards` in the Context Graph Protocol

> Judgement Produces a Verdict given two Variables: Counting & Evidence



The count is the headline; the pile is the evidence. `shard_count` tells you *how many* declared criteria a decision committed past without a verdict — one number, exact, bounded by `|C|`. But the ledger also keeps the pile: a list of `(which if, which criterion)` pairs, so you can point at exactly which decision dropped which declared criterion, not just that some were dropped. That turns dark judgment from a metric into an audit trail — the headline says *a decision went dark on two of its three declared criteria*, and the pile says *this `if` dropped `allergen_safe` and `user_frame`*. And the split stays clean: every name a condition consults goes to exactly one place — into `C` it counts as a verdict, outside `C` it falls to the `⊥` ledger as an undeclared reason — so a criterion you anticipated and skipped (a shard) is never confused with a reason you never declared (an unmapped `⊥`).

```python
# Ensure the JSON Schema validator is available wherever this notebook runs.
import importlib.util, sys, subprocess
if importlib.util.find_spec('jsonschema') is None:
    subprocess.run([sys.executable, '-m', 'pip', 'install', '--quiet',
                    '--break-system-packages', 'jsonschema'], check=True)

from typing import Optional, List, Hashable

BOT = None  # ⊥  — "no shared referent"; this is the branch that triggers ASK

# ── Row 1 — SET (unordered): the bare collection of shared /meaning referents ──
#    M = {A, B, C}.  A set has no index; membership is all it can express.

# ── Row 2 — ENUM (set + a chosen indexing): this is where `match` becomes possible ──
#    Picking an order e: {0,…,n−1} → M lets the matcher return WHICH referent.
def match(x: Hashable, enum: List[Hashable]) -> Optional[int]:
    """SCHEMA, parametric in (x, enum). Returns the index i with enum[i] == x,
       or ⊥ if x points at no shared referent. /meaning does not resolve meaning —
       it certifies a shared pointer (an index) or its absence (⊥)."""
    for i, m in enumerate(enum):
        if m == x:            # the equality relation IS part of the gauge; here: exact identity
            return i
    return BOT

def indicator(x, enum) -> int:
    """χ_M(x): 1 if x matches some referent, else 0. This 2-valued verdict is
       exactly what JSON Schema's `enum` decides."""
    return 0 if match(x, enum) is BOT else 1

# ── Row 3 — JSON SCHEMA: a serialization of the ordered enum ──
def as_json_schema(enum):
    return {"$schema": "https://json-schema.org/draft/2020-12/schema", "enum": list(enum)}

# ── Row 4 — INSTANTIATION: bind M to the three concrete referents for "yesterday" ──
M = ["ref://yesterday/A", "ref://yesterday/B", "ref://yesterday/C"]   # |M| = 3 shared referents
schema = as_json_schema(M)

# ============================ the isomorphism, demonstrated ============================
import jsonschema
from jsonschema import Draft202012Validator
validator = Draft202012Validator(schema)

# (a) round-trip preserves the elements AND their order: set→enum→json-schema→back
assert schema["enum"] == M                      # serialization is faithful
assert set(schema["enum"]) == set(M)            # same element set (the unordered view)
assert list(enumerate(schema["enum"])) == list(enumerate(M))   # same indexing (the ordered view)

# (b) the membership verdict agrees across math and canonical JSON Schema tooling,
#     on every input — including the ⊥ / "not a shared referent" case
trials = ["ref://yesterday/A", "ref://yesterday/B", "ref://yesterday/C", "ref://yesterday/D", "yesterday"]
print(f"{'x':24} {'match→index':12} {'χ_M (math)':11} {'jsonschema valid':16}")
for x in trials:
    i   = match(x, M)
    chi = indicator(x, M)
    ok  = validator.is_valid(x)                 # canonical tooling's verdict
    assert (chi == 1) == ok                      # math indicator ≡ JSON Schema validity
    assert (i is BOT) == (not ok)                # ⊥  ≡  "invalid"  ≡  ASK
    print(f"{x:24} {str(i):12} {chi:<11} {str(ok):16}")

# (c) when match succeeds, the index it returns is the same one recoverable from the
#     ordered enum / JSON array — i.e. "which shared referent" is preserved by the iso
for x in M:
    assert match(x, M) == schema["enum"].index(x)

print()
print("|M| =", len(M), "shared referents.")
print("ROW EQUIVALENCE HOLDS:")
print("  set ⊂ enum (enum = set + indexing) ⊂ json-schema (serialized enum) ⊂ instantiation (bound M)")
print("  • same elements, same order across all four")
print("  • χ_M (math)  ≡  JSON Schema `enum` validity   (the 2-valued membership)")
print("  • match → index recoverable from the ordering  (WHICH shared referent)")
print("  • ⊥  ≡  invalid  ≡  the ASK branch / 'user must be able to explain'")

```


**Output:**
```
x                        match→index  χ_M (math)  jsonschema valid
ref://yesterday/A        0            1           True            
ref://yesterday/B        1            1           True            
ref://yesterday/C        2            1           True            
ref://yesterday/D        None         0           False           
yesterday                None         0           False           

|M| = 3 shared referents.
ROW EQUIVALENCE HOLDS:
  set ⊂ enum (enum = set + indexing) ⊂ json-schema (serialized enum) ⊂ instantiation (bound M)
  • same elements, same order across all four
  • χ_M (math)  ≡  JSON Schema `enum` validity   (the 2-valued membership)
  • match → index recoverable from the ordering  (WHICH shared referent)
  • ⊥  ≡  invalid  ≡  the ASK branch / 'user must be able to explain'

```

# Questions

## What this is, and the doors I am handing off

**Claimed here:** a gauge (instrument). It mints spikes when data crosses a boundary, counts present facets, counts blanks among the three non-data facets, and aggregates over a *chosen* constellation in a sidereal frame with no global view. Everything is URL-addressable, so the gauge is self-describing. Every number is an exact count. No advanced mathematics is used or claimed.

**Classical where it appears:** data crossing and discarding its producing context is a function being constant on the fibers of the value. I claim the *synthesis and the gauge

## Applications

A date field is ambiguous: MM/DD/YYYY or DD/MM/YYYY

Yesterday is ambiguous: Relative to Singapore or NY

Rather than big problems, lots of little assumptions, invisible to users can happen in applications. When there are known risks we can design intent maps to catch them and learn from them . This requires feedback loops and other architectural considerations.

## Goal with math

Foundation to build upon between small and large sale network dynamics.

The only commitment Ron Itelman makes is to be able to count every empty facet in an addressable way, from which analytics can be made and this sophistication will be extended by Leo Torres.

```python
# ── prerequisite from the canon (governor): the transition law over states ──
STATES = ('ACT', 'ASK', 'HALT')           # the Decidatron's three control states
# conservatism order: HALT > ASK > ACT  -> govern returns the MEET (most conservative)
RANK = {'ACT': 0, 'ASK': 1, 'HALT': 2}

def govern(fired_halt, dark_required):
    """The transition function the canon already defines, restated as a step."""
    if fired_halt:    return 'HALT'
    if dark_required: return 'ASK'
    return 'ACT'

# ============================================================================
# INDRANIL — YOUR FIRST SPEC TEST GOES HERE FOR AUTOMATA
# cgp:/e/automata/decidatron.md   (math FIRST, proven, THEN added to the canon)
#
# Claim to formalize: the Decidatron is a finite-state transition system.
#   states  Q = {ACT, ASK, HALT}
#   input   Σ = the measured dark-vector (fired_halt, dark_required) ∈ {0,1}²
#   δ : Q × Σ → Q   is `govern` (here memoryless: next state ignores current state)
#
# Below is a SPEC TEST, not a proof: it asserts the properties a proof must
# discharge, so the formalization has a runnable target to match.
# ============================================================================

import itertools

INPUTS = list(itertools.product([0, 1], repeat=2))   # Σ : all (fired_halt, dark_required)

# P1 — TOTALITY: δ is defined on every input symbol, and lands in Q.
for fh, dr in INPUTS:
    assert govern(fh, dr) in STATES
print('P1 totality      : δ defined on all', len(INPUTS), 'symbols, image ⊆ Q  ✓')

# P2 — DETERMINISM: δ is a function (same symbol -> same state, every time).
for fh, dr in INPUTS:
    assert govern(fh, dr) == govern(fh, dr)
print('P2 determinism   : δ single-valued  ✓')

# P3 — MEET / CONSERVATISM: δ returns the most conservative state any active leg forces.
#   halt leg active -> at least HALT ; dark leg active -> at least ASK ; else ACT.
def expected_meet(fh, dr):
    floors = [RANK['ACT']]
    if dr: floors.append(RANK['ASK'])
    if fh: floors.append(RANK['HALT'])
    top = max(floors)
    return next(s for s, r in RANK.items() if r == top)
for fh, dr in INPUTS:
    assert govern(fh, dr) == expected_meet(fh, dr)
print('P3 meet/order    : δ = most-conservative active leg (HALT>ASK>ACT)  ✓')

# P4 — HALT ABSORBS: once a halt leg fires, no other input lifts it off HALT.
for dr in (0, 1):
    assert govern(1, dr) == 'HALT'
print('P4 halt absorbing: fired_halt=1 ⇒ HALT regardless of dark_required  ✓')

# Full transition table (the thing Indranil formalizes / an automata tool ingests):
print('\nδ transition table  (fired_halt, dark_required) -> state')
for fh, dr in INPUTS:
    print(f'  ({fh},{dr}) -> {govern(fh, dr)}')

print('\nSPEC TEST PASSES — these are the obligations the /e/automata proof must discharge.')
print('When the math proves P1–P4, the extension is admitted to the canon.')
```


**Output:**
```
P1 totality      : δ defined on all 4 symbols, image ⊆ Q  ✓
P2 determinism   : δ single-valued  ✓
P3 meet/order    : δ = most-conservative active leg (HALT>ASK>ACT)  ✓
P4 halt absorbing: fired_halt=1 ⇒ HALT regardless of dark_required  ✓

δ transition table  (fired_halt, dark_required) -> state
  (0,0) -> ACT
  (0,1) -> ASK
  (1,0) -> HALT
  (1,1) -> HALT

SPEC TEST PASSES — these are the obligations the /e/automata proof must discharge.
When the math proves P1–P4, the extension is admitted to the canon.

```

## Shatter slots across the three intent frames

A single decision carries three intent frames — **user**, **program**, and
**business** — and each is a surface where a *shatter slot* can open. A shatter
slot is a position that should hold a resolved value and instead holds nothing;
the **shards** are the values it could have been. The same word can shatter
differently in each frame, because each frame is asking a different question of
it. Take `yesterday`:

| Intent frame | The shatter slot asks… | Shards (the possible values) |
|---|---|---|
| **user-intent** | which timezone did the person mean? | `{NY, Singapore}` |
| **program-intent** | which date-parsing rule should run? | `{MDY, DMY}` |
| **business-intent** | which book's trading-day definition applies? | `{desk-A calendar, desk-B calendar}` |

One input, three independent fractures.

### The frame is what routes the response

Knowing *that* a decision went dark is not enough; the governor needs to know
*on whose intent*, because the remediation differs by frame:

- a shatter slot in **user-intent**, where user-intent is **required** → **ASK**
  (cannot proceed without the person)
- a shatter slot in **program-intent**, where program darkness is **permitted**
  → noted, but **ACT** may still be allowed
- a shatter slot in **business-intent**, **required**, with a hard rule → can
  force **HALT**

So the shatter count is a small **matrix**, not a scalar: for each decision, *per
intent frame*, did a slot shatter, and into how many shards. That distinction —
ask the user, fix the program rule, escalate to the business owner — is exactly
what the per-frame breakdown gives you and a single total throws away.

### What gets reported

- **Facets total / filled** — unchanged: the four-facet darkness count.
- **Shatter slots** — counted **per intent frame** (user / program / business).
  A decision may have one (user only), two, or all three.
- **Shard count** — per shatter slot, i.e. per frame: `|M|`, the size of that
  frame's declared answer space.

The honesty rule carries through one level in: a frame has a *defined* shard
count only if **that frame declared its answer space**. user-intent may declare
`{NY, Singapore}` (shard count 2) while business-intent declared nothing — a
shatter slot is present, but its shard count is **undefined, not zero**. "We know
what the user could have meant but never enumerated what the business rule could
have been" is a real and worse-shaped finding than "we knew the two options and
skipped."

### One thing to pin, because three frames invites the mistake

The three intent frames are **independent surfaces, not a sum.** Do not collapse
them into "total shatter slots = 3" — that discards the one thing the governor
needs: *which* frame shattered. Keep the per-frame triple, e.g.

(user: 1 slot × width 2,  program: 1 slot × width 2,  business: 1 slot × undefined)

not a single number. Per frame, the shatter/shard reading is what turns the
darkness tally into a **routing signal** — ASK vs ACT vs HALT — rather than a
flat count of how dark a decision was.

### Why the three measures together say something a single decision can't say alone

The four facets, the shatter slots, and the shard counts measure three different
things, and the value is in how they compose — not in any one of them.

The **facet count** (total and filled) measures *how much of what crossed the
boundary was specified*. It is a property of the data: a fact arrived with some
of its meaning, structure, and context attached and some left blank. This tells
you the input was incomplete, but not whether that incompleteness mattered to any
decision.

The **shatter slot** measures *where a decision was supposed to consult something
and didn't*. It is a property of the judgment, not the data: it exists only
relative to a declared set of criteria, and it marks the exact point where the
decision committed past a question it was meant to resolve. A blank facet is data
that's missing; a shatter slot is a *judgment that was skipped*. Those are
different failures, and most of the time only the first is visible — the second
is precisely the thing that goes dark when a decision doesn't emit its criteria.

The **shard count** (`|M|`, per slot) measures *how much was at stake in that one
skip*. A slot that fractured across two possible values lost less than one that
fractured across fifty. It is the size of the space the decision quietly chose
within without choosing. And its honest edge — *undefined* when no answer space
was declared — distinguishes "we knew the options and skipped" from "we never
even enumerated the options," which are different states with different
remediations.

Composed, and split across the three intent frames, these stop being a darkness
tally and become an account of *a decision's relationship to its own context*.
The facets say what the decision was working with. The shatter slots say which
judgments it declared but did not make. The shard counts say how much each of
those un-made judgments could have changed the answer. And the per-frame split
says *whose* context was lost — the `user`'s, the `program`'s, or the `business`'s —
which is what determines whether the right response is to ask, to proceed, or to
stop. None of this claims the decision was wrong; it claims only that the grounds
are now legible — that you can see, after the fact and in a single trace, exactly
which questions a decision answered, which it skipped, how much each skip ranged
over, and on whose intent. That legibility is the whole thing. A bare decision
discards all four of these the moment it commits; carrying them is the difference
between a system that can account for its judgments and one that cannot.

# Beyond Phase 1 — the trust hypothesis (horizon, not yet grounded)

> The cells above are specification: defined, runnable, conflict-checked. This
> one is different in kind. It states where the work aims, not what it has
> proven. Read it in that register — every claim here is a hypothesis to be
> grounded later, not a count that already holds.

To reason about an organization **holistically** — its workflows, its processes,
its compounding steps and feedback loops — you need a *gauge*: a shared frame
that lets information flow between its parts the way it flows in music, where one
player's signal reaches another only because they share a key and a tempo. A
decision in isolation can be correct; a decision in a chain is only legible to
the steps downstream if the frame travels with it.

We propose that **if parties can agree on such a gauge, trust becomes
measurable.** Not trust as sentiment — trust as a quantity: the degree to which
a node's decisions leave their grounds recoverable to the nodes that depend on
them. A node you can audit is a node you can trust; a node whose decisions go
dark is one you cannot.

The instrument we aim to measure trust dynamics with is the **judgment shard**:
the loss, at a decision boundary, of the conditional-evaluation information and
the context that lived *outside* the communicated variable. Where dark-count
measures the gaps in what crossed, the shard measures the gaps in *why* — and
tracking shards over time, across a chain of decisions, is how we propose to
watch trust rise and fall rather than merely assert it.

A clarification that keeps faith with the rest of this document: this is **not** a
global, god's-eye measurement. Consistent with the sidereal frame of Tick 3,
trust dynamics are visible only by *composing many local readings* — never from
an outside vantage. A propagation that no single node can see locally may become
visible when local shard-readings are composed across the chain; that
composition, and whether such propagation can be anticipated, is the open
question we hand forward.

To build the vocabulary and structure this requires, **Leo Torres** (complexity
science and semantics) will help formalize the problem space — the proper names,
types, and laws that turn "trust" from a word into a defined object over shards
and dark-state.

The further horizon, stated plainly as speculation: that this same gauge could
let us model an organization as nodes *and* systems at once — local interactions,
shifting beliefs and perspectives, knowledge gaps and gains, and the routing of
decisions under dark information. We call that direction **artificial
psychology**. It is a hope, not a result, and nothing in Phase 1 depends on it.

This specification first DRAFT IS HEREBY SUBMITTED TO INDRANIL (SEMANTIC AUTOMATA CO-CHAIR, IBM -> Goal of Working Group participation) FOR REVIEW and AUTHORSHIP OF EXTENSION FOR AUTOMATA SECTION. Other sections will have named co-editors upon public & legal agreements, if any are needed.

# FOR SELF-UPDATING FUNCTIONS

The code below is for managing the notebook itself

```python
from google.colab import _message

nb = _message.blocking_request('get_ipynb', request='', timeout_sec=5)
for i, c in enumerate(nb['ipynb']['cells']):
    head = ("".join(c["source"]).strip().split("\n", 1)[0] or "(empty)")[:60]
    print(f"{i:2} [{c['cell_type'][:4]}] {head}")
```


**Output:**
```
 0 [mark] # The Observatron
 1 [mark] # Step-by-Step Logic of the Context Graph Protocol
 2 [mark] ---
 3 [mark] # Implementing a Single Observatron in Sidereal Navigation S
 4 [code] (empty)
 5 [mark] ## Core Concepts
 6 [code] FACETS = ('/data', '/meaning', '/structure', '/context')   #
 7 [mark] ## Tick 2 — `dark-count` (the first dark-uncertainty calcula
 8 [code] NON_DATA = ('/meaning', '/structure', '/context')   # the th
 9 [mark] ## Tick 3 — dark over a sidereal field (choose your referent
10 [code] def field_dark(field: dict, referents: list) -> dict:
11 [mark] ## Tick 4 — `outcome` (the one variable that makes the data 
12 [code] def labeled_observation(spike, outcome):
13 [mark] ## Tick 5 — `preference` (promote a resolution to situation 
14 [code] import datetime
15 [code] import ast
16 [mark] ## Observatron System Goal 1: Identify Dark uncertainty
17 [mark] # The Decidatron is a control unit
18 [mark] <!-- e/core/metrics/shatter-slot.md -->
19 [code] # "yesterday" declared across the three intent frames, each 
20 [code] # the pile is the audit trail: (condition, frame, slot, shar
21 [mark] ## Context loss and dark judgment: one collapse, two organs
22 [mark] ### Computational Definition of `Judgement Shards` in the Co
23 [code] # Ensure the JSON Schema validator is available wherever thi
24 [mark] # Questions
25 [code] # ── prerequisite from the canon (governor): the transition 
26 [mark] ## Shatter slots across the three intent frames
27 [mark] ### Why the three measures together say something a single d
28 [mark] # Beyond Phase 1 — the trust hypothesis (horizon, not yet gr
29 [mark] # FOR SELF-UPDATING FUNCTIONS
30 [code] from google.colab import _message

```

# Command Chains

A trigger's `handler` MAY be an **ordered array of chain entries** instead of an opaque payload object. When the runtime matches a trigger whose handler is an array, it runs the **command chain**: each entry's command is resolved and executed in order, and each command's return value is piped to the next command as its input.

## Commands

A command is declared in two parallel files under `cgp:/r/commands/`, keyed by the same tail path (the same extension-swap convention as intents):

| URL | Purpose |
|---|---|
| `cgp:/r/commands/<name>.md` | Prose declaration of the command. |
| `cgp:/r/commands/<name>.js` | The command code. |

A command's code is a single default-exported async function:

```
(value, field, params) → nextValue
```

- **`value`** — the previous command's return value. For the first command in the chain, the initial value supplied by the trigger's declared input (see *Initial value* below).
- **`field`** — a read-only snapshot of canonical state: `{ observatrons: [...], originUrl }`. `originUrl` is the URL of the observatron whose boundary crossing fired the trigger. Commands MUST NOT fetch state through side channels; the field is handed to them by the runner.
- **`params`** — the entry's options object, delivered verbatim (the No-Parsing Rule applies). `{}` for bare entries.
- **`nextValue`** — piped to the next command as its `value`. The shape is opaque to the runner; adjacent commands define their own contract.

The runner does not filter, validate, or transform values. A command that needs no input passes `value` through unchanged. A command that produces nothing new returns `value` unchanged so the chain can continue past it.

## Chain entries: bare or configured

Each entry in the handler array is either a **bare command URI** (string) or a **configured command** (object with exactly two keys, `command` and `params`):

```json
"handler": [
  "cgp:/r/commands/read-headers.md",
  { "command": "cgp:/r/commands/find-match-in-spikes.md",
    "params": { "comparator": "cgp:/r/policies/case-insensitive-exact.md" } },
  "cgp:/r/commands/launch-fiber.md",
  "cgp:/r/commands/compare-facets.md"
]
```

- A bare string entry is equivalent to `{ "command": <string>, "params": {} }`.
- `params` keys are defined by the command, not by the protocol.
- Any `params` value that names a rule — a comparator, a threshold policy, a scope — MUST be a `cgp:/r/policies/<name>.md` URL, so the policy a command ran under is itself a referenceable object. Plain values (numbers, strings, booleans) are permitted for params that do not name rules.

## Policies

A policy is a declared rule at `cgp:/r/policies/<name>.md`. Policies make a command's judgment self-describing: a match, a skip, or a threshold decision is only legible if the rule that produced it is addressable.

**Default string comparison.** The default policy for `/data.value` string matching is `cgp:/r/policies/case-insensitive-exact.md`: trim and case-fold both sides, then strict equality. Any other comparison policy MUST be explicitly declared on the chain entry via `params`. A command performing string matching with no declared comparator MUST behave as if `case-insensitive-exact` were declared.

## Initial value

The trigger declares what the chain's first command receives, via an `input` field on the trigger:

```json
{
  "trigger-url": "cgp:/r/triggers/csv-drop-signal.md",
  "predicates": [ { "type": "event", "event": "cgp:dropzone" } ],
  "input": "csv-headers",
  "handler": [ "..." ]
}
```

The runtime maps each declared input name to an extractor for that trigger type. Currently implemented:

| Input name | Supplied as initial value | Trigger context |
|---|---|---|
| `csv-headers` | Array of trimmed column-header strings from the dropped CSV | drag-and-drop `cgp:dropzone` |

Further input names (e.g., the watched element's current value for textarea triggers) are declared the same way and implemented in the runtime as needed. A trigger whose handler is a chain and whose `input` is undeclared or unimplemented MUST NOT run the chain; this is a declaration error, not a silent empty value.

## Field timing

The field snapshot reflects state as propagated to the page's runtime at dispatch time, via the canonical state subscription. Spikes minted by the same boundary event that fired the trigger MAY or MAY NOT yet be present in the snapshot — the subscription is asynchronous. Chains that must match against their own just-minted spikes are not supported; the contract is **field-state-as-available**: state from before the triggering event, plus whatever has round-tripped through the state pipeline by dispatch time. A chain whose correctness depends on reading its own event's spikes is a design error under this contract.

## Cross-spike scope

Commands that compare spikes operate **cross-spike**, not cross-observatron: the two endpoints of a comparison or a fiber are spikes, which usually belong to different observatrons but need not (one observatron may compare two of its own spikes, e.g. two CSVs dropped on the same component). Any origin-skip or owner-based filtering is a policy of the specific command or chain, declared like any other policy — never an assumption built into the chain mechanism itself.

## ASK Resolution

The protocol does not specify how a question is presented to the party who
holds the frame. It specifies only two things: that the handler doing the
asking is addressable, and what a resolution is when it comes back.

### Handlers MUST be addressable

A handler that gathers a resolution MUST be declared under
`cgp:/r/event-handlers/`, following the same extension-swap convention as
intents and commands:

| URL | Purpose |
|---|---|
| `cgp:/r/event-handlers/<name>.md` | Prose declaration of the handler's behavior. |
| `cgp:/r/event-handlers/<name>.js` | The handler code. |

How the handler asks — popup, dropdown, free text, voice, any UI at all — is
the implementer's choice and is out of scope. The URL is what makes the
asking step itself auditable: a spike resolved by a handler is traceable to
the declared handler that resolved it.

### Resolutions MUST be emitted on the resolution channel

A handler MUST NOT write state directly. It MUST emit the resolution as one
event on:

`cgp:/r/events/ask-resolved.md`

with the payload:

| Field | Holds |
|---|---|
| `anchor` | URL of the spike the answer is about. |
| `facet` | The facet path the answer lights (`/meaning`, `/structure`, or `/context`). |
| `key` | The term being resolved. |
| `value` | The answer, recorded verbatim (No-Parsing Rule). |

State derives the new facet row from the event by replay, like every other
mutation.

A resolution on a two-column facet (`/meaning`, `/structure`) appends one
`key`/`value` row. A resolution on `/context` requires a full six-column row
(`anchor`, `source`, `channel`, `timestamp`, `key`, `value`); in alpha,
implementations MAY support resolutions on two-column facets only and MUST
reject (not partially apply) a `/context` resolution they do not support —
a partial push would corrupt the six parallel arrays.

### A resolution lights exactly one spike

One event, one `anchor`, one facet row. An answer MUST NOT be copied,
propagated, or inferred onto any other spike, however similar its `/data`.
Copying an answer manufactures agreement between parties who were never
asked — the silent failure the gauge exists to detect.

### HALT MUST be witnessed

A halt blocks the in-flight action; it MUST NOT block the record of the
crossing. The spike still mints (Coupling Rule — the datum did cross the
boundary), and the halt MUST be emitted as one event on:

`cgp:/r/events/halted.md`

with the payload:

| Field | Holds |
|---|---|
| `anchor` | URL of the spike whose crossing was blocked. |
| `trigger` | The `trigger-url` that fired. |
| `frame` | Which intent frame the trigger belongs to. |

What the handler does beyond this — error display, escalation, logging —
is the implementer's choice, declared under `cgp:/r/event-handlers/` like
any other handler. A halt that suppresses the crossing's record is
non-conforming: it converts a blocked action into an invisible one, which
is the silent failure the gauge exists to detect.

## TO DO: KNOWLEDGE INTELLIGENCE INTERFACE VIA EVENT BUS / API PAYLOAD

### Operational Research
"/or/business-intent-cognitive-task-cost/<type>" - TBD
"/or/business-intent-cognitive-task-speed/<type>" - TBD

"/or/business-intent-cognitive-task-speed/<type>/human" - TBD
"/or/business-intent-cognitive-task-speed/<type>/human+AI" - TBD
"/or/business-intent-cognitive-task-speed/<type>/AI" - TBD

"/or/business-intent-cognitive-task-cost/<type>/human" - TBD
"/or/business-intent-cognitive-task-cost/<type>/human+AI" - TBD
"/or/business-intent-cognitive-task-cost/<type>/AI" - TBD

### Decisions

"/or/decision-model/type" - TBD
"/or/decision-model/variables" - TBD
"/or/decision-model/ID" - TBD

Thank you!
Ron
