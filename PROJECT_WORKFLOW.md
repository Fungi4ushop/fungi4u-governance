# PROJECT_WORKFLOW

Purpose:
Ensure work execution, governance, repository state, and publication remain aligned.

This workflow implements the lifecycle architecture defined by:

* LIFECYCLE_MODEL.md
* OPERATING_SYSTEM_GLOSSARY.md

---

# Core Principle

The operating system contains three independent lifecycles:

Repository Lifecycle
Chat Lifecycle
Engagement Lifecycle

These lifecycles are related but independent.

A state change in one lifecycle does not automatically imply a state change in another lifecycle.

---

# Repository Lifecycle

Purpose:

Track authority and publication state.

States:

Proposed
↓
Approved
↓
Installed
↓
Published

State Transitions:

Review
↓
Formalisation
↓
Repository Update
↓
Commit / Publication

---

# Chat Lifecycle

Purpose:

Track workspace state.

States:

Active Chat
↓
Continuation Review
↓
Continue
OR
Successor Chat
OR
Closed

Purpose:

Allow work continuity while keeping chats temporary.

---

# Engagement Lifecycle

Purpose:

Track work being performed.

Available Engagement Types:

Discovery
Experiment
Design
Review
Formalisation
Project
Execution
Closure
Continuation Review

Purpose:

Define the nature of the work being performed.

---

# Work Lifecycle

Monitor
↓
Identify Need
↓
Create Engagement
↓
Execute Engagement
↓
Validate Outputs
↓
Review Outputs
↓
Formalise Decisions
↓
Implement Approved Changes
↓
Update Repository
↓
Commit / Publish
↓
Operate
↓
Monitor Again

---

# Lifecycle Relationships

## Discovery

Produces:

Proposed outputs

Examples:

* Findings
* Questions
* Constraints

Repository State:

Proposed

---

## Experiment

Produces:

Proposed outputs

Examples:

* Evidence
* Test results
* Recommendations

Repository State:

Proposed

---

## Design

Produces:

Proposed outputs

Examples:

* Architectures
* Processes
* Solutions

Repository State:

Proposed

---

## Review

Produces:

Proposed outputs

Examples:

* Findings
* Lessons learned
* Recommendations

Repository State:

Proposed

---

## Formalisation

Purpose:

Approve changes.

Produces:

* Approved decisions
* Approved replacement documents

Repository Lifecycle Transition:

Proposed
↓
Approved

Formalisation does not install repository changes.

Formalisation does not publish repository changes.

---

## Project

Purpose:

Implement approved changes.

Produces:

* Installed capabilities
* Installed repository artifacts

Repository Lifecycle Transition:

Approved
↓
Installed

Examples:

* Repository files replaced
* Approved architecture implemented
* Approved governance documents installed

---

## Execution

Purpose:

Perform approved operational work.

Produces:

Operational outcomes.

---

## Closure

Purpose:

Complete and preserve work.

Produces:

Closure artifacts and final status.

---

## Continuation Review

Purpose:

Assess workspace usability.

Produces:

* Current state summary
* Lessons learned
* Continuation decision
* Chat Continuation Package

Affects:

Chat Lifecycle

Does not directly affect Repository Lifecycle.

---

# Execution Gates

## Gate 1 — Startup

Required:

[ ] Business Area identified

[ ] Engagement Type identified

[ ] Objective agreed

[ ] Constraints identified

[ ] Inputs identified

[ ] Outputs identified

[ ] Documentation impact identified

Outcome:

Approved to start engagement.

---

## Gate 2 — Engagement Complete

Required:

[ ] Engagement objective achieved

[ ] Outputs generated

[ ] Validation completed

[ ] Issues recorded

Outcome:

Outputs ready for review or formalisation.

---

## Gate 3 — Formalisation Complete

Required:

[ ] Decisions approved

[ ] Replacement documents approved

[ ] Open actions updated

Outcome:

Repository State = Approved

---

## Gate 4 — Repository Installation

Required:

[ ] Approved documents installed

[ ] Repository files replaced

[ ] Repository consistency verified

Outcome:

Repository State = Installed

---

## Gate 5 — Publication

Required:

[ ] Changes committed

[ ] Publication decision executed

[ ] Push completed (if applicable)

Outcome:

Repository State = Published

---

# Continuation Review Triggers

A Continuation Review may be initiated when:

* Navigation becomes difficult
* Context becomes difficult to manage
* Response quality degrades
* Multiple engagements accumulate
* Workspace becomes inefficient
* Operator judges review necessary

---

# Chat Rollover Process

Continuation Review
↓
Continuation Decision
↓
Create Chat Continuation Package
↓
Create Successor Chat
↓
Resume Work

---

# Repository Update Rule

When an approved change exists:

1. Identify affected documents
2. Generate replacement documents
3. Review replacement documents
4. Approve replacement documents
5. Install replacement documents
6. Verify repository consistency
7. Commit changes
8. Publish if required

Principle:

Approved changes do not become repository state until installation occurs.

---

# Open Action Rule

Open actions must describe remaining work.

Actions should reflect lifecycle state.

Examples:

Good:

Install approved glossary into repository.

Publish approved workflow update.

Avoid:

Create glossary.

Update workflow.

These actions do not indicate lifecycle state and may become ambiguous.

---

# Workspace Rule

Chats are temporary workspaces.

Repository artifacts preserve continuity.

A chat may contain multiple engagements.

An engagement may close without closing the chat.

---

# Publication Rule

Authority progresses through:

Proposed
↓
Approved
↓
Installed
↓
Published

Repository state must accurately reflect the current lifecycle state of governance outputs.

---

# Operating Principles

Repository First

Repository artifacts are authoritative.

---

Lifecycle Separation

Repository Lifecycle, Chat Lifecycle, and Engagement Lifecycle are distinct.

---

Explicit State

All significant outputs should have a clearly identifiable lifecycle state.

---

Continuity Through Artifacts

Continuity is achieved through repository artifacts and Chat Continuation Packages rather than indefinite chat growth.

---

Controlled Evolution

The operating system evolves through review, formalisation, implementation, installation, and publication.


