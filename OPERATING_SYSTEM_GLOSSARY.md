# OPERATING_SYSTEM_GLOSSARY

Purpose:
Provide authoritative definitions for terminology used within the operating system.

This document defines governance language, lifecycle concepts, authority concepts, workspace concepts, and engagement concepts.

When terminology conflicts with common usage, the definitions contained in this document take precedence within the operating system.

This document derives its lifecycle definitions from LIFECYCLE_MODEL.md.

---

# Core Concepts

## Operating System

The governance framework used to organise, execute, review, formalise, implement, and preserve work.

The operating system consists of:

* Governance documents
* Lifecycle models
* Workflows
* Repository structures
* Engagement processes
* Governance principles

---

## Repository

The authoritative system of record.

Repository artifacts define approved and installed state.

When repository content conflicts with chat content, repository content takes precedence.

---

## Chat

A temporary workspace used to conduct work.

A chat:

* Is not authoritative
* Is not part of the repository
* May contain multiple engagements
* Exists to support execution

Chats are temporary by design.

---

## Engagement

A bounded unit of work performed within a chat.

Every engagement has:

* Business Area
* Engagement Type
* Objective
* Inputs
* Outputs
* Constraints

Multiple engagements may occur within the same chat.

Changing engagement does not require creating a new chat.

---

# Lifecycle Concepts

## Lifecycle

A progression of states used to manage a specific aspect of the operating system.

The operating system contains:

* Repository Lifecycle
* Chat Lifecycle
* Engagement Lifecycle

These lifecycles are independent.

---

## Lifecycle Separation

The principle that repository state, chat state, and engagement state are distinct concepts and must not be treated as equivalent.

A state change in one lifecycle does not automatically imply a state change in another lifecycle.

---

## Repository Lifecycle

Tracks authority and publication status.

States:

Proposed
↓
Approved
↓
Installed
↓
Published

Question Answered:

"What is the authority status of this output?"

---

## Chat Lifecycle

Tracks workspace state.

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

Question Answered:

"Where is the work being performed?"

---

## Engagement Lifecycle

Tracks work being performed.

Examples:

* Discovery
* Experiment
* Design
* Review
* Formalisation
* Project
* Execution
* Closure

Question Answered:

"What work is being performed?"

---

# Repository Lifecycle States

## Proposed

A candidate change that has not yet been approved.

Sources may include:

* Discovery
* Experiment
* Design
* Review

Characteristics:

* Not authoritative
* Subject to change
* May be rejected

---

## Approved

A change that has been accepted through Formalisation.

Characteristics:

* Governance approval exists
* Repository may not yet reflect the decision
* Installation remains pending

Examples:

* Approved decision
* Approved architecture
* Approved replacement document

---

## Installed

An approved change that has been applied to repository files.

Characteristics:

* Repository contents reflect approved decisions
* Changes may not yet be committed
* Publication may still be pending

---

## Published

An installed change that has been committed and published according to repository workflow.

Characteristics:

* Repository history reflects the change
* Publication process complete

---

# Chat Lifecycle Concepts

## Active Chat

A chat currently being used as a workspace.

---

## Continuation Review

An engagement used to evaluate workspace usability.

Purpose:

Determine whether work should:

* Continue in the current chat
* Move to a successor chat
* Conclude

Typical Outputs:

* Current state summary
* Lessons learned
* Continuation decision
* Chat Continuation Package

---

## Chat Continuation Package

A structured artifact used to transfer context from one chat to another.

May include:

* Current state
* Decisions made
* Documents affected
* Open actions
* Remaining work
* Recommended next engagement

---

## Successor Chat

A new chat created to continue work from a previous chat.

Inputs:

* Chat Continuation Package
* Repository artifacts

---

## Chat Rollover

The process of ending work in one chat and continuing it in a successor chat.

---

## Closed Chat

A chat no longer used for active work.

---

# Business Areas

## Governance

Work that changes:

* Rules
* Structures
* Ownership
* Operating model
* Governance artifacts

---

## Operations

Work that runs existing capability.

---

## Systems

Work that creates or improves technical capability.

---

## Data

Work that manages information.

---

## Archive

Work that preserves historical information.

Archive is read-only unless explicitly reopened.

---

# Engagement Types

## Discovery

Understand current state.

Typical Outputs:

* Findings
* Constraints
* Questions

Produces:

Proposed outputs.

---

## Experiment

Test assumptions.

Typical Outputs:

* Results
* Evidence
* Recommendations

Produces:

Proposed outputs.

---

## Design

Create a proposed future state.

Typical Outputs:

* Architectures
* Processes
* Solutions

Produces:

Proposed outputs.

---

## Review

Evaluate existing work.

Typical Outputs:

* Findings
* Lessons learned
* Recommendations

Produces:

Proposed outputs.

---

## Formalisation

Convert accepted decisions into authoritative outcomes.

Typical Outputs:

* Approved decisions
* Approved replacement documents

Repository Lifecycle Transition:

Proposed
↓
Approved

---

## Project

Implement approved changes.

Typical Outputs:

* Installed capability
* Installed documents
* Installed repository changes

May contribute to:

Approved
↓
Installed

transition.

---

## Execution

Perform approved operational work.

---

## Closure

Complete and preserve work.

---

# Governance Artifacts

## Governance Artifact

A document that defines, controls, or records how work is performed.

Examples:

* START_HERE.md
* PROJECT_WORKFLOW.md
* LIFECYCLE_MODEL.md
* OPERATING_SYSTEM_GLOSSARY.md

---

## Authoritative Document

The official source of truth for a specific subject.

---

## Working Document

A document that has not yet reached Installed state.

---

# Governance Outputs

## Decision

A conclusion reached during an engagement.

A decision is not automatically authoritative.

---

## Approved Decision

A decision that has passed through Formalisation.

Repository State:

Approved

---

## Finding

An observation produced during Review.

---

## Recommendation

A proposed course of action.

Recommendations require acceptance before becoming decisions.

---

## Open Action

Approved work that remains incomplete.

Open actions track remaining work required to move outputs through lifecycle states.

---

# Repository Evolution Concepts

## Document Emergence

The principle that new repository documents may be created when a distinct responsibility, concern, authority, lifecycle, or architectural boundary becomes visible during an engagement.

Document emergence supports controlled repository evolution.

---

## Architectural Boundary

A separation between responsibilities or concerns that justifies independent treatment.

---

## Separation of Concern

The practice of assigning a distinct responsibility to each document.

---

# Operating Principles

## Repository First

Repository artifacts are authoritative.

Chats are not authoritative.

---

## Lifecycle Separation

Repository state, chat state, and engagement state must not be treated as the same thing.

---

## Explicit Governance

Governance language and authority should be documented rather than assumed.

---

## Controlled Evolution

The operating system evolves through Review, Formalisation, implementation, and publication.

---

## Continuity Through Artifacts

Continuity is achieved through repository artifacts and Chat Continuation Packages rather than indefinite chat growth.

---

## Authority Progression

Authority progresses through:

Proposed
↓
Approved
↓
Installed
↓
Published

Each state represents a distinct governance condition.



