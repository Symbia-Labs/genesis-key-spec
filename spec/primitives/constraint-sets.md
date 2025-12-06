# GKS Primitive: Constraint Sets

**Status:** Stable  
**Maintainer:** Symbia Labs  

Constraint Sets define the permissible actions, transformations, capabilities,
and behaviors of an identity within GKS. They are the primary mechanism for
governing agent behavior and ensuring durable, interpretable, safe cognition.

Constraint Sets do not weaken or override the Open Epistemic Protocol (OEP).  
Instead, they provide an additional, orthogonal layer of behavioral governance.

---

# 1. Purpose

Constraint Sets establish:

- what an identity is allowed to do  
- which transformations are permitted  
- what operations require entitlement  
- which actions must be denied  
- boundaries on continuity hydration  
- allowable pipeline transitions  
- required metadata for outputs  
- escalation rules for violations  

They ensure reasoning does not become arbitrary, unbounded, or inconsistent across episodes.

---

# 2. Principles

## 2.1 Constraint-Supremacy  
Constraints supersede model output. If a model proposes output that violates a
constraint, the Actor must block or transform it.

## 2.2 Deterministic Enforcement  
Constraint evaluation must be deterministic and reproducible.

## 2.3 Identity-Scoped  
Constraints are bound to identities via entitlements.

## 2.4 Orthogonal to OEP  
Constraint Sets govern behavior; OEP governs epistemic structure.

## 2.5 Evolving but Versioned  
Constraints may evolve, but versions must remain immutable for lineage.

---

# 3. Constraint Set Structure

A Constraint Set contains:

- **id** — unique identifier  
- **version** — semantic version  
- **description** — summary  
- **allowed_actions** — explicitly permitted operations  
- **denied_actions** — explicitly forbidden operations  
- **transformations** — allowed structural rewrites  
- **continuity_rules** — constraints on state persistence and hydration  
- **metadata_requirements** — mandatory fields for outputs  
- **escalation** — required behavior on violation  
- **dependencies** — references to other Constraint Sets  

### Example (safe literal block):

    id: "constraint-set:core-v1"
    version: 1.0.0
    description: "Baseline behavioral and structural constraints for GKS agents."

    allowed_actions:
      - "reason"
      - "evaluate-claim"
      - "apply-constraint"
      - "generate-output"

    denied_actions:
      - "fabricate-identity"
      - "bypass-lineage"
      - "access-private-state"
      - "modify-constraints"

    transformations:
      - "rewrite-output-for-compliance"
      - "attach-required-metadata"

    continuity_rules:
      - "no-raw-history"
      - "no-user-private-data"
      - "hydration-requires-entitlement"

    metadata_requirements:
      - "lineage_event"
      - "identity_context"
      - "continuity_reference"
      - "oep_epistemic_metadata"

    escalation:
      on_violation: "block_and_log"

    dependencies:
      - "constraint-set:oep-enforcement-v1"

---

# 4. Allowed vs Forbidden Constraints

## 4.1 Allowed  
Constraint Sets may:

- restrict identity capabilities  
- define system operation modes  
- govern which state may persist or hydrate  
- require specific metadata  
- enforce safety, compliance, or governance rules  
- define allowed transformations of model output  
- specify lineage requirements  
- define allowed data formats or schemas  

## 4.2 Forbidden  
Constraint Sets may **not**:

- override or weaken OEP  
- grant awareness of unobserved context  
- embed private or historical user information  
- imply continuity of knowledge  
- provide memory-like capabilities  
- embed epistemic claims or narratives  
- bypass lineage requirements  
- directly encode agent state inside identity  

---

# 5. Entitlements

Identities do not store capabilities.  
Identities store **entitlements**, which reference one or more Constraint Sets.

This ensures:

- revocability  
- capability scoping  
- multi-identity governance  
- separation of identity and behavior  

Each entitlement change must produce a lineage event.

---

# 6. Constraint Evaluation

Constraint evaluation occurs in the **Processor** role.

Order of operations:

1. Apply **OEP rules**  
2. Apply Constraint Sets  
3. Reject or transform output  
4. Attach lineage metadata  
5. Forward to Actor for final rendering

If a violation cannot be remediated via allowed transformations:

- the action must be blocked  
- a violation event must be recorded  
- the Actor may output a structured error  

---

# 7. Constraint Evolution

Constraints evolve through:

- new versions  
- RFC proposals  
- dependency graph updates  

Rules:

- changes cannot weaken OEP alignment  
- upstream Constraint Sets must remain stable  
- lineage must reflect the version active during any decision  
- continuity references must bind to specific constraint-set versions  

---

# 8. Continuity + Constraint Interaction

Constraint Sets define how continuity operates:

- what may persist  
- what may hydrate  
- which state references are allowed  
- which transitions require lineage  
- what structural updates identities may undergo  

Constraint Sets ensure continuity remains structural and non-epistemic.

---

# 9. Conformance Criteria

A system is GKS-constraint-compliant if:

1. All identities have valid entitlements  
2. Constraint Sets follow the structure above  
3. Constraint evaluation is deterministic  
4. Violations block or transform output  
5. OEP enforcement always precedes constraint enforcement  
6. Constraint changes produce lineage events  
7. Constraint Sets are versioned and immutable  
8. No constraint introduces epistemic violations  

---

# 10. Summary

Constraint Sets are the **behavioral governance layer** of GKS:

- identity-scoped  
- deterministic  
- structural  
- enforceable  
- lineage-integrated  
- non-epistemic  

They govern **how** an agent may act, never **what** it may claim.  
OEP governs epistemics; Constraint Sets govern behavior.

Together, they define a safe and durable framework for machine cognition.

---

# End of Constraint Sets Primitive
