# GKS Primitive: Identity

**Status:** Stable  
**Maintainer:** Symbia Labs  

Identity is the foundational primitive of the Genesis Key Specification (GKS).
It provides a stable, portable, cryptographically grounded representation of
actors, agents, systems, and processes operating within a GKS-compliant
environment.

Identity primitives allow cognition to persist across episodes without granting
models implicit memory or unbounded access to past state. Identity is a structural,
not epistemic, construct.

---

# 1. Purpose

Identity enables:

- continuity across sessions  
- traceability of actions and lineage  
- constraint and entitlement enforcement  
- scoped access to state and capabilities  
- deterministic reconstruction of state transitions  

Identity is **not** a memory resource and does **not** bypass the Open Epistemic
Protocol (OEP). It is a label and permission framework, not a knowledge channel.

---

# 2. Identity Requirements

An identity must be:

1. **Stable** — persists across sessions unless intentionally rotated  
2. **Unique** — globally non-colliding  
3. **Opaque** — does not reveal private information  
4. **Portable** — transferable between compatible systems  
5. **Auditable** — usable as a reference in lineage  
6. **Non-epistemic** — cannot imply awareness or access to unobserved information  

These properties ensure identity does not leak information or introduce implicit
context outside the OEP boundary.

---

# 3. Identity Structure

A GKS identity consists of the following minimum fields:

- **id** — unique cryptographic identifier  
- **type** — category (e.g., agent, user, system, process)  
- **entitlements** — references to constraint sets governing behavior  
- **attributes** — optional, non-sensitive metadata  
- **public_key** — optional, used for signed lineage or capabilities  
- **created_at** — timestamp of identity creation  
- **version** — identity schema version  

Example (YAML):

id: “gks:agent:92f8b3e7-3d29-4c8c-af7c-a1c7d3c5c843”
  type: agent
  entitlements:
  constraint-set:core-v1
  attributes:
  role: “assistant”
  public_key: “ED25519:abc123…”
  created_at: “2025-01-01T12:00:00Z”
  version: 1

---

# 4. Entitlement Binding

Identities do not carry capabilities directly.  
Instead, they reference **constraint sets**, which define what the identity is
allowed to do.

This ensures:

- capabilities remain revocable  
- permissions are externally governed  
- constraints can evolve without rotating identity keys  

Entitlements are *always* evaluated by the Processor role.

---

# 5. Identity and OEP

Identity must not violate OEP boundaries:

- It cannot encode or imply user intent  
- It cannot reveal past interactions  
- It cannot embed private state  
- It cannot grant awareness of previous episodes  
- It cannot carry unverified or unverifiable information  

Identity is strictly a governance and continuity construct, not a memory or
knowledge channel.

---

# 6. Identity Rotation

GKS supports deliberate identity rotation for:

- privacy  
- lifecycle management  
- privilege reduction  
- revocation events  
- lineage forks  

Rotation rules:

1. Old identity remains in lineage  
2. New identity receives a new unique identifier  
3. Entitlements may be preserved or reassigned  
4. No epistemic continuity is implied; continuity must be explicit  

Rotation must never create ambiguous or merged identities.

---

# 7. Identity Interoperability

Identities may be:

- exported  
- imported  
- verified  
- revoked  

Interoperability requirements:

- format must be stable  
- signatures (if used) must be verifiable  
- entitlements must be interpretable  
- lineage references must remain valid  

Cross-system portability does **not** grant cross-system access.

---

# 8. Conformance Criteria

A system is GKS-identity-compliant if:

1. Every agent, system, or process has a valid identity  
2. Identities follow the structural requirements above  
3. Identities do not embed epistemic or private state  
4. Entitlements tie identities to constraint sets  
5. Identity rotation preserves lineage  
6. Identities remain stable unless intentionally rotated  
7. No identity information bypasses OEP boundaries  

---

# 9. Summary

Identity is the anchor for:

- constraint enforcement  
- continuity across episodes  
- lineage traceability  
- capability scoping  
- multi-agent coordination  

Identity is structural—not epistemic, not contextual, and not a memory source.

It is the first and most fundamental primitive of GKS.

---

# End of Identity Primitive
