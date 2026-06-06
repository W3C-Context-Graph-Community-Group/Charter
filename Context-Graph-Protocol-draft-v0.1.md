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
