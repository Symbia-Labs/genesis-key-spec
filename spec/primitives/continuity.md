# GKS Primitive: Continuity

**Status:** Stable  
**Maintainer:** Symbia Labs  

Continuity provides durable cognitive structure across episodes without violating
epistemic boundaries. It enables long-horizon reasoning while preventing implicit,
uncontrolled, or memory-like behavior.

Continuity is engineered persistence, not awareness.

---

# 1. Purpose

Continuity ensures:

- stable commitments  
- state evolution across sessions  
- deterministic reconstruction  
- constraint persistence  
- lineage coherence  

It prevents cognition from dissolving after each episode while also preventing
models from accessing unobserved historical information.

---

# 2. Continuity Principles

## 2.1 Explicit  
Continuity must be intentionally created.

## 2.2 Structural  
It stores state, not knowledge.

## 2.3 Deterministic  
Hydration and updates must be reproducible.

## 2.4 Identity-Scoped  
Continuity belongs to identities, not models.

## 2.5 Constraint-Governed  
Constraint Sets dictate what may persist or hydrate.

## 2.6 Lineage-Attached  
Every continuity transformation is logged.

---

# 3. Continuity Structure

A continuity object contains:

- identity reference  
- anchors  
- state_refs  
- constraints active at time of update  
- lineage links  
- version  

### Example (safe literal block):

    identity: "gks:agent:92f8b3e7"
    anchors:
      - anchor_id: "cont:2025-01-01T12:00Z"
        description: "post-initialization"
    state_refs:
      - "state:constraint-graph:v1"
      - "state:capability-set:v1"
    constraints:
      - "constraint-set:core-v1"
    lineage_links:
      - "event:001"
    version: 1

Continuity stores references, never raw user or conversation data.

---

# 4. Allowed vs Forbidden Content

### Allowed:
- state machine positions  
- constraint evaluations  
- entitlements  
- lineage pointers  
- structural configuration  

### Forbidden:
- raw conversation  
- user secrets  
- implicit memory  
- unverifiable knowledge  
- private agent state  

Continuity is not a knowledge substrate.

---

# 5. Continuity vs Memory

| Category           | Continuity         | Model Memory       |
|--------------------|--------------------|--------------------|
| Epistemically safe | Yes                | No                |
| Deterministic      | Yes                | No                |
| Stores knowledge   | No                 | Sometimes         |
| Stores structure   | Yes                | Sometimes         |
| User-controlled    | Yes                | Partially         |

Continuity avoids the risks of “hidden LLM memory.”

---

# 6. Continuity Anchors

Anchors are named checkpoints. Examples:

- post-initialization  
- pre-deployment  
- post-constraint-update  
- post-identity-rotation  

Anchors do not imply remembered content.

---

# 7. Lifecycle

## Creation  
Occurs when identity is created.

## Update  
Occurs when structural state changes.

## Checkpoint  
Creates anchors and lineage links.

## Hydration  
Restores structural state only when constraints allow it.

## Rotation  
Continuity rotates when identity rotates; lineage preserves history.

---

# 8. Continuity + OEP

Continuity must not:

- modify epistemic metadata  
- imply awareness of prior episodes  
- rehydrate private or narrative context  
- bypass OEP observability boundaries  
- insert unverifiable information  

Continuity works strictly outside the epistemic boundary.

---

# 9. Conformance Criteria

A system is GKS-continuity-compliant if:

1. Continuity objects follow defined structure  
2. No forbidden content persists  
3. All updates produce lineage events  
4. Hydration occurs only via allowed constraints  
5. No continuity mechanism implies knowledge continuity  
6. Continuity is identity-bound  
7. All operations are deterministic  

---

# 10. Summary

Continuity is:

- explicit  
- deterministic  
- structural  
- identity-scoped  
- constraint-governed  
- lineage-integrated  

It enables durable cognition without violating OEP or introducing implicit memory.

---

# End of Continuity Primitive
