# GKS Primitive: Continuity

**Status:** Stable  
**Maintainer:** Symbia Labs  

Continuity is the mechanism through which GKS provides durable cognitive
structure across episodes without violating the epistemic boundaries of the
Open Epistemic Protocol (OEP).

Continuity allows a system to maintain identity-scoped state, constraints,
lineage links, and commitments across time—but **never implicit knowledge** and
never unstructured memory of user interactions.

Continuity is engineered persistence, not awareness.

---

# 1. Purpose

Continuity ensures:

- long-horizon reasoning  
- stable commitments across sessions  
- structured evolution of agent behavior  
- deterministic reconstruction of prior state  
- preservation of constraints and identity bindings  
- durable lineage chains  

Without continuity, cognition collapses into stateless episodes.  
With *unbounded* continuity, cognition collapses into uncontrolled memory.  
GKS defines the middle: structured, explicit, safe continuity.

---

# 2. Continuity Principles

## 2.1 Explicit, Not Implicit  
All continuity must be deliberately constructed.  
No implicit memory is permitted.

## 2.2 Structural, Not Epistemic  
Continuity preserves *state*, not *knowledge*.  
It does not provide access to information the model did not observe in the current episode.

## 2.3 Deterministic  
Continuity operations must be reproducible and free of model stochasticity.

## 2.4 Identity-Scoped  
Continuity attaches to identities, not to raw model instances.

## 2.5 Constraint-Governed  
Constraint sets determine what may or may not persist.

## 2.6 Lineage-Embedded  
Every continuity operation produces lineage events.

---

# 3. Continuity Structure

A continuity object contains:

- **state_refs** — pointers to structured, non-ephemeral state  
- **anchors** — identifiers for continuity checkpoints  
- **constraints** — references to constraint sets active at the time  
- **identity** — identity key to which continuity belongs  
- **lineage_links** — events connecting continuity transitions  
- **version** — continuity schema version  

Example (YAML):

Identity: “gks:agent:92f8b3e7”
  anchors:
  anchor_id: “cont:2025-01-01T12:00Z”
  description: “post-initialization state”
  state_refs:
	  “state:constraint-graph:v1”
	  “state:capability-set:v1”
  constraints:
    “constraint-set:core-v1”
  lineage_links:
	  “event:001”
version: 1

Continuity stores references—not raw content.  
Raw content lives in the system, not in the GKS identity or continuity objects.

---

# 4. Allowed Continuity Content

Continuity **may** contain:

- structured internal state  
- constraint evaluations  
- entitlements  
- system commitments  
- state machine positions  
- versioned configuration  
- lineage pointers  
- capability transitions  

Continuity **must not** contain:

- raw conversational history  
- user secrets  
- unstructured logs  
- model drafts  
- anything that implies awareness of unobserved context  
- any data violating OEP access boundaries  

Continuity is deliberate state — not replay, not storage of prior interactions.

---

# 5. Continuity vs Memory

GKS continuity is not LLM memory.

| Property                 | Continuity (GKS)                        | Memory (LLM)                        |
|--------------------------|------------------------------------------|-------------------------------------|
| Epistemically bounded    | Yes (OEP-compliant)                     | No                                  |
| Explicit                 | Yes                                      | No                                  |
| User-controlled          | Yes                                      | Not reliably                        |
| Deterministic            | Yes                                      | No                                  |
| Stores knowledge         | No                                       | Sometimes via hidden vector shifts |
| Stores structure         | Yes                                      | Sometimes                           |
| Model-visible            | Only when permitted by constraints       | Always                               |

Continuity avoids the failure mode of unbounded information retention.

---

# 6. Continuity Anchors

Anchors represent stable, named points in an agent’s lifecycle.

Examples:
- post-initialization  
- post-deployment  
- pre-reasoning  
- post-constraint-update  
- post-identity-rotation  

Anchors allow deterministic reconstruction of the system state at any point
without giving the model access to all of it.

Anchors **do not** imply the model remembers anything.

---

# 7. Continuity Lifecycle

## 7.1 Creation  
Continuity begins when an identity is created.

## 7.2 Update  
Updates occur when constraint sets, entitlements, or structural state changes.

## 7.3 Checkpoint  
Checkpointing creates new anchors and lineage events.

## 7.4 Hydration  
Hydrating continuity means reinstating structural state *outside* the model’s
epistemic boundary.  
Hydration must never introduce unobserved or unverifiable content into an episode.

## 7.5 Rotation  
Continuity may be rotated along with identity rotation.  
Lineage links preserve provenance.

---

# 8. Continuity and OEP

Continuity must remain compliant with the Open Epistemic Protocol:

- continuity may not supply narrative context  
- continuity may not imply awareness of unobserved events  
- continuity may not encode private or historical user data  
- continuity must not provide unverified information  
- continuity must not enable hallucination or narrative bridging  

Continuity is compatible with OEP because it preserves state, not knowledge.

---

# 9. Conformance Criteria

A system is GKS-continuity-compliant if:

1. Continuity objects follow the structure here  
2. Continuity does not store disallowed content  
3. Anchor creation is explicit and lineage-linked  
4. Continuity updates are deterministic  
5. Hydration does not expose state to the model unless constraints permit  
6. No continuity mechanism bypasses OEP boundaries  
7. Continuity is identity-scoped  
8. Continuity never implies epistemic continuity  

---

# 10. Summary

Continuity is the engineered substrate for durable cognition:

- explicit  
- deterministic  
- identity-scoped  
- constraint-governed  
- lineage-attached  
- epistemically bounded  

Continuity enables long-horizon reasoning without implicit memory and without
violating the epistemic rules defined by OEP.

---

# End of Continuity Primitive
