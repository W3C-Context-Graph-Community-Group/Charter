# W3C Context Graph Community Group — Email #001

**Date:** 2026-03-17  
**From:** Ron Itelman, Community Group Chair  
**To:** W3C Context Graph Community Group Members  
**Subject:** Welcome — Committee Chairs, Kickoff Dates, and How We Work Together  

---

Hi everyone,

I'm Ron Itelman, chair of the W3C Context Graph Community Group. I'm grateful for the participation this group is already seeing, and I wanted to share three things: a bit about where this work comes from, who's leading the committees, and how I'd like us to work together.

## Where This Started (A Short Origin Story)

I started this work doing R&D in banking around AI accuracy in finance. I quickly ran into the roadblocks many people face daily:

- I couldn't get the team owning the data catalog to give me access.
- I had no authority to impose an ontology, and none existed that I was aware of.
- All I could control was my own local system.

That constraint turned out to be the insight: start with what you have, not what you want. I laid out the uncertainty — which columns were ambiguous, which definitions were missing, which assumptions I was making — and collapsed it piece by piece.

I saw the same pattern everywhere: Every team was doing context engineering independently — constantly adapting prompts, running evals in their own way, using LLMs to judge LLMs. It was uncertainty stacked on uncertainty. I wanted to ground the effort in something that could actually be measured.

That led to a formal protocol for detecting and resolving misalignment at system boundaries — not by imposing a framework, but by giving any system a way to represent what it knows, what it doesn't know, and what it needs to ask. That's what the context graph does, and that's what we're building together.

## Committee Chairs

Each committee covers a different part of the architecture. Please review the full descriptions and decide which group (or groups) you'd like to participate in:

*Each committee within the Context Graphs Community Group leads a specific surface of this architecture.*

| Committee | Chair | Scope |
|---|---|---|
| **Coherence Protocol** | Ron Itelman | Core protocol specification: four facets, canonical claim form, Halt/Ask/Act, dependency ordering |
| **Semantic Alignment** | Kurt Cagle | Interface with existing semantic web infrastructure (OWL, RDF, SHACL, SKOS) |
| **Decision Interface** | Dr. Lorien Pratt | Contract between coherence measurements and decision models |
| **Applied Knowledge** | Audrey Depeige | Bridge between specification, deployment, and measuring benefit |
| **Syntax & Serialization** | Juan Cruz Viotti | Wire formats, Intent Map specification, canonical claim form serialization |
| **Business & Industry** | Anthony Marquardt | Use cases, pilots, and the business case for adoption |
| **Agentic AI** | Alex Brown | Agent-to-agent and agent-to-system boundary crossings |
| **Error Analysis and Theory** | <pending> | Error classification, coherence scoring, and measurement theory for the Halt/Ask/Act thresholds |



Thank you to all the committee chairs for stepping up to lead this work. I'll be honest — I'm amazed at the group we've assembled. Semantic web architects, decision scientists, applied researchers, JSON/API engineers, and business strategists all in one room. Every one of them is someone I learn from, and the opportunity to work alongside them is not lost on me. 

If you're interested in helping with group communications and coordination, there's an open slot — reach out to me directly.

Full descriptions are here: [Committee Chairs README](https://github.com/W3C-Context-Graph-Community-Group/Charter)

## How We Work Together

This group is community driven. The chairs bring a starting foundation — a theoretical paper, a glossary, and an architectural framework. But the specification will be shaped by what you bring to it. The specification follows the problems, not the other way around.

If you see a problem we're not addressing, bring it. If you have boundary problems from your own systems — the time your systems passed every check and the answer was still wrong — those are exactly the use cases that will make this standard real.

## Kickoff Calls

I'd like to host two kickoff calls so people can choose which works better for them, and if you can't make either time, please ping me and we'll figure something out.

- **Option 1:** March 24th  
Tuesday, March 24 · 12:00 – 1:00pm  
Time zone: America/Denver  
Video call link: https://meet.google.com/zmq-ztjj-qxx  
Or dial: ‪(US) +1 339-545-4323‬ PIN: ‪682 982 936‬#  

- **Option 2:** March 31st  
Tuesday, March 31 · 12:00 – 1:00pm  
Time zone: America/Denver  
Video call link: https://meet.google.com/bqr-nqsc-wut  
Or dial: ‪(US) +1 267-870-7492‬ PIN: ‪471 927 350‬#  

Each call will cover the same content: brief introductions, a walk through of the committees and how to get involved, and a chance to ask questions. Attend whichever works for you.

Looking forward to meeting everyone.

**Ron Itelman**
W3C Context Graph Community Group Chair
