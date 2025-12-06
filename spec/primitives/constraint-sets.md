# GKS Primitive: Constraint Sets

**Status:** Stable  
**Maintainer:** Symbia Labs  

Constraint Sets define the permissible actions, transformations, capabilities,
and behaviors of an identity within GKS. They function as the primary behavioral
governance layer for durable, interpretable cognition. Constraint Sets do not
replace or weaken the Open Epistemic Protocol (OEP); they complement it.

---

# 1. Purpose

Constraint Sets specify:

- which actions are permitted  
- which actions are forbidden  
- which transformations of output are allowed  
- what metadata must accompany outputs  
- which continuity operations are allowed  
- boundaries on state hydration  
- escalation rules for violations  

They ensure that behavior remains controlled, deterministic, and compliant,
regardless of model output.

---

# 2. Principles

## 2.1 Constraint-Supremacy  
If a model proposes an action or output that violates a constraint, the system
must block or transform it. Constraints override generated content.

## 2.2 Deterministic Enforcement  
All constraint evaluation must be reproducible and deterministic.

## 2.3 Identity-Scoped  
Constraint Sets are bound to identities via entitlements, not to the model.

## 2.4 Orthogonal to OEP  
OEP governs epistemic claims; Constraint Sets govern behavior.

## 2.5 Versioned and Immutable  
Once published, Constraint Set versions must remain immutable for lineage and
continuity integrity.

---

# 3. Constraint Set Structure

A Constraint Set includes:

- id  
- version  
- description  
- allowed_actions  
- denied_actions  
- transformations  
- continuity_rules  
- metadata_requirements  
- escalation behavior  
- dependencies (optional)  

### Example (safe literal block):

    id: "constraint-set:core-v1"
    version: "1.0.0"
    description: "Baseline behavioral and structural constraints for GKS agents."

    allowed_actions:
      - reason
      - evaluate-claim
      - apply-constraint
      - generate-output

    denied_actions:
      - fabricate-identity
      - bypass-lineage
      - access-private-state
      - modify-constraints

    transformations:
      - rewrite-output-for-compliance
      - attach-required-metadata

    continuity_rules:
      - no-raw-history
      - no-user-private-data
      - hydration-requires-entitlement

    metadata_requirements:
      - lineage_event
      - identity_context
      - continuity_reference
      - oep_epistemic_metadata

    escalation:
      on_violation: block_and_log

    dependencies:
      - constraint-set:oep-enforcement-v1

---

# 4. Allowed vs Forbidden Constraint Content

## 4.1 Allowed  
Constraints may:

- restrict behavior  
- require lineage entries for specific actions  
- define allowed transformations of output  
- govern what structured state may persist or hydrate  
- define metadata requirements  
- define system operation modes  
- enforce compliance or safety policies  

## 4.2 Forbidden  
Constraints may **not**:

- weaken or override OEP  
- grant awareness of unobserved events  
- embed historical user content  
- encode unverifiable knowledge  
- provide implicit memory  
- bypass lineage or continuity rules  
- alter or fabricate identity  

Constraint Sets govern behavior, not knowledge.

---

# 5. Entitlements

Identities do not store behavior.  
Identities store *entitlements*, which reference Constraint Sets.

This ensures:

- revocability  
- minimal coupling  
- fine-grained permission control  
- multi-identity coexistence  

Each entitlement modification is recorded in lineage.

---

# 6. Constraint Evaluation

Constraint evaluation occurs in the **Processor** role.

Execution order:

1. Apply OEP rules  
2. Apply Constraint Sets  
3. Block or transform violations  
4. Attach required metadata  
5. Forward to the Actor role for final rendering  

If a violation cannot be corrected via an allowed transformation, the system must:

- block the action, and  
- record the violation in lineage  

---

# 7. Constraint Evolution

Constraint Sets evolve via:

- new versions  
- RFC processes  
- dependency graph updates  

Rules:

- new versions must not weaken OEP alignment  
- all versions must remain immutable once published  
- lineage must reference specific versions  
- continuity entries must reference constraint versions explicitly  

---

# 8. Continuity + Constraint Interaction

Constraint Sets define:

- what state may persist across episodes  
- what state may hydrate in new episodes  
- which transitions require lineage  
- limits on continuity operations  
- how identities may evolve over time  

Constraint Sets prevent continuity from collapsing into memory.

---

# 9. Conformance Criteria

A system is GKS-constraint-compliant if:

1. Every identity has valid entitlements  
2. Constraint Sets follow the structure above  
3. Violations block or transform model output  
4. Constraint evaluation is deterministic  
5. OEP enforcement always precedes constraint enforcement  
6. All constraint changes generate lineage events  
7. Constraint Sets are versioned and immutable  
8. No constraint introduces epistemic violations  

---

# 10. Summary

Constraint Sets are the **behavioral spine** of GKS:

- identity-scoped  
- deterministic  
- structural  
- enforceable  
- lineage-integrated  
- non-epistemic  

They govern **how an agent may act**, never **what it may claim**.  
OEP governs epistemic boundaries; Constraint Sets govern behavior.

Together, they form the dual-governance system required for durable machine cognition.

---

# End of Constraint Sets Primitive
