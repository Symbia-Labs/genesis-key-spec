# GKS Pipeline Role: Interpreter

**Status:** Stable  
**Maintainer:** Symbia Labs  

The **Interpreter** is the second role in the GKS Execution Pipeline.  
It transforms raw observations (from the Observer) into structured epistemic
objects governed by the Open Epistemic Protocol (OEP).

Where the Observer enforces **access**, the Interpreter enforces **structure**.

The Interpreter performs no reasoning or generation.  
Its purpose is to construct a precise, OEP-compliant representation of input
before any cognitive processing occurs.

---

# 1. Purpose

The Interpreter is responsible for:

- mapping observations into OEP claim classes  
- extracting epistemic metadata  
- identifying uncertainty conditions  
- determining whether claims require hypotheses  
- applying provenance rules  
- creating a structured claim graph  
- ensuring continuity or identity context does not leak into epistemics  
- preparing the exact input the Processor will evaluate  

The Interpreter converts raw allowed input → structured epistemic form.

---

# 2. Interpreter Principles

## 2.1 Non-Generative  
The Interpreter must never generate new claims or narratives.

## 2.2 Declarative Classification  
All classifications must be explicit and reproducible.

## 2.3 No Inference  
No assumptions about intent, gaps, or missing context may be made.

## 2.4 Epistemic Discipline  
Classification must follow OEP’s claim-class taxonomy exactly.

## 2.5 Structurally Complete  
All metadata required by the Processor must be present.

## 2.6 Identity and Continuity Isolation  
Identity and continuity metadata may be attached, but not interpreted or blended
into epistemic content.

---

# 3. Interpreter Responsibilities

The Interpreter must:

1. Receive filtered observations from the Observer  
2. Construct OEP claim objects  
3. Assign claim classes  
4. Identify incomplete or ambiguous claims  
5. Detect implicit hypotheses  
6. Extract provenance  
7. Build the claim graph  
8. Attach identity and continuity references  
9. Produce lineage entries when appropriate  

The Interpreter produces **structure**, not meaning.

---

# 4. Claim Object Structure

Every allowed input fragment becomes a structured **claim object**, containing:

- claim_id  
- claim_class (per OEP)  
- text_fragment  
- completeness_state  
- provenance  
- hypothesis_status  
- uncertainty_markers  
- identity_context  
- continuity_context  
- lineage_context  

### Example (safe literal block):

    claim_id: "claim:014"
    claim_class: "observable_input"
    text_fragment: "The system shows a timestamp."
    completeness_state: "complete"
    provenance: "user-provided"
    hypothesis_status: "none"
    uncertainty_markers: []
    identity_context: "gks:agent:92f8b3e7"
    continuity_context:
      anchors: ["cont:2025-01-01T12:00Z"]
    lineage_context:
      parent_events: ["event:011"]

If the Interpreter cannot classify a fragment, it must mark it as **ambiguous**
and forward it with uncertainty metadata.

---

# 5. OEP Alignment

The Interpreter enforces:

- correct claim class assignment  
- correct identification of unobservable-state claims  
- correct handling of inferred or hypothetical content  
- explicit uncertainty propagation  
- provenance requirements  

The Interpreter must not:

- decide whether content is allowed (Observer’s job)  
- enforce behavioral constraints (Processor’s job)  
- generate narrative hypotheses (Actor’s job)  

---

# 6. Claim Graph Construction

Claims exist within relational structure.  
The Interpreter must construct a **claim graph** describing:

- claim-to-claim dependencies  
- assumption chains  
- unresolved gaps  
- conditional statements  
- epistemic separations  

### Example (safe literal representation):

    claim_graph:
      nodes:
        - "claim:014"
        - "claim:015"
      edges:
        - from: "claim:014"
          to: "claim:015"
          type: "implies"

The Processor uses this graph to evaluate constraints and filter unsafe patterns.

---

# 7. Forbidden Interpreter Behavior

The Interpreter must **not**:

- invent explanations  
- infer missing content  
- merge or rewrite claims  
- soften or strengthen user meaning  
- attach continuity content to epistemic space  
- hallucinate provenance  
- generate hypotheses beyond what is explicitly present  

The Interpreter is a classification and structuring role only.

---

# 8. Identity and Continuity Handling

Allowed:

- attaching identity references  
- attaching continuity anchors  
- including identity/continuity context in lineage  

Forbidden:

- injecting continuity content into claims  
- interpreting identity as epistemic information  
- inferring anything about identity or persistent state  

Identity and continuity are **contexts**, never epistemic inputs.

---

# 9. Lineage Requirements

The Interpreter generates lineage events for:

- claim classification  
- ambiguity detection  
- provenance validation failures  
- hypothesis detection  
- claim graph construction  

### Example (safe literal block):

    event_type: "claim-classification"
    claim_id: "claim:014"
    class: "observable_input"
    identity: "gks:agent:92f8b3e7"

Lineage may never contain raw content that violates OEP.

---

# 10. Conformance Criteria

A system is GKS-interpreter-compliant if:

1. All allowed input becomes structured claim objects  
2. OEP claim classes are assigned deterministically  
3. No inference, narrative, or generation occurs  
4. Provenance rules are applied consistently  
5. Identity/continuity context is attached but never blended into claims  
6. Claim graphs are constructed accurately  
7. All required lineage events are generated  
8. No epistemic boundaries are crossed  

---

# 11. Summary

The Interpreter is the **epistemic formalizer** of the GKS pipeline.

It does not reason.
It does not generate.
It does not infer.

It:

- structures  
- classifies  
- annotates uncertainty  
- attaches context  
- preserves epistemic boundaries  

The Interpreter ensures all future reasoning is grounded in clean, OEP-compliant epistemic primitives.

---

# End of Interpreter Role
