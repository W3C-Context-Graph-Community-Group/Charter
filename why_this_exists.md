# Context Graphs: Why This Exists

**W3C Context Graphs Community Group**

---

## The Scope Boundary

In 1948, Shannon gave us a formal theory of communication. It is one of the most successful theories in the history of science. His model is complete, elegant, and proven: given a shared codebook — a mapping between symbols and their referents — he tells you everything you need to know about transmitting information reliably.

Every major framework the industry builds on inherits this foundation. Expected utility theory, Bayesian inference, dynamic programming, active inference, Decision Intelligence — each presupposes that the meaning of inputs is shared between the system that produced the data and the model that consumes it. Shannon built this into the foundation. It is not a caveat in his theory. It is an axiom.

Shannon is correct. We are not challenging his work. We are identifying where its assumptions stop holding.

The entire industry operates in the regime where Shannon's assumption doesn't hold — open systems, multiple codebooks, no single authority — and has been using closed-system instruments to certify correctness in an open-system world. The instruments report success because they can't see the thing that's failing. That's not a flaw in the instruments. It's a scope mismatch between the instrument and the environment.

### A simple example

A system in Singapore sends a date field to a system in London:

```
time: 03/01/2026
```

Shannon's channel delivers it perfectly — zero bit error rate, zero conditional entropy, maximal mutual information. The receiver has the string exactly as the sender sent it.

But is this March 1st or January 3rd?

The sender uses MM/DD/YYYY. The receiver uses DD/MM/YYYY. For any day from the 1st through the 12th — roughly 40% of all dates in a year — the month and day positions are interchangeable. Both sides parse a valid date. Both proceed with confidence. One of them is wrong. Shannon reports zero uncertainty. The boundary carries a bit of uncertainty that no standard instrument detects.

Now add a second layer: the sender defines "time" as the moment the order was *placed*. The receiver defines "time" as the moment the order was *received*. Same label, different events. That's another bit — meaning uncertainty — also invisible to Shannon, also invisible to every downstream framework.

And a third: the sender is in Singapore (UTC+8), the producing system is hosted in New York (UTC−5), and the receiver is in London (UTC+0). Three reference frames, three possible calendar dates, no shared one. That context was never surfaced.

One field. Three bits of boundary uncertainty. Shannon reports zero. Every system reports success. Every decision model downstream receives a clean input and makes a confident decision — on a value that is structurally ambiguous, semantically misaligned, and contextually ungrounded.

### Why agents make it urgent

Humans at system boundaries have always performed an informal, undocumented version of coherence checking. They ask colleagues what a field means. They verify timezone assumptions. They pick up the phone. This is slow, fragile, and dependent on institutional memory that leaves when people leave — but it works, approximately, because humans recognize when something feels wrong and know how to ask.

Agents skip this entirely. They infer and proceed. The more capable the agent, the more convincingly it proceeds with a wrong interpretation. An agent crossing ten boundaries in a single query — ten tools, ten APIs, ten systems — has no mechanism for detecting that the meaning of a field shifted at hop three and every downstream decision is now grounded in a misinterpretation. If the interpretation flipped between hops — March 1st at one boundary, January 3rd at the next — the error propagates into every downstream decision without a trace.

The problem compounds. Each unmeasured boundary multiplies the possible misalignment states — five boundaries in a routine pipeline produce over 32,000 configurations, all invisible to standard instruments. The gap that decision theory always carried is now operationally exposed at machine speed, across organizational boundaries, with no human in the loop to catch the silent failure.

This is not a data quality problem. The data is correct. It is not a schema error. The schema validated. It is a structural property of boundaries between systems that operate under different assumptions — and it is the default condition whenever independently designed systems interact.

A natural response to the date example is: "just standardize on ISO 8601" or "enforce a single format in the schema." Inside a closed system — one design authority, one team, one governance structure — that works, and you should do it. The date format is a trivial problem when you control both sides of the boundary. The Context Graph is not built for that case. It is built for the case where you don't control the other side — where the system in Singapore was designed by a different team, under different conventions, and you have no authority to change it. You only discover the mismatch when data crosses the boundary. The protocol exists for the boundaries you don't own, connecting systems you didn't design, at runtime, when the only option is to detect the divergence and decide what to do about it.

### Toward an information-theoretic view of Context

The missing quantity is **context**: the information required to resolve ambiguity in meaning, structure, or data at a specific boundary. Context is not metadata. It is not a linguistic property of terms. It is the information-theoretic gap between what a sender encodes and what a receiver requires in order to act correctly on that encoding. When a receiver doesn't know whether `03/01/2026` is MM/DD or DD/MM, the missing information is context. When a receiver doesn't know whether "time" means order placement or order receipt, the missing information is context. When a receiver doesn't know which timezone produced the value, the missing information is context.

Context is structured uncertainty at a system boundary. Resolving it — surfacing what was missing, recording what was asked, documenting what was decided — is what collapses the ambiguity. Leaving it unresolved is what allows misalignment to compound silently across every downstream boundary.

Coherence is the achieved state when systems at a boundary can resolve their own uncertainty about meaning, structure, and data while producing a shared record that every other node in the interaction can verify.

### Why nobody built this yet

The gap is so foundational and so simple that it seems like someone should have built the instrument already.

The problem has been acknowledged since Weaver in 1949 — he wrote about levels of communication beyond Shannon's. People built ontology alignment, schema matching, context mediation — all valuable, all real contributions. But every one of these systems requires that the codebooks on both sides of a boundary have already been surfaced before reconciliation can begin. They solve the problem *after* someone has externalized what each system assumes.

Nobody built the instrument for the layer below: detecting that the codebooks haven't been surfaced at all. That is the condition that precedes every other reconciliation system's operation — and it is the default condition of most cross-system communication.

You cannot pre-build an ontology that covers every date convention, timezone, fiscal calendar, locale, and field definition across every system an agent might touch. The space is open-ended and changes as systems change. But you can build instrumentation that detects the misalignment at the boundary where it happens.

### What this program provides

The Coherence Protocol is that instrument. It decomposes the codebook into three comparison facets — **Meaning**, **Structure**, and **Data** — and a resolution layer, **Context**, that accumulates the information required to make those comparisons well-defined. Each comparison produces a binary result: aligned (0) or misaligned (1). The output is an uncertainty vector at a boundary.

The protocol produces three actions — **Act**, **Ask**, or **Halt** — where Ask is a measurement in the formal sense: it acquires information that no computation on the received data can produce. Every Ask produces Context. Every Context entry resolves an incompleteness. The protocol terminates when no further incompleteness is visible to either party.

The Context Graphs Community Group is building the specifications, vocabularies, and tooling to make this instrument operational at scale — across any two systems, at any boundary, in any domain.

The instrument exists. The industry faces the hole. The fact that it's simple doesn't make it wrong — it makes it overdue.

---

*Each committee within the Context Graphs Community Group owns a specific surface of this architecture. See the committee's own README for its scope, responsibilities, and current work.*

| Committee | Chair | Scope |
|---|---|---|
| **Community Group** | Ron Itelman | Overall direction and the Coherence Protocol specification |
| **Semantic Alignment** | Kurt Cagle | Interface with existing semantic web infrastructure (OWL, RDF, SHACL, SKOS) |
| **Decision Interface** | Dr. Lorien Pratt | Contract between coherence measurements and decision models |
| **Applied Knowledge** | Audrey Depeige | Bridge between specification, deployment, and measuring benefit |
| **Syntax & Serialization** | Juan Cruz Viotti | Wire formats, Intent Map specification, canonical claim form serialization |
| **Business & Industry** | Anthony Marquardt | Use cases, pilots, and the business case for adoption |
| **Agentic AI** | Alex Brown | Agent-to-agent and agent-to-system boundary crossings |

---

## Links

- [W3C Context Graphs Community Group](https://www.w3.org/community/context-graphs/)
- [Coherence Protocol Paper (Draft)](./docs/liquid-coherence-draft.pdf)
- [Community Group Charter](./CHARTER.md)
