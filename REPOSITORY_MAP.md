REPOSITORY_MAP

Purpose:
Describe how business information is organised.

Principles:
- Business owns structure
- Projects are temporary
- Operations persist
- Documents have one owner
- State is recorded in documents
- Archive is read-only

Target Business Workspace:

Business
├── Governance
├── Operations
├── Projects
├── Systems
├── Data
└── Archive

Document Ownership:
--------------------------------------------------

Repository Roles

Governance Repository

Purpose:
Define governing principles.

Repository:
operational-core

Authority:
Constitutional

Contains:
Constitution
Vision
Architecture declarations
Amendments
Governance standards

Must Not Contain:
Implementation artifacts
Runtime systems
Operational state


Implementation Repository

Purpose:
Implement governed systems.

Repository:
stock-control

Domain:
Economic Governance Domain

Authority:
Inherited from Governance

Contains:
Architecture
Migrations
Infrastructure
Operational execution

Must Not Contain:
Governance authority
Constitution amendments
Strategic doctrine


Relationship

operational-core
governs

↓

stock-control
implements

--------------------------------------------------

Workspace Layers

Authority Layer

Purpose:
Own approved truth.

Examples:
Business State
Decision Log
Constitution


Workspace Layer

Purpose:
Perform controlled work.

Examples:
Local Linux repositories
Generated outputs
Working documents


Interaction Layer

Purpose:
Enable engagement.

Examples:
ChatGPT
Android
Linux desktop


Publication Layer

Purpose:
Publish and recover state.

Examples:
Git
GitHub


Rules

Authority is independent of platform.

Work may occur from any device.

Durable outputs return to workspace.

Git manages history.

Publication does not define truth.
--------------------------------------------------

Repository Roles

Governance Repository

Purpose:
Define governing principles.

Repository:
operational-core

Authority:
Constitutional

Contains:
Constitution
Vision
Architecture declarations
Amendments
Governance standards

Must Not Contain:
Implementation artifacts
Runtime systems
Operational state


Implementation Repository

Purpose:
Implement governed systems.

Repository:
stock-control

Domain:
Economic Governance Domain

Authority:
Inherited from Governance

Contains:
Architecture
Migrations
Infrastructure
Operational execution

Must Not Contain:
Governance authority
Constitution amendments
Strategic doctrine


Relationship

operational-core
governs

↓

stock-control
implements

--------------------------------------------------

Workspace Layers

Authority Layer

Purpose:
Own approved truth.

Examples:
Business State
Decision Log
Constitution


Workspace Layer

Purpose:
Perform controlled work.

Examples:
Local Linux repositories
Generated outputs
Working documents


Interaction Layer

Purpose:
Enable engagement.

Examples:
ChatGPT
Android
Linux desktop


Publication Layer

Purpose:
Publish and recover state.

Examples:
Git
GitHub


Rules

Authority is independent of platform.

Work may occur from any device.

Durable outputs return to workspace.

Git manages history.

Publication does not define truth.

--------------------------------------------------
--------------------------------------------------


Governance:
- ENGAGEMENT_START.md
- BUSINESS_STATE.md
- DECISION_LOG.md
- ASSUMPTIONS.md
- DONE_CRITERIA.md
- REPOSITORY_MAP.md

Operations:
- SOPs
- Maintenance
- Operating records

Projects:
- PROJECT_STATE.md
- PROJECT_WORKFLOW.md
- Project documents

Systems:
- Firmware
- ESPHome
- Home Assistant
- Supabase
- Architecture

Data:
- Stock
- Production
- Reporting

Archive:
- Closed work
- Historical records

Status:
Concept approved
Migration not started
