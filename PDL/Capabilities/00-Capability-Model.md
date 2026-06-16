# Capability Model

## Objective
Define the capability architecture of the Platform Delivery Lifecycle (PDL).

Capabilities represent persistent management concerns that span multiple lifecycle phases and ensure continuity, governance, and operational integrity across the entire delivery system.

---

## Core Principle

A capability is a lifecycle-independent management function.

While phases describe:

> When work happens

Capabilities describe:

> What concerns must be continuously managed

---

## PDL Meta-Model

```text
Vision
    ↓
Lifecycle Phases
    ↓
Capabilities
    ↓
Artifacts
    ↓
Verification
```

---

## Fundamental Dimensions

### Phase

Defines:
- sequence
- progression
- lifecycle timing

Question answered:

> When does this happen?

---

### Capability

Defines:
- ownership
- policies
- controls
- management responsibilities

Question answered:

> What is being managed?

---

### Artifact

Defines:
- evidence
- traceability
- state representation

Question answered:

> What proves it happened?

---

## Capability Characteristics

A valid capability must:

### Persistent
Remain active across multiple phases.

### Governed
Operate according to explicit policies.

### Measurable
Expose measurable outcomes.

### Traceable
Produce auditable artifacts.

### Verifiable
Support validation and compliance checks.

---

## Capability Structure

Each capability must define:

- Purpose
- Scope
- Lifecycle Coverage
- Ownership
- Policies
- Artifacts
- Metrics
- Maturity Model

---

## Lifecycle Coverage Model

Capabilities may span:

Discovery → Design → Planning → Engineering → Verification → Release → Operations → Evolution

Coverage is explicitly declared.

---

## Capability Ownership

Each capability must have:

- Accountable Owner
- Contributing Roles
- Governance Authority

---

## Capability Artifact Model

Each capability produces artifacts such as:

- Risk Register
- Change Request
- Security Assessment
- Configuration Baseline
- Knowledge Record
- Governance Decision

Artifacts must follow PDL versioning and integrity rules.

---

## Capability Metrics

Capabilities expose indicators such as:

- Risk Exposure
- Change Success Rate
- Security Findings
- Configuration Drift
- Knowledge Coverage
- Policy Compliance

---

## Capability Maturity

- Level 1 — Ad Hoc
- Level 2 — Managed
- Level 3 — Defined
- Level 4 — Measured
- Level 5 — Optimized

---

## Initial Core Capability Catalog

- Risk Management
- Change Management
- Security Management
- Configuration Management
- Knowledge Management
- Governance Management

---

## Key Constraint

Every lifecycle phase must be governed by one or more capabilities, and every capability must produce verifiable artifacts.

---

## Next Step
Proceed to Capabilities/01-Risk-Management