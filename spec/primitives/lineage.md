# GKS Primitive: Lineage

**Status:** Stable  
**Maintainer:** Symbia Labs  

Lineage is the event-sourcing substrate of the Genesis Key Specification (GKS).
It provides a durable, auditable, deterministic record of all structural changes,
decisions, constraints, identity events, and continuity transitions.  

Lineage enables interpretability, accountability, reproducibility, and forensic
reconstruction of system behavior across episodes. It is the historical ledger of
the Execution Layer.

Lineage is structural—not epistemic.  
It does not provide memory, knowledge, or awareness to models.

---

# 1. Purpose

Lineage serves six core purposes:

1. **Traceability** — every cognitive event can be reconstructed  
2. **Accountability** — all constraint and identity operations are recorded  
3. **Determinism** — past decisions become reproducible  
4. **Auditability** — external verifiers can inspect system behavior  
5. **Forensics** — failures can be diagnosed  
6. **Continuity stitching** — continuity transitions are linked across time  

Lineage is the persistent connective tissue between events, not a knowledge
channel.

---

# 2. Principles

## 2.1 Immutable  
Lineage entries may not be altered once written.

## 2.2 Append-Only  
New events extend the timeline; they do not modify old ones.

## 2.3 Deterministic  
Event creation must follow deterministic logic, not model stochasticity.

## 2.4 Non-Epistemic  
Lineage stores structural metadata, not content that could imply knowledge.

## 2.5 Identity-Scoped  
Events attach to identities or processes.

## 2.6 Ordered  
Lineage maintains strict temporal ordering.

## 2.7 Verifiable  
Signatures or hashes may be used when higher assurance is required.

---

# 3. Lineage Structure

Each lineage entry contains:

- event_id  
- timestamp  
- actor_identity  
- event_type  
- payload (structured state)  
- constraint_context  
- continuity_context  
- parent_links  
- checksum or hash (optional)  

### Example (safe literal block):

    event_id: "event:001"
    timestamp: "2025-01-01T12:00:01Z"
    actor_identity: "gks:agent:92f8b3e7"
    event_type: "constraint-update"
    payload:
      updated_constraints:
        - "constraint-set:core-v1"
    constraint_context:
      active:
        - "constraint-set:core-v1"
    continuity_context:
      anchors:
        - "cont:2025-01-01T12:00Z"
    parent_links:
      - "event:000"
    checksum: "sha256:abc123..."

The payload structure is governed by the type of event.

---

# 4. Event Types

Lineage must include, at minimum:

### **4.1 Identity Events**
- identity creation  
- identity rotation  
- entitlement modification  

### **4.2 Constraint Events**
- constraint-set creation  
- constraint-set update  
- constraint-set dependency resolution  
- violation events  

### **4.3 Continuity Events**
- continuity initialization  
- anchor creation  
- continuity updates  
- continuity hydration (structural only)  

### **4.4 Execution Events**
- pipeline role transitions  
- structural transformations  
- blocked actions  
- successful rule evaluations  

### **4.5 Observability & Epistemic Events**
- OEP enforcement outcomes  
- awareness violation detections  
- hypothetical-labeling inserts  
- provenance validation 

Lineage is not aware of epistemic content — it records the *structural outcome*.

---

# 5. Allowed vs Forbidden Lineage Content

## Allowed:
- structural metadata  
- constraint identifiers  
- identity references  
- timestamps  
- continuity anchors  
- hashes or signatures  
- version identifiers  
- state machine transitions  

## Forbidden:
- raw conversation  
- subjective model outputs  
- user-provided private data  
- anything that implies accessible prior context  
- unverifiable knowledge  
- model-internal state or logits  

Lineage is a structural audit trail, not a content store.

---

# 6. Parent Links and Causality

Each event may link to zero or more parents:

Example:

- event:002 -> event:001  
- event:003 -> event:001, event:002  

Properties:

- creates a causal DAG  
- enables reconstruction of system behavior  
- supports branching and merging  
- enables introspection of forks in continuity  

Parents may never be removed, only added.

---

# 7. Lineage and OEP

Lineage must never:

- override OEP metadata  
- embed epistemic claims  
- imply continuity of knowledge  
- produce unverifiable assertions  
- introduce information unavailable in the current episode  

Instead:

- lineage entries include OEP metadata (e.g., claim class, reasoning mode)  
- lineage confirms OEP compliance but does not add knowledge  

Lineage exists *outside* the model’s epistemic boundary.

---

# 8. Lineage Hydration

Hydration restores **structural state** for the Execution Layer.

Hydration may restore:

- constraint contexts  
- continuity anchors  
- identity entitlements  
- versioned state references  
- event-order constraints  

Hydration may *not* restore:

- past conversation  
- user content  
- model-side context  
- any epistemic information disallowed by OEP  

Hydration is always subject to Constraint Sets.

---

# 9. Serialization Requirements

Lineage must support stable serialization formats. Requirements:

- deterministic key ordering  
- consistent timestamps  
- global uniqueness for event_ids  
- ability to hash or sign  
- cross-system interoperability  

Formats may include JSON, CBOR, MessagePack, or others, but must preserve
structure faithfully.

---

# 10. Conformance Criteria

A system is GKS-lineage-compliant if:

1. All lineage entries follow the structure above  
2. No lineage entry contains epistemic or narrative content  
3. All constraint and identity changes generate lineage entries  
4. Event IDs are globally unique  
5. Lineage ordering is strictly maintained  
6. Hydration follows allowed rules only  
7. Signatures/hashes (if used) are valid  
8. All lineage entries are immutable once written  

---

# 11. Summary

Lineage is the **auditable backbone** of GKS:

- immutable  
- append-only  
- deterministic  
- structural  
- identity-scoped  
- constraint-governed  
- continuity-linked  

It enables full accountability and traceability without providing the model
any additional knowledge or awareness.

Lineage is the Execution Layer’s memory of structure — not content.

---

# End of Lineage Primitive
