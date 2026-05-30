REPOSITORY_MAP

Purpose:
Describe how business information is organised and where authority resides.

Principles:

* Business owns structure
* Projects are temporary
* Operations persist
* Documents have one owner
* State is recorded in documents
* Archive is read-only

---

Repository Roles

Constitutional Governance Repository

Repository:
operational-core

Authority:
Constitutional

Purpose:

* Constitution
* Vision
* Amendments
* Governance standards
* Document register
* Framework models

Contains:

* CONSTITUTION.md
* VISION.md
* AMENDMENTS.md
* DOCUMENT_REGISTER.md
* WORK_MOVEMENT_MODEL.md
* Architecture templates

Must Not Contain:

* Runtime systems
* Domain implementation
* Operational state

---

Operational Governance Repository

Repository:
fungi4u-governance

Authority:
Operational Governance

Purpose:

* Business state
* Decisions
* Open actions
* Engagement process
* Governance workflows
* Lifecycle operation

Contains:

* BUSINESS_STATE.md
* DECISION_LOG.md
* OPEN_ACTIONS.md
* START_HERE.md
* ENGAGEMENT_START.md
* PROJECT_WORKFLOW.md
* LIFECYCLE_MODEL.md
* OPERATING_SYSTEM_GLOSSARY.md
* EVOLUTION_PATH.md

Must Not Contain:

* Domain implementation artifacts
* Runtime systems

---

Implementation Repository

Repository:
stock-control

Authority:
Inherited from Governance

Purpose:

Implement governed systems.

Contains:

* Systems authority stack
* Architecture
* Allocation
* Operational controls
* Implementation documents

Must Not Contain:

* Constitutional governance
* Governance decisions
* Strategic doctrine

---

Authority Relationships

operational-core
governs governance framework

↓

fungi4u-governance
governs business operation

↓

stock-control
implements approved systems

---

Workspace Layers

Authority Layer

Owns approved truth.

Examples:

* Constitution
* Business State
* Decision Log
* Systems Authority Stack

Workspace Layer

Performs work.

Examples:

* Local repositories
* Working documents
* Generated outputs

Interaction Layer

Enables engagement.

Examples:

* ChatGPT
* Linux desktop
* Mobile devices

Publication Layer

Publishes state.

Examples:

* Git
* GitHub

---

Work Movement

Interaction
↓
Workspace
↓
Repository
↓
Commit / Publication
↓
Operation
↓
Monitor

Principles

* Chat enables engagement
* Workspace performs work
* Repository stores managed state
* Publication distributes state
* Operation executes approved state
* Monitoring initiates future work

---

Status:

Repository model validated through operational use.

Last Updated:
2026-05-30

