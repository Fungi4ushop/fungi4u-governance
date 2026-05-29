# START_HERE

Purpose:
Provide a consistent method for starting work within the operating system.

This document is used to prepare an engagement before execution begins.

Execution starts only after ENGAGEMENT_START has been completed.

This document does not perform work.

It prepares work.

---

# Core Principle

The operating system contains three independent lifecycles:

Repository Lifecycle
Chat Lifecycle
Engagement Lifecycle

These lifecycles answer different questions.

Repository Lifecycle:

What is the authority status?

Chat Lifecycle:

Where is the work being performed?

Engagement Lifecycle:

What work is being performed?

These lifecycles must not be treated as the same thing.

---

# Repository Lifecycle

Authority progresses through:

Proposed
↓
Approved
↓
Installed
↓
Published

Definitions:

Proposed:
Candidate change.

Approved:
Accepted through Formalisation.

Installed:
Applied to repository files.

Published:
Committed and published.

Repository artifacts are authoritative.

Chats are not authoritative.

---

# Chat Lifecycle

Work occurs within chats.

Chats are temporary workspaces.

A chat may contain multiple engagements.

Chat lifecycle:

Active Chat
↓
Continuation Review
↓
Continue
OR
Successor Chat
OR
Closed

Continuation Review should be considered when:

* Navigation becomes difficult
* Context becomes difficult to manage
* Response quality degrades
* Multiple engagements accumulate
* Workspace usability declines

---

# Engagement Lifecycle

Work is performed through engagements.

Available engagement types:

Discovery
Experiment
Design
Review
Formalisation
Project
Execution
Closure
Continuation Review

Each engagement has:

* Business Area
* Objective
* Inputs
* Outputs
* Constraints

---

# Startup Process

Step 1
↓
Select Business Area

Step 2
↓
Select Engagement Type

Step 3
↓
Define Objective

Step 4
↓
Select Inputs

Step 5
↓
Define Expected Outputs

Step 6
↓
Assess Workspace Health

Step 7
↓
Start ENGAGEMENT_START

---

# Step 1 — Select Business Area

Business Area identifies ownership of the work.

Available Business Areas:

Governance

Examples:

* operating system
* repository structure
* governance documents
* decision processes

---

Operations

Examples:

* production
* maintenance
* administration

---

Systems

Examples:

* software
* ESP32
* automation
* infrastructure

---

Data

Examples:

* databases
* reporting
* measurements

---

Archive

Examples:

* historical records
* retired work
* preserved artifacts

Selected Business Area:

---

---

# Step 2 — Select Engagement Type

Select the work being performed.

Discovery

Purpose:

Understand current state.

---

Experiment

Purpose:

Test assumptions.

---

Design

Purpose:

Create proposed future state.

---

Review

Purpose:

Evaluate existing work.

---

Formalisation

Purpose:

Approve decisions and replacement documents.

Repository Lifecycle Transition:

Proposed
↓
Approved

---

Project

Purpose:

Implement approved changes.

Repository Lifecycle Transition:

Approved
↓
Installed

---

Execution

Purpose:

Perform approved operational work.

---

Closure

Purpose:

Complete and preserve work.

---

Continuation Review

Purpose:

Assess workspace usability.

Selected Engagement:

---

---

# Step 3 — Define Objective

Objective:

---

Success Means:

---

---

# Step 4 — Select Inputs

Inputs should be selected intentionally.

Not every engagement requires every document.

---

## Architecture Documents

Used to understand how the operating system works.

Examples:

* LIFECYCLE_MODEL.md
* OPERATING_SYSTEM_GLOSSARY.md
* PROJECT_WORKFLOW.md
* START_HERE.md

Load when architectural understanding is required.

---

## State Documents

Used to understand current reality.

Examples:

* OPEN_ACTIONS.md
* BUSINESS_STATE.md
* DECISION_LOG.md

Load when current status is required.

---

## Domain Documents

Used to understand a specific subject area.

Examples:

* System architecture
* Business architecture
* Technical specifications
* Project documents

Load as required.

---

Selected Inputs:

---

---

# Step 5 — Define Expected Outputs

Possible Outputs:

* Findings
* Recommendations
* Decisions
* Approved Decisions
* Replacement Documents
* Installed Documents
* Open Actions
* Repository Updates
* Chat Continuation Package
* Closure Record

Selected Outputs:

---

---

# Step 6 — Assess Workspace Health

Evaluate the current chat.

Indicators:

[ ] Navigation difficult

[ ] Context difficult to manage

[ ] Response quality degrading

[ ] Multiple engagements accumulated

[ ] Workspace becoming inefficient

If one or more indicators are present:

Consider:

Continuation Review

Purpose:

Determine whether work should continue in the current chat or move to a successor chat.

---

# Step 7 — Start Execution

Open:

ENGAGEMENT_START.md

Transfer:

* Business Area
* Engagement Type
* Objective
* Inputs
* Outputs
* Constraints

Execution begins after ENGAGEMENT_START.

---

# Operator Rules

Repository is authoritative.

Chats are temporary.

Engagements are bounded units of work.

Use architecture documents to understand the system.

Use state documents to understand current reality.

Prefer replacement documents over editing instructions.

Do not reconstruct context when repository artifacts exist.

---

# Recovery Rule

If uncertain:

Return to START_HERE.

Determine:

* Business Area
* Engagement Type
* Objective
* Inputs
* Outputs

Then restart the engagement.


