# Phase 7 — Operations
## Capability: Monitoring Framework

## Objective
Define a structured Monitoring Framework within the Platform Delivery Lifecycle (PDL) that transforms observability signals into actionable operational decisions through SLI, SLO, SLA, and alerting systems.

Monitoring ensures the system is not only observable, but also **actively controlled through defined reliability targets**.

---

## Core Principle

> Observability tells you what is happening. Monitoring tells you what matters.

Monitoring is the decision layer on top of observability signals.

---

## Scope

The Monitoring Framework applies to all runtime environments:

- Production systems
- Critical staging environments
- High-fidelity pre-production systems

---

## Monitoring Hierarchy

### 1. SLIs (Service Level Indicators)
Define measurable system behaviors.

Examples:
- Request latency
- Error rate
- Throughput
- Availability

SLIs are **raw measurements derived from observability data**.

---

### 2. SLOs (Service Level Objectives)
Define target thresholds for SLIs.

Examples:
- 99.9% request success rate
- < 200ms p95 latency
- < 1% error rate

SLOs represent **acceptable system behavior boundaries**.

---

### 3. SLAs (Service Level Agreements)
Define contractual obligations based on SLOs.

Includes:
- Business commitments
- Penalty conditions
- External guarantees

SLAs are **externalized reliability promises**.

---

## Alerting Model

### 1. Signal-Based Alerts
Triggered when SLI deviates from expected thresholds.

### 2. SLO Burn Alerts
Triggered when error budget consumption exceeds safe limits.

### 3. Anomaly Alerts
Triggered by deviation from historical behavioral patterns.

---

## Error Budget Model

Error budget defines allowable failure tolerance.

```text
Error Budget = 1 - SLO
```

Example:
- SLO = 99.9%
- Error Budget = 0.1%

---

## Alert Severity Levels

### Critical
- Immediate system failure risk
- Requires immediate response

### High
- Degradation of service
- Requires urgent intervention

### Medium
- Performance degradation
- Requires scheduled attention

### Low
- Informational signals
- No immediate action required

---

## Monitoring Layers

### Infrastructure Monitoring
- CPU, memory, disk, network
- Node and cluster health

### Application Monitoring
- API performance
- Service dependencies
- Error rates

### Business Monitoring
- Transaction success rate
- Revenue-impacting failures
- User journey completion

---

## Integration with Observability

Monitoring consumes observability signals:

- Metrics → SLI computation
- Logs → anomaly detection
- Traces → bottleneck identification

---

## Integration with PDL Capabilities

### Risk Management
- Detect risk exposure via SLO breaches

### Change Management
- Validate impact of deployments on SLOs

### Security Management
- Detect abnormal system behavior patterns

### Configuration Management
- Monitor configuration-induced deviations

### Knowledge Management
- Convert incidents into operational learning

### Governance Management
- Enforce reliability policies and thresholds

---

## Monitoring Outputs

- Dashboards (SLO health views)
- Alert streams
- Error budget reports
- Reliability reports
- Incident triggers

---

## Key Constraints

- Every critical service must define SLIs
- Every SLI must have an SLO
- No production system may operate without defined alerting rules
- Alerts must map to actionable responses

---

## Success Criteria

Monitoring is effective when:

- System health is continuously measurable
- SLO violations are detected early
- Alerts are actionable, not noisy
- Reliability trends are visible over time

---

## Relationship to Observability

Observability provides raw data.
Monitoring provides **decision logic** on top of that data.

---

## Next Step
Proceed to:
`03-Incident-Management.md`