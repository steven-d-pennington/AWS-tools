# Workstream Tracker — Ingestion Pipeline

## Mission
Engineer the end-to-end ingestion flow for AWS Inspector exports, covering upload intake, staging, validation, chronological enforcement, normalization, and progress telemetry to support large (≈100 MB+) batches.

## Current Status
- **Owner:** Unassigned
- **Status:** Not Started
- **Last Update:** _None_

## Milestones & Target Outcomes
| Milestone | Description | Target Exit Criteria | Status | Notes |
| --- | --- | --- | --- | --- |
| Intake Design | Define upload channels (UI/API), payload limits, validation rules, and chronological enforcement strategy. | Architecture diagram and decision log attached here. | Not Started | Coordinate with Security on sanitization requirements. |
| Staging & Storage Implementation | Build durable staging storage, metadata recording, and duplicate detection. | Staging service deployed locally with automated tests. | Not Started | Ensure idempotent retries documented. |
| Normalization & Processing | Implement parsers, normalization pipelines, transactional writes, and derived metric computation. | Processing jobs successful against sample datasets with benchmarks logged. | Not Started | Align schema with Data Storage workstream. |
| Telemetry & Error Handling | Provide progress tracking, retry logic, and failure reporting hooks. | Telemetry endpoints and dashboards operational; error taxonomy documented. | Not Started | Feed metrics to Admin workstream. |
| Handoff & Documentation | Deliver API/CLI interface specs, runbooks, and onboarding guides. | README and runbook updated; integration tests passing. | Not Started | Link to supporting artefacts below. |

## Task Board
| Task | Owner | Dependencies | Status | Notes/Links |
| --- | --- | --- | --- | --- |
| Confirm upload SLA targets and concurrency expectations with stakeholders. | Unassigned | Program Ops clarifications | Not Started | Record in Update Log once received. |
| Define file validation schemas (JSON, CSV, other formats). | Unassigned | Sample AWS Inspector exports | Not Started | Version schemas in repo. |
| Design chronological enforcement using report timestamps and advisory locks. | Unassigned | Data Storage schema decisions | Not Started | Document algorithm in `/docs/architecture/ingestion.md`. |
| Implement streaming parser for large CSV/JSON payloads. | Unassigned | Parser library selection | Not Started | Capture benchmarks. |
| Build staging persistence (object storage or filesystem) with cleanup policies. | Unassigned | Deployment constraints | Not Started | Include retention schedule. |
| Create normalization workers with transactional writes to core tables. | Unassigned | Database schema | Not Started | Coordinate with Background Processing for job queue selection. |
| Instrument ingestion lifecycle telemetry (queued, processing, completed, failed). | Unassigned | Observability stack | Not Started | Ensure data feeds admin dashboards. |
| Establish failure handling playbooks and alerting thresholds. | Unassigned | Monitoring tools | Not Started | Share runbook link. |
| Provide API endpoints for upload submission and status polling. | Unassigned | Presentation/API requirements | Not Started | Document in OpenAPI spec. |
| Write automated tests covering happy paths, large file benchmarks, and failure scenarios. | Unassigned | Test framework | Not Started | Add performance metrics to Update Log. |

## Dependencies
- Database schema ownership from Data Storage workstream.
- Job orchestration decisions from Background Processing workstream.
- Security requirements for input sanitization and rate limiting.

## Acceptance Criteria Checklist
- [ ] Upload paths handle ≥100 MB files within agreed SLA (<5 minutes target).
- [ ] Chronological ordering and duplicate detection rules enforced and documented.
- [ ] Telemetry surfaces ingestion metrics for Admin dashboards.
- [ ] Comprehensive runbook covering retries, failures, and rollback procedures.
- [ ] Integration tests with Presentation Layer and exports validated.

## Update Log
| Date | Author | Summary |
| --- | --- | --- |

