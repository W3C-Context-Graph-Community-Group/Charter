# W3C Context Graph Community Group

**version:** 2

By Ron Itelman, W3C Context Graph Community Group Chair

July 15, 2026

The mission of the Context Graph Community Group is to develop an open specification for the Context Graph Protocol: a protocol for creating structured, addressable records of contextual alignment and misalignment at communication boundaries.

Context is defined as information that changes how a receiving party interprets what has already been communicated or known. Context may be missing from an interaction, held by only one party, or understood differently by the parties. Common expressions such as “Let me give you context” and “You are taking that out of context” reflect this role.

A Context Graph enables systems and organizations to observe communication events, identify information that may be insufficient for a receiving party to interpret what was communicated, and support actions to resolve that insufficiency using a common, scalable format.

The protocol is intended to support human-to-human, human-to-agent, and agent-to-agent interactions. When the parties to an interaction do not share sufficient understanding of the information being communicated, downstream decisions and actions may carry an increased risk of error.

To join: [https://www.w3.org/community/context-graph/](https://www.w3.org/community/context-graph/)

## Quick Business Explanation
As businesses adopt AI and generative AI for knowledge work, it is increasingly important to ensure that:

1. An agent has sufficient information about the user’s intent before executing a task
2. Differences in meaning, assumptions, or context can be surfaced and resolved
3. Organizations can learn from previous context-related events rather than resolving the same ambiguity from scratch each time

For example, a banker asks an AI system, “What were my trades yesterday?” The correct interpretation may depend on the banker’s location, the exchange’s timezone, the organization’s reporting calendar, and the intended reference date.

Without a declared reference frame, “yesterday” may refer to different calendar periods in Singapore, London, and New York. The information needed to determine the intended period is context. 

A Context Graph may be instantiated on demand at a system boundary and provides a standard structure for recording, evaluating, and resolving potential contextual misalignment.

## High-Level Technical Overview
A Context Graph is produced by running the processes defined by the protocol. The initial technical model includes four primary components:

1. _Observatron:_ Observes communication events at a defined boundary
2. _Intent Map:_ Defines what communication events may trigger a response by the system
3. _Decidability Gate:_ Applies declared rules to select an Act, Ask, or Halt response
4. _Four Facets:_ Provides a common structure for recording Data, Meaning, Structure, and Context
  
Traditional semantic systems can provide rich representations of meaning, but they generally depend on prior agreement about terms, vocabularies, or models. Many non-semantic systems do not provide a standard mechanism for detecting and resolving conflicts in meaning or context.

Both kinds of systems can encounter the same problem at a boundary: the receiving system may interpret information differently from the sending system without either party detecting the difference. The Context Graph Protocol is intended to complement existing approaches by providing a lightweight mechanism for surfacing and responding to potential misalignment in meaning, context, and intent.

## Group Structure
The group organizes its work through topic-specific steering committees. Each committee is led by a Steering Committee Chair responsible for coordinating that committee’s subject area, participation, and deliverables.

“Steering Committee Chair” is an internal leadership title within the Context Graph Community Group. Each Chair is responsible for defined deliverables that support the group’s primary objective: identifying and pursuing the most direct viable path for the Context Graph Protocol to transition into standardization through a W3C Working Group.

**Steering Committee Chairs**
- Semantic Automata: Indranil Mukhopadhyay, Principal Architect - Data Systems & Platforms and Quantum Ambassador (Technical), IBM
- Applied Knowledge: Audrey Depeige, Head of Knowledge Intelligence, Amazon
- Agentic Engineering: Alex Brown, Sr. Director of Enterprise AI Engineering, Broadridge
- Serialization & Specification: Juan Cruz Viotti, Founder of SourceMeta and member of the JSON Schema Technical Steering Committee
- Business & Finance: Ajay Wanchoo, Senior Managing Director, KPMG (in progress)
- Explainability: Michael Barnett, Co-Founder & CTO of HMX.ai (in progress)

**Committee Deliverables**

Each Steering Committee has a defined focus that contributes to the collective goals of the group:

- Semantic Automata: Develop an alpha specification and reference implementation for machine-to-machine communication that preserves and exposes relevant system context
- Applied Knowledge: Develop standardized measures for benchmarking contextual alignment in knowledge systems from the user’s perspective
- Serialization & Specification: Develop clear, implementable serialization formats and support high-quality protocol documentation
- Agentic Engineering: Identify and test real-world protocol requirements within enterprise agentic technology stacks
- Business & Finance: Define a real-world business problem and usage scenario, including benchmarks and success criteria.
- Explainable Engineering: Develop approaches for transparently exposing user, system, and organizational intent for explainability and root-cause analysis

**Group Chair's Deliverables**
- A whitepaper that integrates the work from the Steering Committee Chairs

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

The Charter ratification process will begin at the group’s first quarterly meeting.

Following that meeting, the Community Group Chair will provide the proposed Charter to all group participants and open a 14-day review period. Participants may raise substantive objections through the group’s public mailing list or GitHub repository.

If no substantive objection is received, the Charter is ratified by consensus. If an objection cannot be resolved through discussion or revision, the Community Group Chair may call a recorded vote. Ratification requires approval by two-thirds of votes cast.

After ratification, substantive changes to the group’s mission, scope, deliverables, leadership process, decision process, or amendment process will follow the same 14-day review and approval process.

The Community Group Chair may make non-substantive corrections—including typographical, formatting, link, title, and contact-information updates—without a vote. Such changes will be publicly recorded.

## Initial Technical Draft

The group’s initial technical input is the [Context Graph Protocol Draft v0.1](https://github.com/W3C-Context-Graph-Community-Group/Charter/blob/main/Context-Graph-Protocol-draft-v0.1.md).

This document is an alpha draft for review and development. It is expected to evolve through public contributions, implementation experience, testing, and Community Group decision-making.

