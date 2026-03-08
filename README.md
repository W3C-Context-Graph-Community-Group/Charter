# W3C Context Graphs Community Group Charter

---

## Mission

The mission of the Context Graphs Community Group is to develop specifications, vocabularies, and best practices for representing and resolving contextual misalignment between systems at their boundaries — where global knowledge representations (organizational knowledge bases, ontologies, policies, shared data models) meet local interpretation contexts (user intent, operational setting, execution constraints, domain-specific framing) in decision systems and human–AI workflows.

## Introduction

A database can enforce its own schema. An ontology can define its own terms. An AI model can optimize its own outputs. But none of these systems can know what a consuming system requires, what assumptions a producing system embedded, or whether the meaning of a term as defined in one context matches the meaning expected in another. That information does not exist inside either system. It exists only at the boundary between them — in the relationship between what one system declares and what another system needs.

This is why investments in better data quality, richer ontologies, and more capable AI models — however valuable in their own right — cannot solve the coherence problem. A column in a CSV does not know what the dashboard consuming it requires. A dashboard does not know what the CSV assumed. An AI agent retrieving a financial filing does not know which of 27 tagged revenue definitions matches the analyst's intent, and the analyst does not know the definitions exist. Every component can be individually correct and the composite result can still be wrong, because correctness at the boundary was never evaluated.

The problem is structural: coherence emerges from interaction, not from any participant in the interaction. Therefore the solution must also be structural. It must operate at the boundary, not inside either system. It must define a shared standard for declaring what is required, demonstrating what is known, identifying what is missing, and recording what was decided — at every crossing point, between any two systems, regardless of their internal architecture.

The Context Graphs program addresses this in four layers:

| Layer | Name | Purpose | Key Operations |
|---|---|---|---|
| 0 | **Tensor Substrate** | Converts contextual prerequisites, resolution states, and facet evaluations into a unified mathematical representation for computational analysis | Eigensum computation, Tucker decomposition, tensor factorization of multi-facet uncertainty vectors, dimensionality reduction across boundary-crossing state |
| 1 | **Context Graph** | An auditable, append-only hypergraph log of context events at local and global system boundaries, accessible only through the Context Graph Control Plane | Four-facet evaluation (meaning, structure, data, context); gap decomposition; validation report generation; knowledge graph view; authenticated access control |
| 2 | **Coherence Protocol** | Composes boundary evaluations across systems and governs action at each crossing | Gap propagation through pipelines; resolution trace linking; canonical form reduction (O(N²) → O(N)); Act / Ask / Halt protocol actions; Flag and Trace |
| 3 | **Decision Interface** | Consumes coherence measurements and resolution traces to drive downstream decisions | Facet-indexed uncertainty vector ingestion; decision model integration (threshold, Bayesian, utility, etc.); auditable decision replay; policy parameter application |

## Scope

Many decision and information systems implicitly assume that a shared knowledge model and the local context at the point of interaction are aligned. In practice, this alignment frequently fails: terms carry different meanings across organizational, temporal, or operational boundaries; assumptions embedded in global models do not hold locally; and key context required to interpret state, policy, or meaning is absent, unavailable, or ambiguous at the point of use. These failures are distinct from data quality or optimization problems. They represent a structural interoperability gap in how context is communicated, validated, and resolved across systems.

A Context Graph treats this gap as a first-class, interoperable artifact: a structured representation of the contextual prerequisites required for valid interpretation, their dependencies, and their resolution status. A Context Graph is instantiated on demand at a system boundary, populated during the course of a query or interaction, and produces a resolution trace recording what was checked, what was found, what was ambiguous, and what action was taken.

### In Scope

The Community Group will address the following areas:

#### 1. Context Graph Specification (Single Boundary)

A core data model for expressing contextual prerequisites and resolution state at any individual system boundary. This includes a minimal vocabulary for describing common categories of contextual mismatch across four facets: meaning, structure, data, and context. The context facet encompasses both operational context (temporal, organizational, and environmental conditions at the point of use) and epistemic context (the actor's domain knowledge, assumptions, and capacity to interpret what a system returns). The specification will define the lifecycle of a Context Graph instance — instantiation, population, evaluation, trace production, and teardown — as an ephemeral, on-demand operation.

These instances carry no assumptions about the scale of the systems involved and can be joined, persisted, or kept ephemeral and in memory.

#### 2. Intent Map Specification

A declarative format for expressing coherence requirements at a boundary crossing: what must be checked, what rules apply, what thresholds trigger clarification or halt conditions, and what risk tolerance governs action under uncertainty. Intent Maps may be authored by users, inferred by systems, or composed from both. The specification will define a minimal schema that is format-agnostic (JSON, YAML, or other serializations).

#### 3. Coherence Protocol (Cross-Boundary Composition)

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

#### 6. Coherence Failure Taxonomy for Agentic Systems

A classification of failure modes that arise when autonomous or semi-autonomous agents act on data whose contextual alignment has not been verified. This includes silent misalignment (definitions conflict but pipelines execute without error), semantic drift (meaning shifts between systems or over time without notification), absent context (required prerequisites for valid interpretation were never defined), and cascading incoherence (a coherence failure in one boundary crossing propagates through downstream agent decisions). The taxonomy will define each failure mode, its observable symptoms, its relationship to the four-facet evaluation model, and the protocol actions appropriate to detect or prevent it.

### Out of Scope

The following areas are explicitly excluded from the work of this Community Group:

**Defining ontologies or vocabularies for specific domains.** The Community Group standardizes how systems report what they know and do not know about meaning at a boundary. It does not standardize what meaning is in any particular domain.

**Replacing or competing with existing semantic web standards.** Context Graphs are complementary to RDF, OWL, SKOS, and similar vocabularies. They operate at the pragmatic layer — meaning in use, in context, by a specific actor — not at the semantic layer where meaning is defined by a system.

**Data quality frameworks.** Contextual misalignment is distinct from data quality. A column may be well-formed, well-typed, and complete, yet carry a definition that conflicts with the consuming system's intent. This is the gap the Context Graph addresses.

**Prescribing internal system architecture.** The specification does not require changes to the internal structure of any participating system. A Context Graph is instantiated at the boundary, not inside the systems on either side.

**Specifying runtime execution environments.** The specification defines the data model, vocabulary, and protocol. It does not prescribe how implementations host, execute, or scale Context Graph evaluations.

## Motivating Example

A driver pulls out of a parking lot. The navigation system says turn left. The map is correct. The route is correct. The GPS coordinates are correct. The driver turns left and goes the wrong direction.

The system did not know which direction the driver was facing. Every piece of data was accurate. The road network ontology was sound. The sensors worked. But one missing contextual prerequisite — the driver's orientation relative to the map's frame of reference — turned a correct instruction into a wrong action. The system did not flag the uncertainty. It did not ask. It issued a confident directive based on an incomplete model of the driver's local state. The recovery cost was a U-turn.

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

The Coherence Protocol performs the same factorization for semantic coherence. The canonical form is not a universal dictionary of definitions — that would require all systems to agree on what terms mean, which is neither feasible nor desirable. The canonical form is a shared structure for expressing what is required and what is known at any boundary. Each system publishes its prerequisites and evidence in terms of that shared structure. Resolution traces produced at one boundary are legible at every other boundary without translation. The protocol standardizes the envelope, not the message.

### What this means in practice

An organization with 50 systems exchanging data today manages semantic coherence — to whatever extent it manages it at all — through a combination of tribal knowledge, manual documentation, and bespoke validation scripts. That is point-to-point integration, whether or not it is recognized as such. Adding a 51st system means understanding its interactions with each of the existing 50.

Under the Coherence Protocol, adding that 51st system means defining its prerequisite mappings once, in terms of the shared vocabulary. Every existing resolution trace in the ecosystem is already legible to it. Every boundary evaluation it produces is immediately legible to every other system. The protocol-level integration cost of adding a new system is constant — one adapter — not proportional to ecosystem size.

This is not an analogy to internet protocols. It is the same mathematical structure applied to a different domain. The Internet Protocol proved that connectivity scales only when the interoperability contract is defined at the boundary, not inside the systems on either side. The Coherence Protocol applies that same principle: the interoperability contract for meaning, structure, data, and context must be defined at the boundary, where the gap between systems actually exists.

## Steering Committees

The Community Group organizes its technical and strategic work through steering committees, each responsible for a distinct surface of the specification and its adoption. Committee chairs report to the Community Group Chair and are responsible for soliciting input, coordinating feedback, testing proposals within their domain, and maintaining the interface between their area of expertise and the broader group.

Initial operating expectations for Steering Committee Chairs:

1. One hour for a one-on-one session with the Community Group Chair approximately every six weeks to check alignment.
2. Communicating with general members who wish to participate within their committee.
3. Notifying the Community Group Chair if they are unable or no longer willing to continue in the role.

These expectations may be revised by the Community Group Chair as the group's operational processes develop.

**Coherence Protocol** — Chaired by the Community Group Chair. Owns the core specification for cross-boundary composition: how independent Context Graphs relate, how uncertainty propagates across multiple boundary crossings, and how composite resolution traces are produced. This is the central technical deliverable of the group.

**Syntax & Serialization** — Owns the Intent Map specification and all format-level concerns: how coherence requirements, resolution states, and traces are expressed in concrete serializations (JSON, YAML, and other formats). Ensures the specifications are implementable by developers working in mainstream toolchains without requiring adoption of any single data model.

**Semantic Alignment** — Owns the interface between the Context Graph specification and existing semantic web infrastructure (OWL, RDF, SHACL, SKOS). Ensures that organizations with existing ontologies, knowledge graphs, and constraint languages can express their definitions as inputs to the meaning facet without translation loss. Validates that the specification is compatible with, and does not duplicate, established W3C standards.

**Industry Adoption** — Owns the relationship between the specification and real enterprise problems. Responsible for sourcing use cases from active industry engagements, identifying organizations willing to pilot the protocol, validating that the specification addresses problems practitioners recognize, and building the business case required to advance from Community Group to Working Group status.

**Applied Knowledge** — Owns the bridge between specification, deployment, and measuring benefit to users and organizations.

**Decision Interface** — Owns the specification for how coherence measurements interface with decision models. Defines the contract between the measurement layer (the uncertainty vector produced by a Context Graph evaluation) and any external decision model that consumes it: what inputs the decision model receives, what outputs it must return, and what must be recorded in the resolution trace to ensure the decision is auditable and replayable. Ensures the interface is neutral to the choice of decision framework — threshold-based rules, utility models, Bayesian inference, or other approaches — so that the measurement and decision layers remain independently replaceable.

## Deliverables

### Specifications

The Community Group intends to produce the following Community Group Reports:

1. **Context Graph Data Model** — Core specification for representing contextual prerequisites, resolution state, and the four-facet evaluation model at a single system boundary.

2. **Intent Map Format** — Specification for declaring coherence requirements, risk tolerance, and evaluation rules at a boundary crossing.

3. **Coherence Protocol** — Specification for composing multiple Context Graphs across system boundaries, including uncertainty propagation, cross-boundary alignment detection, and composite resolution traces.

4. **Resolution Trace Format** — Specification for recording and exchanging the decision history of Context Graph evaluations.

5. **Decision Interface Specification** - Specification for the contract between Context Graph coherence measurements and external decision models. Defines the input surface (the facet-indexed uncertainty vector, policy parameters, and boundary metadata), the output surface (a protocol action and optional flags), and the trace requirements for auditable decision replay. The specification is neutral to the choice of decision framework: it standardizes what a decision model receives and what it must return, not how it reasons internally.


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

The group prioritizes iterative development and testable outputs. Decisions will be made through consensus where possible. Where consensus cannot be reached, the Chair may call for a group vote, requiring a simple majority of participants who have expressed a position. The initial Chair is Ron Itelman, as proposer of the Community Group. Additional or successor Chairs may be appointed by consensus or majority vote of the group participants. This charter may be amended by consensus of the group participants. Substantive changes require notice to the group mailing list and a minimum comment period of 14 days before adoption. This charter will be updated as operational processes mature.
