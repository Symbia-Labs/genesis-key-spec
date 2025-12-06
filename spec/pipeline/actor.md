# GKS Pipeline Role: Actor

**Status:** Stable  
**Maintainer:** Symbia Labs  

The **Actor** is the final role in the GKS Execution Pipeline.  
It renders outputs **after** all epistemic, behavioral, and structural rules have
been enforced by the Processor.

The Actor is not a reasoning component.  
It is a *presentation layer* responsible for ensuring that final system output:

- complies with OEP  
- respects Constraint Sets  
- preserves lineage  
- remains structurally valid  
- maintains uncertainty discipline  
- never fabricates awareness  
- never leaks structural or private state  

The Actor is the last and strictest gate before output becomes visible externally.

---

# 1. Purpose

The Actor exists to:

1. Render Processor-approved output  
2. Ensure compliance with all constraints  
3. Apply any required transformations (allowed via constraints)  
4. Attach final metadata  
5. Prevent leakage of identity, continuity, or lineage internals  
6. Maintain epistemic discipline in all final phrasing  
7. Produce lineage events for the completion of an episode  

The Actor guarantees that no unvetted content escapes the Execution Layer.

---

# 2. Actor Principles

## 2.1 Non-Generative by Default  
The Actor does not create new semantic content unless the Processor has explicitly
allowed a transformation.

## 2.2 Deterministic Rendering  
Given the same validated output object, the Actor renders the same final output.

## 2.3 Structural Transparency  
No hidden information from the Execution Layer may leak into external output.

## 2.4 Epistemic Compliance  
All outputs must conform to OEP’s uncertainty, hypothetical, and non-awareness rules.

## 2.5 Constraint Compliance  
The Actor must obey all constraints related to rendering.

## 2.6 Minimalism  
The Actor should add nothing not required by constraints or epistemic discipline.

---

# 3. Actor Responsibilities

The Actor must:

1. Accept validated Processor output  
2. Apply permitted transformations  
3. Render hypotheses, uncertainty markers, or caveats as required  
4. Attach required metadata (if user-visible)  
5. Strip internal metadata not intended for exposure  
6. Produce lineage entries  
7. Output the final external representation  

The Actor never decides whether output is allowed — that is the Processor’s role.

---

# 4. Actor Input Structure

The Actor receives a **validated output object** from the Processor.  
It contains:

- output_id  
- rewritten or approved content  
- applied constraints  
- identity context  
- continuity anchors  
- lineage event references  
- compliance metadata  
- allowed transformations  

### Example (safe literal block):

    output_id: "output:017"
    content: "Based on the available input, here are the possibilities..."
    applied_constraints:
      - constraint-set:core-v1
    identity_context: "gks:agent:92f8b3e7"
    continuity_context:
      anchor: "cont:2025-01-01T12:00Z"
    lineage_event: "event:042"
    allowed_transformations:
      - render-uncertainty
      - attach-oep-metadata

The Actor renders this content **without adding unauthorized semantics**.

---

# 5. Output Rendering Rules

The Actor must:

### 5.1 Preserve Uncertainty  
If the Processor indicates uncertainty, the Actor must express it explicitly.

### 5.2 Preserve Hypothesis Labels  
OEP hypothesis structures must remain intact.

### 5.3 Prevent Awareness Fabrication  
The Actor must not phrase output in a way that implies:

- unobserved access  
- model continuity of knowledge  
- identity-level memory  
- awareness of user behavior not permitted by OEP  
- hidden internal state  

### 5.4 Apply Allowed Transformations Only  
Transformations must be explicitly listed in the Processor output.

Allowed examples (if permitted by constraints):

- rewriting for clarity  
- attaching uncertainty or provenance metadata  
- removing unsafe fragments  
- formatting for readability  

Forbidden examples:

- generating new unverifiable claims  
- injecting new hypotheses  
- adding narrative bridges  
- softening or strengthening meaning  

---

# 6. Presentation Discipline

The Actor ensures that:

- content is phrased in OEP-compliant language  
- uncertainty markers are explicit  
- no private structural metadata is visible  
- content does not imply continuous awareness  
- no identity or continuity secrets leak  
- no Processor internals leak  

### Never reveal:

- identity internals  
- continuity state  
- lineage details  
- constraint set internals  
- enforcement logic  
- model internals  

The Actor is a **rendering boundary**, not an explanation engine.

---

# 7. Lineage Integration

Every Actor output must generate a lineage entry describing:

- which identity invoked the output  
- which constraints were in force  
- which transformations were applied  
- which continuity anchors were referenced  
- which event IDs were consumed  

### Example (safe literal block):

    event_type: "render-output"
    output_id: "output:017"
    identity: "gks:agent:92f8b3e7"
    applied_constraints:
      - "constraint-set:core-v1"
    continuity_context:
      anchor: "cont:2025-01-01T12:00Z"

---

# 8. Forbidden Actor Behavior

The Actor must never:

- invent new semantic content  
- override Processor decisions  
- re-interpret claims  
- alter constraints  
- generate epistemic claims  
- leak identity or continuity internals  
- expose lineage contents  
- merge or rewrite identity  
- admit or imply unbounded memory  
- imply awareness of user context not in the current episode  

The Actor is a controlled funnel — not a reasoning component.

---

# 9. Conformance Criteria

A system is GKS-actor-compliant if:

1. All rendered output originates from Processor-approved content  
2. Only allowed transformations are performed  
3. No epistemic boundaries are violated  
4. No behavioral constraints are violated  
5. Final phrasing maintains OEP-compliant uncertainty  
6. No structural information is leaked  
7. Lineage entries are generated for all outputs  
8. Rendering is deterministic and minimal  

---

# 10. Summary

The Actor is the **final gate** of the Execution Layer.

It:

- renders  
- formats  
- attaches metadata  
- preserves uncertainty  
- blocks unsafe phrasing  
- ensures external alignment  
- logs lineage  

It does **not** reason, infer, reinterpret, or generate.

The Actor converts safe structure into safe expression — nothing more, nothing less.

---

# End of Actor Role
