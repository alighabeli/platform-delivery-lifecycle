# Capability: Risk Management

## Objective
Define a unified risk management capability within the Platform Delivery Lifecycle (PDL) that identifies, evaluates, mitigates, and monitors risks across all lifecycle phases.

Risk Management ensures the system remains **predictable under uncertainty**.

---

## Core Principle

> Every system failure is a failure to manage risk, not a failure of execution.

Risk Management is a **continuous lifecycle-wide capability**, not a phase-specific activity.

---

## Scope

Risk Management applies across:

- Discovery
- Design
- Planning
- Engineering
- Verification
- Release
- Operations
- Evolution

It is **phase-agnostic and continuously active**.

---

## Risk Lifecycle

### 1. Risk Identification
- Detect potential system risks
- Classify risks (technical, operational, business)

### 2. Risk Assessment
- Evaluate probability
- Evaluate impact
- Assign severity level

### 3. Risk Prioritization
- Rank risks based on severity
- Determine mitigation urgency

### 4. Risk Mitigation
- Define mitigation strategies
- Apply design or process changes

### 5. Risk Monitoring
- Continuously observe risk indicators
- Track risk drift over time

### 6. Risk Closure
- Mark resolved risks
- Archive with traceability

---

## Risk Categories

### Technical Risk
- Architecture failure
- Performance degradation
- Integration failure

### Operational Risk
- Deployment failure
- Monitoring gaps
- Incident recurrence

### Delivery Risk
- Scope creep
- Timeline deviation
- Resource constraints

### Security Risk
- Vulnerabilities
- Threat exposure
- Misconfiguration

### Business Risk
- Market mismatch
- Requirement misalignment
- Value delivery failure

---

## Risk Register Model

Each risk must include:

- Unique ID
- Description
- Category
- Severity (Low / Medium / High / Critical)
- Probability
- Impact
- Owner
- Status
- Mitigation plan
- Trace references

---

## Risk Scoring Model

```text
Risk Score = Probability × Impact
```

Where:

- Probability: 1–5
- Impact: 1–5

---

## Integration with PDL Phases

### Discovery
- Early risk discovery

### Design
- Architectural risk modeling

### Planning
- Delivery risk forecasting

### Engineering
- Implementation risk control

### Verification
- Risk validation via testing

### Release
- Release risk gating

### Operations
- Runtime risk monitoring

### Evolution
- Long-term risk reduction

---

## Key Constraints

- No risk may remain untracked
- All critical risks must have mitigation strategies
- Risk state must be continuously updated

---

## Outputs (Artifacts)

- Risk Register
- Risk Assessment Reports
- Mitigation Plans
- Risk Dashboards

---

## Success Criteria

Risk Management is effective when:

- Risks are identified early
- Risk exposure is continuously reduced
- No unmanaged critical risks exist in production

---

## Next Step
Proceed to:
`02-Change-Management`