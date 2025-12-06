# Genesis Key Specification (GKS)

A public specification for the primitives of durable machine cognition.  
GKS defines identity, continuity, constraint, and lineage structures used by
the Symbia Execution Layer and any system that requires persistent, accountable
reasoning across sessions and contexts.

GKS aligns directly with the Open Epistemic Protocol (OEP).  
OEP defines epistemic boundaries.  
GKS defines the execution substrate built on top of them.

---

## Purpose

The Genesis Key Specification formalizes the foundational elements required to
move from isolated, stateless model predictions to durable, structured,
long-horizon machine cognition.

While OEP governs *what a system may claim*,  
GKS governs *how a system persists, identifies, constrains, and evolves over time*.

GKS introduces four core primitives:

1. **Identity** — stable, portable representations for agents and users  
2. **Continuity** — cognitive structures that survive across episodes  
3. **Constraint Sets** — rules and entitlements that bound agent behavior  
4. **Lineage** — event sourcing, traceability, and provenance across interactions

---

## Relationship to OEP

GKS is built upon and extends the Open Epistemic Protocol.

### OEP provides:
- Claim classes  
- Observability boundaries  
- Enforcement rules  
- Uncertainty and provenance discipline  
- Anti-hallucination safeguards  

### GKS adds:
- Identity models (e.g., Symbikey primitives)  
- Continuity constructs  
- Constraint and entitlement graphs  
- Execution roles (Observer, Interpreter, Processor, Actor)  
- Lineage and persistent-state descriptions  

Together, these layers define the foundations for next-generation AI systems
capable of durable, interpretable cognition.

See `spec/alignment-oep.md` for detailed mapping.

---

## Repository Structure
spec/
gks-v1.0.md
alignment-oep.md
primitives/
identity.md
continuity.md
constraint-sets.md
lineage.md
pipeline/
observer.md
interpreter.md
processor.md
actor.md

examples/
sample-identity-key.yaml
constraint-set-example.yaml
lineage-trace.json

rfc/
TEMPLATE.md
INDEX.md

LICENSE
README.md

---

## Versioning

GKS follows semantic versioning:

- **MAJOR** — breaking changes to primitives or semantics  
- **MINOR** — new optional primitives or fields  
- **PATCH** — clarifications or minor corrections  

Canonical specification lives in `spec/gks-v1.0.md`.

---

## RFC Process

Changes to GKS require:

1. Opening an issue describing the proposed change  
2. Drafting an RFC using `rfc/TEMPLATE.md`  
3. Submitting a pull request containing the RFC  
4. Public discussion and review  
5. Maintainer approval  
6. Spec updates and version increment  

Current RFCs appear in `rfc/INDEX.md`.

---

## Contributing

Contributions are welcome.  
Before submitting, review:

- `rfc/TEMPLATE.md`  
- `spec/alignment-oep.md`  

All contributions must align with OEP and maintain internal consistency of
identity, continuity, constraint, and lineage primitives.

By contributing, you agree to the Apache 2.0 license.

---

## License

The Genesis Key Specification is released under the  
**Apache License 2.0**, included in this repository.

---

## Status

GKS is an evolving open specification.  
It forms the conceptual basis of the Symbia Execution Layer and is intended for:

- agent architects  
- reasoning-system designers  
- AI safety researchers  
- distributed cognition frameworks  
- identity-aware AI systems  

Feedback and participation are encouraged.
