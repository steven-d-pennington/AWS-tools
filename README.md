# AWS Inspector Operations Platform Planning Repo

This repository houses the coordinated build plan for the AWS Inspector operations platform. It captures the implementation strategy, workstream trackers, and operational guidance required to deliver the end-to-end system across presentation, ingestion, storage, processing, admin, security, and deployment domains.

## Repository Structure
| Path | Description |
| --- | --- |
| `stack-plan.md` | Approved high-level stack implementation plan captured during initial planning. |
| `system-rebuild-guide.md` | Source guidance document informing requirements (read-only reference). |
| `docs/master-build-tracker.md` | Master program management tracker for orchestrating all workstreams. |
| `docs/subtasks/` | Individual workstream trackers with task boards, milestones, and update logs. |

Future artefacts such as runbooks, research, and architecture diagrams should be stored in the suggested subdirectories referenced throughout the trackers (e.g., `docs/runbooks/`, `docs/architecture/`, `docs/research/`). Create directories as needed when contributing.

## How to Use the Trackers
1. **Start with the master tracker:** Review `docs/master-build-tracker.md` to understand overall status, owners, and cross-workstream dependencies.
2. **Claim work:** Update the relevant `Primary Owner` field in the master tracker and the `Owner` field in the corresponding subtask file.
3. **Maintain status fidelity:** After each working session, update status columns and the `Last Update` field in the master tracker and append a dated entry to the subtask’s Update Log summarizing progress, blockers, and next steps.
4. **Link artefacts:** When producing designs, diagrams, or runbooks, store them in the repo (or link to external tools) and reference them in the Notes/Links column of the relevant task.
5. **Escalate blockers:** Use the Risk & Issue Log in the master tracker to highlight cross-cutting concerns. Escalations should also appear in the subtask Notes field with mitigation steps.

## Status Vocabulary
All trackers share the same status vocabulary to simplify orchestration:
- **Not Started** — Work item has not begun; available for pickup.
- **In Progress** — Work is actively underway.
- **Blocked** — Progress halted pending dependency resolution.
- **Error** — Execution failed; remediation required before proceeding.
- **Complete** — Acceptance criteria met and validated.

## Contribution Workflow
- **Editing:** Update markdown files directly and ensure tables remain valid. Maintain chronological order in Update Logs.
- **Decision Logging:** Record significant architectural or product decisions in the relevant Notes sections and, if cross-cutting, in the Program Operations risk log.
- **Runbooks & Documentation:** Store operational documents under `docs/runbooks/` and link them from the workstream trackers.
- **Change Management:** Any scope or requirement changes must be logged in the master tracker’s Change Management section and propagated to affected subtask documents.

## Onboarding Checklist for New Contributors
- Read `system-rebuild-guide.md` to absorb context.
- Review `stack-plan.md` for the agreed architectural direction.
- Study `docs/master-build-tracker.md` for current priorities and ownership.
- Select a subtask file, review its mission and milestones, and update the `Owner` field when claiming work.
- Confirm security and compliance requirements with the Security workstream before handling sensitive data or integrations.

## Communication Expectations
- Daily async updates should be captured via tracker edits; no separate standup doc is required unless noted.
- Weekly stakeholder summaries should aggregate workstream highlights and be archived under `docs/reports/` once created.
- Major decisions or escalations must be highlighted in both the master tracker and relevant subtask Notes sections for traceability.

## Questions & Clarifications
Outstanding clarifications (e.g., tech stack preferences, authentication scope, export priorities, backup cadence, ingest volume) are tracked under Program Operations in the master tracker. When answers are obtained, update both the master tracker and any affected subtasks.

