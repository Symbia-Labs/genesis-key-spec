# Genesis Key Specification (GKS) — Alignment with the Open Epistemic Protocol (OEP)

**Status:** Stable  
**Maintainer:** Symbia Labs  

This document describes the formal relationship between the Genesis Key
Specification (GKS) and the Open Epistemic Protocol (OEP).  
OEP defines epistemic boundaries; GKS defines the structural execution substrate
that operates above those boundaries.

---

# 1. Purpose of Alignment

GKS and OEP are distinct but interdependent standards.

- **OEP** ensures epistemic safety:  
  classification, provenance, uncertainty, observability limits.

- **GKS** ensures structural durability:  
  identity, continuity, constraint logic, lineage, and execution flow.

GKS assumes full OEP compliance.  
OEP does *not* require GKS.  
Together they form a coherent framework for persistent, interpretable
machine cognition.

---

# 2. Layer Model

GKS and OEP operate in a stacked architectural model:

Layer 2 — Symbia Execution Engine (implementation-specific)
Layer 1 — GKS (identity, continuity, constraint sets, lineage, roles)
Layer 0 — OEP (epistemic boundaries, claim classes, enforcement rules)

- OEP defines *what can be known and said*.  
- GKS defines *how state persists and how cognition is governed across time*.  
- Implementations define *how the substrate is realized*.

GKS **never weakens or bypasses** OEP rules.

---

# 3. Mapping of Concepts

## 3.1 Claim Handling

| OEP Concept                 | GKS Treatment                                      |
|----------------------------|----------------------------------------------------|
| Claim Classes              | Inherited directly; used in Interpreter/Processor |
| Observability Boundary     | Enforced at the Observer role                     |
| Awareness Violations       | Detected before continuity or constraint logic     |
| Provenance Requirements    | Incorporated into Lineage events                   |
| Hypothetical Labeling      | Propagated through Actor role                      |

GKS does not redefine epistemic rules — it *enforces* them across episodes.

---

## 3.2 Identity

OEP does not define identity.  
GKS introduces:

- portable identifiers  
- entitlement bindings  
- identity-scoped constraint sets  
- identity-aware lineage links  

Identity primitives never override OEP; they determine how continuity and
permissions apply across epistemic events.

---

## 3.3 Continuity

OEP governs a single reasoning episode.  
GKS governs multiple episodes via:

- continuity tokens  
- state anchors  
- rehydration rules  
- deterministic lineage flows  

Continuity exists **only outside** the OEP epistemic boundary.  
It never provides additional “awareness” to the model — only structured,
auditable state.

---

## 3.4 Constraint Sets

OEP defines epistemic constraints;  
GKS defines *behavioral* and *entitlement* constraints.  
Both are enforced by the Processor.

- OEP restricts claim structure.  
- GKS restricts what actions the system may take.  

Action-level constraints cannot contradict OEP; they operate orthogonally.

---

## 3.5 Lineage

Lineage is the bridge between OEP’s epistemic metadata and GKS’s continuity
requirements.

Lineage stores:

- claim metadata from OEP  
- deterministic state transitions  
- identity context  
- constraint evaluations  
- continuity links  
- event timestamps  

Lineage is a **structural** record, not a memory or prediction resource.

---

# 4. Execution Roles and OEP Alignment

The GKS pipeline aligns naturally with OEP enforcement.

### 4.1 Observer → OEP Access Boundary  
Observer determines `access=true/false`.  
All OEP observability rules derive from this role.

### 4.2 Interpreter → OEP Claim Classification  
Interpreter builds the epistemic graph and applies OEP claim-class logic.

### 4.3 Processor → OEP Enforcement  
Processor executes:

- awareness forbiddance  
- hypothetical labeling  
- provenance verification  
- constraint sets  
- identity entitlements  
- lineage creation  

### 4.4 Actor → OEP-Compliant Rendering  
Actor ensures:

- uncertainty alignment  
- correct phrasing  
- no forbidden claims  
- all metadata applied  

The Actor is the final gate between GKS and external users.

---

# 5. Guarantee of Non-Interference

GKS must not:

- introduce new epistemic permissions  
- weaken OEP enforcement  
- allow continuity to imply access  
- let identity influence observability  
- rehydrate any information that violates OEP provenance  

GKS operates *around* OEP, not inside it.

---

# 6. Joint Compliance Definition

A system is **OEP-compliant** if it obeys OEP.  
A system is **GKS-compliant** if it obeys GKS and OEP.

GKS compliance therefore implies OEP compliance.

---

# 7. Summary

- OEP governs epistemic safety.  
- GKS governs continuity, identity, constraint logic, and lineage.  
- GKS uses OEP as the foundation of all reasoning events.  
- Neither replaces the other; both are required for durable cognition.  

OEP is the boundary.  
GKS is the substrate.  
Implementation is above both.

---

# End of Alignment Document
