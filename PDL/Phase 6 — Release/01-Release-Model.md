# Phase 6 — Release
## 01 — Release Model

## Objective
Define the formal model of "Release" within the Platform Delivery Lifecycle (PDL), specifying how a verified system transitions into controlled production activation.

This model separates **deployment mechanics** from **production activation semantics**.

---

## Core Principle

Release is a **state transition of system exposure**, not a technical deployment event.

A system may be deployed but not released.
A system may be released only if explicitly authorized by verification outputs.

---

## 1. Definition of Release

A system is considered RELEASED when:

- Phase 5 verification status is PASS
- Acceptance criteria evaluation is PASS
- Artifact integrity is PASS
- System consistency is CONSISTENT
- Explicit release authorization is granted

---

## 2. Release vs Deployment

### Deployment
- Technical action of moving artifacts into an environment
- Infrastructure-level operation
- May occur in staging or production

### Release
- Logical activation of system functionality in production context
- Governance-level decision
- Requires verification approval

---

## 3. Release States

The system supports the following release states:

```
Prepared → Approved → Deployed → Activated → Released → Monitored
```

### State Definitions

- Prepared: system passes verification
- Approved: governance allows release
- Deployed: system is placed in production environment
- Activated: system is enabled for real traffic
- Released: system is officially in production usage
- Monitored: system is under observability and feedback

---

## 4. Release Activation Model

### Activation Conditions
A system becomes active only if:

- deployment is successful
- feature flags (if any) are enabled
- monitoring systems are operational

### Activation Control
- controlled via configuration or feature gating
- reversible without system redeployment

---

## 5. Release Boundaries

Release boundaries define what is exposed to production users:

- API endpoints
- user-facing features
- external integrations

Non-released components remain:

- disabled
- isolated
- non-executable from production entry points

---

## 6. Release Authorization Model

Release requires explicit authorization from:

- Phase 5 Verification Engine (technical approval)
- Governance layer (policy approval)

No unilateral release is allowed.

---

## 7. Controlled Exposure Strategy

Release follows progressive exposure principles:

- internal release (limited scope)
- pilot release (controlled users)
- full production release

Each stage requires validation before progression.

---

## 8. Rollback Compatibility Requirement

Every release must:

- support full rollback
- preserve previous stable state
- allow reactivation of prior version

Rollback is not optional; it is mandatory.

---

## 9. Key Constraint

> Release is a governance-controlled activation of a verified system, not a deployment artifact.

---

## Next Step
Proceed to:
`02-Deployment-Strategy.md`