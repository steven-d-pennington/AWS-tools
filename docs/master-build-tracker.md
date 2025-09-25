# AWS Inspector Ops Platform — Master Build Tracker

This master tracker translates the approved stack implementation plan into an executable program of work. It is designed for orchestration agents to coordinate specialist contributors across the full build lifecycle while maintaining clear visibility into status, ownership, and dependencies.

## Status Legend
- **Not Started** — No active work yet; ready for pickup.
- **In Progress** — Work has begun but is not yet complete.
- **Blocked** — Work is paused pending resolution of a dependency or issue.
- **Error** — Work encountered a failure that requires remediation or escalation.
- **Complete** — Work has met the acceptance criteria and is ready for QA/next stage.

## Workstream Overview
| Workstream | Scope Summary | Primary Owner | Current Status | Last Update |
| --- | --- | --- | --- | --- |
| [Program Operations](#program-operations) | Cross-cutting PMO duties, clarifications, decision tracking, and release readiness. | Unassigned | Not Started | _None_ |
| [Presentation Layer](subtasks/presentation-layer.md) | Web UI, accessibility, workflow UX, and public API surface. | Unassigned | Not Started | _None_ |
| [Ingestion Pipeline](subtasks/ingestion-pipeline.md) | Upload intake, staging, normalization, and processing orchestration. | Unassigned | Not Started | _None_ |
| [Data Storage & Modeling](subtasks/data-storage-modeling.md) | Relational schema design, migrations, indexing, and provenance rules. | Unassigned | Not Started | _None_ |
| [Background Processing & Exports](subtasks/background-processing-exports.md) | Async job platform, export generation, archival workflows, telemetry. | Unassigned | Not Started | _None_ |
| [Admin & Telemetry Surfaces](subtasks/admin-telemetry.md) | Admin console, health probes, monitoring, and audit logging. | Unassigned | Not Started | _None_ |
| [Security & Compliance](subtasks/security-compliance.md) | Secure handling of uploads, secrets management, auth strategy, and governance. | Unassigned | Not Started | _None_ |
| [Deployment & Operations](subtasks/deployment-operations.md) | Docker delivery, environment configuration, scaling, backups, DR, and release validation. | Unassigned | Not Started | _None_ |

> **Update protocol:** Orchestration agents must update the table after each working session by editing the `Current Status` and `Last Update` columns and linking to the relevant progress notes in the associated subtask file.

## Program Operations
**Objectives**
- Centralize decision logs, clarifications, and cross-workstream risks.
- Ensure clarifying questions from the stack plan are resolved and recorded.
- Coordinate timelines, release readiness reviews, and stakeholder communications.

**Key Tasks**
| Task | Owner | Dependencies | Status | Notes |
| --- | --- | --- | --- | --- |
| Capture responses to outstanding clarifying questions (tech stack, auth scope, export priorities, backup cadence, ingest volume). | Unassigned | Stakeholder input | Not Started | Document answers in this section and relevant subtask(s). |
| Establish intake process for new requirements, scope changes, and risk escalations. | Unassigned | None | Not Started | Define SLA for responses and update README if process changes. |
| Maintain master delivery timeline and sprint/iteration plan. | Unassigned | All workstreams | Not Started | Create `docs/schedule.md` if timeline detail exceeds this tracker. |
| Publish weekly stakeholder status summaries referencing each workstream. | Unassigned | Workstream updates | Not Started | Archive summaries in `/docs/reports/` if generated. |

**Communication Cadence**
- Daily async update posted via tracker edits.
- Twice-weekly standup (or written equivalent) summarizing blockers.
- Release readiness review at end of each major milestone.

## Dependencies & Coordination
- **Shared Environments:** Data modeling, ingestion, and background processing must align on schema versioning—coordinate migrations via change control documented in the Data Storage subtask.
- **API Contracts:** Presentation Layer and Admin tooling depend on API endpoints specified by Ingestion and Background Processing—ensure OpenAPI/GraphQL schemas are versioned and reviewed before implementation.
- **Security Sign-off:** No deployment workstream tasks may reach _Complete_ status without Security & Compliance review notes recorded in both trackers.

## Risk & Issue Log
| Risk/Issue | Impact | Owner | Mitigation/Next Steps | Status |
| --- | --- | --- | --- | --- |
| Pending stakeholder decisions on authentication, export priority, backup cadence, and ingest volume sizing. | Medium | Program Operations | Follow up with stakeholders; record decisions once received. | Not Started |

## Deliverable Acceptance Checklist
- [ ] All workstream subtasks show **Complete** status with supporting QA evidence or links to verification artefacts.
- [ ] README reflects final deployment/operational guidance and any deviations from this plan.
- [ ] Security & Compliance sign-off documented for ingestion, storage, admin, and deployment workstreams.
- [ ] Release notes drafted and approved by stakeholders.

## Change Management
Any adjustments to scope, timelines, or acceptance criteria must be:
1. Logged under **Risk & Issue Log** with new status.
2. Communicated to affected workstream leads via their subtask documents.
3. Reflected in the **Workstream Overview** table and, if necessary, the README.

## Artifacts & Links
- [Stack Implementation Plan](../stack-plan.md)
- [System Rebuild Guide](../system-rebuild-guide.md)
- Subtask trackers under `docs/subtasks/`

