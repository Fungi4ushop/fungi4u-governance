
# LIFECYCLE_MODEL

Purpose:
Define the independent lifecycle dimensions of the operating system and the relationships between them.

This document provides the architectural model that governs:

* Repository state
* Chat state
* Engagement state

The purpose of this model is to prevent lifecycle concepts from being mixed together and to provide a consistent framework for governance decisions.

---

# Core Principle

The operating system contains multiple independent lifecycles.

These lifecycles serve different purposes.

A state change in one lifecycle does not automatically imply a state change in another lifecycle.

The operating system currently contains:

* Repository Lifecycle
* Chat Lifecycle
* Engagement Lifecycle

---

# Repository Lifecycle

Purpose:

Track authority and publication status.

Question Answered:

"What is the authority status of this output?"

States:

Proposed
↓
Approved
↓
Installed
↓
Published

---

## Proposed

Definition:

A candidate change that has not yet been approved.

Typical Sources:

* Discovery
* Experiment
* Design
* Review

Characteristics:

* Not authoritative
* Subject to change
* May be rejected

Examples:

* Recommendation
* Draft document
* Candidate architecture

---

## Approved

Definition:

A change that has been accepted through Formalisation.

Characteristics:

* Governance approval exists
* Repository may not yet reflect the decision
* Installation remains pending

Examples:

* Approved decision
* Approved replacement document
* Approved governance change

---

## Installed

Definition:

An approved change that has been applied to repository files.

Characteristics:

* Repository content reflects the decision
* Changes may not yet be committed
* Publication may still be pending

Examples:

* Local repository updated
* Replacement files installed

---

## Published

Definition:

An installed change that has been committed and published according to repository workflow.

Characteristics:

* Repository history reflects the change
* Publication process complete

Examples:

* Commit completed
* Push completed

---

# Chat Lifecycle

Purpose:

Track workspace state.

Question Answered:

"Where is the work being performed?"

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

---

## Active Chat

Definition:

A chat currently being used as a workspace.

Characteristics:

* Supports execution
* May contain multiple engagements
* Temporary by design

---

## Continuation Review

Definition:

An engagement used to evaluate workspace usability.

Purpose:

Determine whether the current chat remains suitable.

Outputs:

* Current state summary
* Lessons learned
* Continuation decision
* Chat Continuation Package (if required)

---

## Continue

Definition:

Decision to remain within the current chat.

Reason:

Workspace remains usable.

---

## Successor Chat

Definition:

A new chat created to continue work from another chat.

Inputs:

* Chat Continuation Package
* Repository artifacts

Purpose:

Maintain continuity while allowing chats to remain temporary.

---

## Closed Chat

Definition:

A chat no longer used for active work.

Characteristics:

* Historical workspace
* Not authoritative
* May still contain useful context

---

# Engagement Lifecycle

Purpose:

Track work being performed.

Question Answered:

"What work is being performed?"

Typical States:

Discovery
Experiment
Design
Review
Formalisation
Project
Execution
Closure

---

## Discovery

Understand current state.

---

## Experiment

Test assumptions.

---

## Design

Create a proposed future state.

---

## Review

Evaluate existing work.

---

## Formalisation

Convert accepted decisions into authoritative outcomes.

Outputs:

* Approved decisions
* Approved replacement documents

Formalisation changes repository state from:

Proposed
↓
Approved

---

## Project

Implement approved changes.

Outputs:

* Implemented capability
* Installed artifacts

Projects may contribute to:

Approved
↓
Installed

transition.

---

## Execution

Perform approved operational work.

---

## Closure

Finish and preserve work.

---

# Lifecycle Independence

Repository lifecycle, chat lifecycle, and engagement lifecycle are independent.

Examples:

A document may be:

Repository State:
Approved

while simultaneously being produced during:

Engagement:
Formalisation

inside:

Chat State:
Active Chat

---

A chat may be:

Chat State:
Successor Chat

while work inside it is:

Engagement:
Design

and repository outputs remain:

Repository State:
Proposed

---

# Lifecycle Relationships

The operating system uses the following relationships.

Review may produce:

Proposed outputs.

Formalisation may produce:

Approved outputs.

Repository Update may produce:

Installed outputs.

Commit and Publication may produce:

Published outputs.

Continuation Review may affect:

Chat lifecycle only.

---

# Governance Principles

## Repository First

Repository artifacts are authoritative.

Chats are not authoritative.

---

## Lifecycle Separation

Repository state, chat state, and engagement state must not be treated as the same thing.

---

## Explicit State

All significant outputs should have a clearly identifiable lifecycle state.

---

## Continuity Through Artifacts

Work continuity is achieved through repository artifacts and Chat Continuation Packages rather than indefinite chat growth.

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
