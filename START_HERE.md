START_HERE

Purpose:
Restart work reliably without depending on memory or chat history.


Rule

Do not begin with documents.

Begin with questions.


Step 1 — Choose Business Area

Select the area that owns the work.


□ Governance

Purpose:
Define rules, ownership, structure, workflows, decisions, and operating principles.

Examples:
Repository structure
Decision making
Operating model
Policies


□ Operations

Purpose:
Run existing activities and maintain continuity.

Examples:
Producing mushrooms
Routine administration
Maintenance
Deliveries


□ Systems

Purpose:
Build, improve, or operate technical systems.

Examples:
Stock-control
ESP32
Home Assistant
Infrastructure
Software


□ Data

Purpose:
Organise, measure, record, and analyse information.

Examples:
Databases
Metrics
Reports
Tracking
Recordkeeping


□ Archive

Purpose:
Retain completed or inactive information.

Examples:
Retired projects
Historical decisions
Old versions


--------------------------------------------------


Step 2 — Choose Engagement

Select the type of work.


□ Discovery

Purpose:
Understand current reality.

Questions:
What exists?
What is true?
What are the boundaries?

Outputs:
Findings
Classification
Observations


□ Experiment

Purpose:
Learn through controlled trial.

Questions:
Will this work?
What assumptions exist?

Outputs:
Results
Lessons
Decision inputs


□ Design

Purpose:
Create a proposed future state.

Questions:
What should exist?
How should it work?

Outputs:
Plans
Architecture
Proposals

□ Project

Purpose:
Introduce approved change.

Questions:
What should improve?
What capability should be added?

Outputs:
Implemented change
Transition plan
Updated operating state

□ Formalisation

Purpose:
Convert approved ideas into governed state.

Questions:
What becomes official?

Outputs:
Documents
Rules
Ownership


□ Execution

Purpose:
Perform approved work.

Questions:
How do we implement?

Outputs:
Completed work
Updated state


□ Review

Purpose:
Evaluate outcomes and alignment.

Questions:
Did we achieve the objective?

Outputs:
Corrections
Validation
Open actions


□ Closure

Purpose:
Finish work and preserve state.

Questions:
What must be retained?

Outputs:
Updated documents
Publication
Next actions


--------------------------------------------------


Step 3 — Define Objective

Complete:

Objective:
_________________________________


--------------------------------------------------


Step 4 — Load Minimum Context


Always load:

□ ENGAGEMENT_START.md
□ BUSINESS_STATE.md
□ OPEN_ACTIONS.md


Load if governance changes:

□ REPOSITORY_MAP.md
□ PROJECT_WORKFLOW.md
□ DONE_CRITERIA.md


Load if direction matters:

□ EVOLUTION_PATH.md


Load domain documents only if required.


--------------------------------------------------


Step 5 — Start Chat


Use:


Business Area:
<selected>

Engagement:
<selected>

Objective:
<completed>

Constraints:
From BUSINESS_STATE


--------------------------------------------------


Step 6 — Execute


Work.

Approve.

Update impacted documents.


--------------------------------------------------


Step 7 — Close


Confirm:


□ Documents updated

□ Open actions updated

□ Repository updated

□ Commit completed

□ Publication completed


--------------------------------------------------


Step 8 — Continue Evolution


If work repeatedly needs memory:

Promote to domain.


If work repeatedly needs process:

Promote to governance.


If work repeatedly needs effort:

Consider automation.


--------------------------------------------------


Operating Principles


The system must explain itself.

Authority lives in documents.

Platforms execute.

Discovery precedes design.

Experiment precedes formalisation.

Progress over perfection.


--------------------------------------------------


When Lost


Load:

START_HERE.md
BUSINESS_STATE.md
OPEN_ACTIONS.md


and begin again.
