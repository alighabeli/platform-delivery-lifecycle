# Phase 2 — Data Model

## Objective
Define the structural data foundation of the Platform Delivery Lifecycle (PDL), including artifact schemas, versioning strategy, lifecycle state management, and storage boundaries.

This model ensures **data consistency, traceability, and deterministic evolution of all system artifacts**.

---

## 1. Core Data Entities

### 1.1 Artifact Entity
The central unit of data in PDL.

**Fields:**
- `artifact_id` (string, unique)
- `name` (string)
- `type` (enum: Vision | Problem | Stakeholder | DomainModel | Architecture | Requirement | TestReport | etc.)
- `version` (semver-like: v1, v1.1, v2)
- `status` (Draft | InReview | Approved | Deprecated)
- `phase` (Discovery | Design | Planning | Engineering | Verification | Release | Operations | Evolution)
- `content` (markdown / structured document)
- `created_at` (timestamp)
- `updated_at` (timestamp)
- `created_by` (stakeholder_role)
- `checksum` (hash of content for immutability verification)

---

### 1.2 Lifecycle Phase Entity
Represents a controlled stage of delivery.

**Fields:**
- `phase_id`
- `name`
- `order_index`
- `entry_criteria`
- `exit_criteria`

---

### 1.3 Stakeholder Role Entity
Defines system actors with permissions.

**Fields:**
- `role_id`
- `name`
- `permissions[]`
- `owned_artifact_types[]`

---

### 1.4 Decision Gate Entity
Represents validation checkpoints between phases.

**Fields:**
- `gate_id`
- `from_phase`
- `to_phase`
- `required_artifacts[]`
- `validation_rules[]`
- `approval_roles[]`

---

## 2. Artifact Versioning Model

### Versioning Rules
- Every artifact is immutable once status = Approved
- Updates always create a new version
- Previous versions remain accessible but marked as Deprecated

### Version Format
- v1 → initial
- v1.1 → minor update
- v2 → major structural change

### Version Lineage
Each artifact maintains:
- `parent_version_id`
- `change_reason`
- `diff_metadata`

---

## 3. Lifecycle State Machine

### Artifact States
```
Draft → InReview → Approved → Deprecated
```

### Transition Rules
- Draft → InReview: author submission
- InReview → Approved: stakeholder validation
- Approved → Deprecated: replaced by new version

### Constraint
No Approved artifact can be modified directly.

---

## 4. Storage Model

### Hybrid Storage Architecture

#### 4.1 Git-Based Storage (Primary Source of Truth)
- Stores artifact content (markdown/specs)
- Provides version history
- Enables auditability

#### 4.2 Metadata Store (Structured DB)
- Stores artifact index
- Stores lifecycle states
- Stores relationships and references

#### 4.3 Optional Event Log
- Stores lifecycle transitions
- Stores gate validations
- Used for observability and analytics

---

## 5. Consistency Model

### Strong Consistency Rules
- Artifact status changes must be atomic
- Gate validation must be complete before phase transition
- Version updates must be checksum-verified

### Eventual Consistency Areas
- Observability metrics
- Analytics and reporting
- Cross-system integrations

---

## 6. Traceability Model

Every artifact must maintain:
- Source linkage (Vision → Requirement → Architecture → Code)
- Version lineage
- Decision history

This ensures full lifecycle traceability.

---

## 7. Integrity Constraints

- No orphan artifacts (every artifact belongs to a phase)
- No unversioned modifications
- No phase transition without valid gate approval
- No role-based action outside permissions

---

## 8. Key Design Principle

The Data Model enforces that:
> The system is not a collection of documents — it is a versioned, stateful, and governed knowledge graph.

---

## Next Step
Proceed to Phase 2 — UX / Interaction Model (05-UX-Model.md)
