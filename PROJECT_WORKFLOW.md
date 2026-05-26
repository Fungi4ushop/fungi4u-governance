PROJECT_WORKFLOW

Purpose:
Ensure work execution and documentation remain aligned.

Lifecycle:

Monitor
↓
Identify Need
↓
Create Engagement
↓
Execute
↓
Validate
↓
Generate Document Outputs
↓
Review Outputs
↓
Replace Documents
↓
Update Business State
↓
Move Outputs To Workspace
↓
Repository Update
↓
Commit / Publication
↓
Operate
↓
Monitor Again

--------------------------------------------------

Execution Gates

Gate 1 — Startup

Required:
[ ] Business Area identified
[ ] Engagement Type identified
[ ] Objective agreed
[ ] Constraints identified
[ ] Inputs identified
[ ] Outputs identified
[ ] Documentation impact identified

Outcome:
Approved to start

--------------------------------------------------

Gate 2 — Execution

Required:
[ ] Work completed
[ ] Validation completed
[ ] Issues recorded

Outcome:
Approved to close

--------------------------------------------------

Gate 3 — Closure

Required:

[ ] Documents generated
[ ] Documents reviewed
[ ] Documents replaced
[ ] Business State updated
[ ] Decisions recorded
[ ] Open actions recorded
[ ] Publication readiness confirmed
[ ] Repository committed
[ ] Publication completed (if applicable)

Outcome:
Engagement complete

--------------------------------------------------

Operating Rules

- Projects change the business
- Operations run the business
- State lives in documents
- Archive is read-only

Document Update Rule

When a change is approved:

1. Identify impacted documents
2. Generate complete replacement content
3. Review generated documents
4. Replace local files
5. Commit
6. Publish

Avoid:

- incremental edit instructions
- searching through chat
- manual reconciliation

Principle:

Approval should result in document outputs rather than editing tasks.

Closure Rule

Workspace Rule

Workspace is temporary execution state.

Repository is managed state.

Publication is optional unless required.

Nothing closes
until documentation alignment is complete.

Publication Rule

Authority updates are not complete until:

1. Documents classified
2. Repository placement decided
3. Local repository updated
4. Changes committed
5. Publication decision executed

Document States:

Unmanaged
Exists outside repository

Managed
Stored in repository

Published
Committed and pushed

Publication options:

Publish:
Add to repository → commit → push

Defer:
Record publication deferral as open action

Archive:
Store outside active repository with ownership recorded

Rules:

- Publication platform does not define truth.
- Repository membership must be intentional.
- Git history is authoritative for published state.
- Deferred publication must be intentional.
- Documents may not remain unmanaged without ownership.
