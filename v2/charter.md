# W3C Context Graph Community Group

**Charter Version 2**

Ron Itelman, Chair, W3C Context Graph Community Group — *July 27, 2026*

_Context_ is information that can change how other information is understood, relative to a task and moment in time. Context may itself be factual knowledge. What makes information contextual is the **role it plays in the process of changing interpretation**.

For example, “the temperature is 30 degrees Celsius (86 degrees Fahrenheit)” is an observation. Learning that the measurement was taken outdoors during winter, at a location where temperatures are **normally below freezing**, _changes how that observation is understood_. Context serves the purpose of revealing missing information, "Why is the temperature so different than expected?". The process of answering questions context revealed gains us the knowledge to minimize the uncertainty of our own understanding.

Without additional context, the temperature reading alone does not reveal why it may be surprising or whether there is a problem. **Contextualization** is the process of surfacing, comparing, and applying such information so that knowledge gaps become visible and available for resolution.

Under this broad definition, meaning and structure are contextual dimensions because changes in meaning or structure can change understanding. The Context Graph Protocol makes these dimensions separately engineerable by representing each observed datum through four facets: **data, meaning, structure, and situational context**. 

At a communication boundary, a sender, receiver, or downstream system may interpret the same information differently. A system may also silently fill missing information using local assumptions, conventions, or knowledge that are not shared with the other parties.

The Context Graph Protocol uses URIs as addresses for lightweight reference artifacts. In the minimal reference format, a URI points to a Markdown document. The reference can be created locally, dynamically, or published for shared use. This gives any participating human, agent, or system a common way to ask:

> **Are we pointing to the same reference?**

A participant may also apply a declared comparison, transformation, validation, or business rule when exact reference identity is not sufficient.

The protocol applies to every sender-receiver pairing among humans, agents, and systems:

| SENDER | RECEIVER |
|--------|----------|
| Human  | Human    |
| Human  | Agent    |
| Human  | System   |
| Agent  | Agent    |
| Agent  | Human    |
| Agent  | System   |
| System | System   |
| System | Agent    |
| System | Human    |

The Context Graph Protocol provides a shared, addressable format for making interpretive dependencies visible and engineerable. At each declared boundary, an **Observatron** records what crossed and organizes the resulting observation into the four facets of data, meaning, structure, and context.

This gives every communication event a standard way to expose missing, differing, or aligned information upstream before misunderstanding propagates downstream. The key benefit of the Context Graph Protocol is to make context engineerable and designable at scale, complete with feedback loops at all layers of the technology stack.

The protocol does not require artificial intelligence. The same references, validations, and comparisons can be evaluated by people, deterministic programs, AI systems, or any combination of them.

> **The goal is not to make an AI intelligent enough to guess how an organization’s data fits together. The goal is to reveal how an organization's many disparate systems have missing context, that once filled, minimizes the uncertainty of completing tasks in inefficient ways.**

## Background to Need / Problem

Organizational data is created by federated teams that do not share one representation of meaning, structure, or context. One team may use an ontology, another a data catalog, another a calibration record, another application code, and another local or tribal knowledge.

Requiring a central knowledge engineer to unify all of these sources is often impractical and may remove important local distinctions. The Context Graph Protocol does not replace these local knowledge systems. Instead, it introduces a stable observation envelope through which they can be referenced and compared.

Every observed datum is represented through the same four facets—data, meaning, structure, and context—while each participating party retains local authority over the references it contributes and over whether its own intent has been represented accurately.

The protocol therefore normalizes the **declaration surface**, rather than requiring every organization or team to adopt the same ontology, schema, catalog, or internal knowledge model.

When an upstream process does not expose task-relevant interpretive information, a downstream system may silently substitute its own assumptions. The protocol calls required but unobserved information **Dark Uncertainty**.

Dark Uncertainty becomes measurable when an _Intent Map_ declares a finite set of variables or addresses that are relevant to the current task. The protocol can then record and count which declarations are:

- present and aligned;
- present but different; or
- absent and therefore dark.

Dark Uncertainty is not a claim to measure every unknown that could exist. It is a standard unit of measure of the declared, task-relevant information that was not observable at a particular boundary.

By making those conditions addressable, the protocol enables organizations to engineer contextual experiences, compare independently produced data, minimize unsupported assumptions, and learn over time which contextual distinctions matter for reliable outcomes.

**Important Links**
- To join: [https://www.w3.org/community/context-graph/](https://www.w3.org/community/context-graph/)
- Draft Alpha spec: [Context Graph Protocol Draft v0.1](https://github.com/W3C-Context-Graph-Community-Group/Charter/blob/main/Context-Graph-Protocol-draft-v0.1.md).

## Quick Business Explanation
As businesses adopt AI and generative AI for knowledge work, it is increasingly important to ensure that:

1. An agent has sufficient information about the user’s intent before executing a task
2. Differences in meaning, assumptions, or context can be surfaced and resolved
3. Organizations can learn from previous context-related events rather than resolving the same ambiguity from scratch each time

For example, a banker asks an AI system, “What were my trades yesterday?” The correct interpretation may depend on the banker’s location, the exchange’s timezone, the organization’s reporting calendar, and the intended reference date.

Without a declared reference for the _user-intent_, “yesterday” may refer to different calendar periods in Singapore, London, and New York. The information needed to determine the intended period is context. 

A Context Graph may be instantiated on demand at a system boundary and provides a standard structure for recording, evaluating, and resolving potential contextual misalignment.

## High-Level Technical Overview
A Context Graph is produced by running the processes defined by the protocol. The initial technical model includes four primary components:

1. _Observatron:_ Observes communication events at a defined boundary
2. _Intent Map:_ Defines what communication events may trigger a response by the system
3. _Decidability Gate:_ Applies declared rules to select an Act, Ask, or Halt response
4. _Dark Facets:_ Provides a common structure for recording Data, Meaning, Structure, and Context
5. _Decision Trace_: a durable record of what was interpreted, what was resolved, and how the system responded.
  
Traditional semantic systems can provide rich representations of meaning, but they generally depend on prior agreement about terms, vocabularies, or models. Many non-semantic systems do not provide a standard mechanism for detecting and resolving conflicts in meaning or context.

Both kinds of systems can encounter the same problem at a boundary: the receiving system may interpret information differently from the sending system without either party detecting the difference. The Context Graph Protocol is intended to complement existing approaches by providing a lightweight mechanism for surfacing and responding to potential misalignment in meaning, context, and intent.

## Group Structure
The group organizes its work through topic-specific steering committees. Each committee is led by a Steering Committee Chair responsible for coordinating that committee’s subject area, participation, and deliverables.

“Steering Committee Chair” is an internal leadership title within the Context Graph Community Group. Each Chair is responsible for defined deliverables that support the group’s primary objective: identifying and pursuing the most direct viable path for the Context Graph Protocol to transition into standardization through a W3C Working Group.

### Steering Committee

**Committee Deliverables**

Each Steering Committee has a defined focus that contributes to the collective goals of the group:

- _Semantic Automata:_ Develop an alpha specification and reference implementation for machine-to-machine communication that preserves and exposes relevant system context (semantic attributions). Research and provide directions on the application of formal language and other related techniques to preserve semantic state-space in machine-to-machine communication. 
- _Applied Knowledge:_ Develop standardized, user-centered measures for benchmarking contextual alignment in knowledge systems over time, including confidence, missing information and other dimensions that are relevant for users to calibrate reliance appropriately.
- _Serialization & Specification:_ Develop clear, implementable serialization formats and support high-quality protocol documentation.
- _Business & Finance:_ Provides a real-world business problem and usage scenario, including benchmarks and success criteria.
- _Agentic Engineering:_ Apply a context graph to the full stack to block PII: Back-end (Markdown),front-end (HTML)user input & LLM output.

**Steering Committee Chairs**
- _Semantic Automata:_ Indranil Mukhopadhyay, Principal Architect - Data Systems & Platforms and Quantum Ambassador (Technical), IBM.
- _Applied Knowledge:_ Audrey Depeige, Head of Knowledge Intelligence, Amazon.
- _Agentic Engineering:_ Alex Brown, Sr. Director of Enterprise AI Engineering, Broadridge.
- _Serialization & Specification:_ Juan Cruz Viotti, Founder of SourceMeta and member of the JSON Schema Technical Steering Committee.
- _Business & Finance:_ Ajay Wanchoo, Senior Managing Director, KPMG.

**Group Chair's Deliverables**
- A white paper, authored and edited by the Group Chair, published as a W3C Community Group Report, integrating contributions from the Steering Committees at the Chair's editorial discretion. Participants and committees may separately publish their own materials.
- Preparation material & work with Steering Committee Chairs to move the group to a W3C Working Group status, with the white paper as evidence to provide the W3C and its members.

**Community Group Member Deliverables**
- Participation is open to anyone; W3C membership is not required and there is no fee to join. The group welcomes participants who wish to contribute real-world use cases and context-alignment needs, propose features or specification requirements, and experiment with the alpha Context Graph Protocol specification and reference implementation. Use cases and feature requests are submitted as issues in the group's GitHub repository or on the public mailing list.


## Operations & Processes

### Decision Process

The group will seek to make decisions through consensus.

The Community Group Chair may make routine operational, editorial, scheduling, and committee-management decisions. Material decisions affecting the group’s specifications, deliverables, or governance will be publicly recorded.

When broader participant review is appropriate, the Community Group Chair may issue a Call for Consensus lasting at least 14 calendar days. If no substantive objection is raised, the proposal is adopted by consensus.

If a substantive objection cannot be resolved and a decision is required for the group to continue its work, the Community Group Chair may call a recorded vote. Unless otherwise specified in this Charter, a proposal is approved by a simple majority of votes cast.

### Leadership

Ron Itelman serves as the Founding Chair and current W3C Community Group Chair. The Community Group Chair coordinates the integrated roadmap, Charter, specification work, committee structure, and potential transition of the group’s work to a W3C Working Group.

Steering Committee Chairs are appointed by the Community Group Chair and are responsible for defined subject areas and deliverables. The Community Group Chair may appoint, replace, or leave vacant a Steering Committee Chair position based on the group’s needs, participation, delivery, or alignment with the Charter. Leadership changes will be communicated respectfully and publicly recorded.

The addition, replacement, or removal of a formal W3C Community Group Chair requires a Call for Consensus of the group’s participants. If the matter remains contested, it requires approval by two-thirds of votes cast. A formal Community Group Chair continues to serve until they resign or a change is approved under this process.

### Charter Ratification and Amendments

The Charter ratification process may begin no earlier than the group’s first quarterly meeting.

Following that meeting, the Community Group Chair will provide the proposed Charter to all group participants and open a 14-day review period. Participants may raise substantive objections through the group’s public mailing list or GitHub repository.

If no substantive objection is received, the Charter is ratified by consensus. If an objection cannot be resolved through discussion or revision, the Community Group Chair may call a recorded vote. Ratification requires approval by two-thirds of votes cast.

After ratification, substantive changes to the group’s mission, scope, deliverables, leadership process, decision process, or amendment process will follow the same 14-day review and approval process.

The Community Group Chair may make non-substantive corrections—including typographical, formatting, link, title, and contact-information updates—without a vote. Such changes will be publicly recorded.

### Participation, Contributions, and Licensing
This group operates under the W3C Community and Business Group Process. Anything in this Charter that conflicts with that Process, the Community Contributor License Agreement (CLA), or the Final Specification Agreement (FSA) is void. Participation is open to anyone; W3C membership is not required and there is no fee to join. Substantive contributions to specifications are made only by participants who have agreed to the CLA. All specifications, documents, software, and code artifacts produced by the group are licensed under the W3C Software and Document License. The group conducts its technical work in public, and the W3C Code of Ethics and Professional Conduct applies.

## Notes
This is in a draft state. It is expected to evolve through public contributions, implementation experience, testing, and Community Group decision-making.
