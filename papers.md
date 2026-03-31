# Papers

## Liquid Hypergraphs: A Context Graph Protocol
[Liquid Hypergraphs: A Context Graph Protocol](https://zenodo.org/records/19351081)

This paper identifies the boundary gap — the structural condition where no entity governs and no entity possesses the information needed to verify codebook alignment between systems — and proves via the closure property that no computation within a fixed state space resolves it. We introduce null uncertainty as a third epistemic category beyond Knight's taxonomy, where the system structurally cannot perceive the absence of a variable, and prove a computable lower bound on the number of misaligned configurations guaranteed indistinguishable from alignment by any within-system observable (Proposition 3). The bound is a pigeonhole argument over Kowalski's forced quantization theorem: for realistic organizations it exceeds 2^800. We formalize the liquid hypergraph — a data structure whose edges exist only because measurements were made — and provide a protocol (four-facet gauge, five-column canonical claims, TCP-style handshake) that implements the measurement layer. Two synthetic demonstrations show the mechanism. Code, datasets, and protocol specification: https://w3c-context-graph-community-group.github.io/protocol/

## Decisions Under Null Uncertainty: The Unit Cost of Ignorance at System Boundaries 

[Decisions Under Null Uncertainty: The Unit Cost of Ignorance at System Boundaries](https://zenodo.org/records/19192949)


This paper takes a motivating question from decision science: how should we describe, in the language of decisions, cost, uncertainty, and state, a system that remains confident while failing to represent a consequential blind spot? What are the economic costs of missing such boundaries, and how might we detect them before they impose those costs on us?

The paper identifies a single structural property — the closure property — and derives five consequences from it: that Shannon's semantic gap is permanent from inside his framework; that verified safety and total ignorance are observationally identical at runtime; that decision-theoretic optimality is conditional in a way no framework checks; that no existing instrument detects codebook misalignment at unmeasured boundaries; and that cross-boundary inquiry is the sole mechanism for resolving what the paper calls null uncertainty — the state in which a system does not know there is a question to ask.

## Liquid Coherence: A Protocol for Codebook Alignment at System Boundaries

[Liquid Coherence: A Protocol for Codebook Alignment at System Boundaries](https://zenodo.org/records/19005457)


Every framework that minimizes uncertainty — Shannon's channel coding, active inference, Bayesian decision theory — presupposes that sender and receiver share a codebook. This paper proves that no quantity computable from Shannon's model detects codebook misalignment, and shows that this gap extends to every downstream framework. When systems cross a boundary without verifying their codebooks, the receiver proceeds with zero uncertainty about an interpretation that may be wrong — a condition we call ignorance of incoherence.

We provide the instrument that fills this gap: a coherence protocol that decomposes the codebook into three comparison facets — Meaning, Structure, and Data — and a resolution layer, Context, that accumulates what was missing, surfaced, and resolved across the other three. The protocol is grounded in an irreducible five-column canonical claim form onto which any system can project its codebook at the moment of contact, requiring no prior agreement on terms.

The protocol produces three actions — Halt, Ask, and Act — where Ask is a measurement in the formal sense: it acquires information that no computation on the received data can produce. The cost is O(1) per facet comparison per boundary crossing. The substrate reduces to binary and admits tensor decomposition, opening a path toward self-referential inference on the same surface that performs measurement.

## Rotational Cost at System Boundaries: Perseverant Decisions Under Null Uncertainty

[Rotational Cost at System Boundaries: Perseverant Decisions Under Null Uncertainty](https://zenodo.org/records/19239912)



When a variable crosses a system boundary, its value arrives but its reference frame does not. No computation inside the receiving system can recover the missing frame. The only mechanism is rotation: orienting outward to observe the other system's frame, then inward to compare it against one's own. The two orientations are mutually exclusive at any instant. Each switch has a cost. This cost is the irreducible unit of coherence.

The paper introduces perseverance as a technical term for the invariance of a measurement process across varying reference frames, and identifies the rotation — each alternation between inward and outward orientations — as the atomic unit of coherence cost. A five-column canonical claim form (the gauge) makes each rotation productive by providing a fixed projection surface that requires no prior agreement on terms.

Claim 1 (completed): Coherence does not guarantee correctness. It guarantees a shared frame of reference for mutually agreed measures of correctness.

Claim 2 (open research agenda): The minimum rotations required to detect failure at level N from level N+1 in nested decision systems, and the economic price of unpaid rotations, are not formally characterized. Argyris's double-loop learning, von Foerster's second-order cybernetics, and Friston's hierarchical active inference all describe the phenomenon of stepping outside a model. None price the rotation.
