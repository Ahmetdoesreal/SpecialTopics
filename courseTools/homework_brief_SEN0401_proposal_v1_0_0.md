# SEN0401 Special Topics: Blockchain — course project homework: Proposal

*Generated from the proposal rubric by pw_brief 1.0.0; the Project Grader applies exactly these criteria.*

## 1. What you hand in

One submission per team, prepared in the **Proposal Workbench** (`proposal_tool_v4_11_0.html`, published in the course repository). In the Workbench choose your course **SEN0401**, the submission stage **Proposal** and the current term. The plan: who the system is for, what it will do, how it will be built and checked, and who does what. Nothing is implemented yet: the Delivery and evidence part stays empty.

Hand in **the ZIP the Workbench saves** (File › Save › ZIP of every format: the proposal file `.json`, the read-only web page, the Markdown and the lineage draft). The Workbench names it after your project title (`<title>_proposal.zip`); do not rename it. Upload the same ZIP unchanged to the course's assignment, and commit the saved files to your project's GitHub repository under `proposal/` (the Workbench's *Post to GitHub* does this for you with a repository token that is never stored; without a token, commit the files yourself).

The Workbench's **Review and export › Grades** shows the grade the Project Grader will compute from your file. What it shows is what you get for the automatic part; the examiner may award half or no points where a criterion is met in form only.

**A real project, not a toy.** The Workbench's example files are invented — teams, customers and all — and are there only to show the form of a complete file. Your project serves a customer that exists and that you have reached: an organisation, a unit, a club, a business or a person who will use or own the system. The *Customer* rows ask who you spoke to and how and when; a proposal without that, or built on an example, is not graded as a project.

## 2. What must be in the file — every criterion the Grader checks

### Team and work — the team grade

| Points | Criterion |
|---|---|
| 3 | Every member owns a module or feature, and each has an owner and an epic |
| 3 | The work log's chain is intact and shows no anomaly |
| 2 | Each core engineering process has a member leading it |
| 2 | Every member has at least one development role |
| 2 | Every member has work-log entries |
| 2 | Repository confirmed to exist on GitHub |
| 2 | Work shares given for every member, summing to 100% |
| 1 | A team lead is named among the administrative roles |
| 1 | Every member has a name, student number and e-mail |
| 1 | GitHub repository address given (github.com/owner/name) |
| 1 | Team of the advised size (5-10 members) |
| 1 | Team within the course's limit (1-10 members) |

### Mission — 20% of the project grade

| Points | Criterion |
|---|---|
| 2 | A real customer: a named contact person or role, and how and when they were reached (3 words or more each) |
| 2 | Every end-user group is concrete: who, what they do, how often |
| 2 | Mission of 40 words or more that names an end-user group |
| 2 | The customer is named, with their relation and what they get |
| 2 | The end users' problem: 120 words or more, with a number |
| 1 | Mission origin chosen and outcome stated |
| 1 | Title of 15 words or fewer |

### Scope — 15% of the project grade

| Points | Criterion |
|---|---|
| 2 | At least 2 semantic technologies chosen, with why |
| 1 | At least 2 domain entities, each defined |
| 1 | At least 2 exclusions, each with a reason |
| 1 | At least 2 scope areas |
| 1 | Every area has at least one deliverable |
| 1 | Every deliverable has an area, a layer and a kind |
| 1 | Project kind chosen from the project-kind taxonomy |
| 1 | Technologies cover at least 2 stack layers |

### Goal — 15% of the project grade

| Points | Criterion |
|---|---|
| 1 | A containment-facing goal |
| 1 | A mission-facing goal |
| 1 | A nominal test scenario |
| 1 | A rejection test scenario |
| 1 | A scope-facing goal |
| 1 | Every scope area is covered by a goal |
| 1 | Specification of 60 words or more |

### Objective — 10% of the project grade

| Points | Criterion |
|---|---|
| 2 | Activity and sequence models written |
| 2 | Every goal has an objective |
| 2 | Every objective: how measured, baseline, target, direction |

### Backlog — 20% of the project grade

| Points | Criterion |
|---|---|
| 2 | Every story has a Given/When/Then acceptance criterion |
| 2 | Every story is told by a defined end user or customer |
| 2 | The design model each chosen concern owes is written |
| 1 | At least 5 stories |
| 1 | Class model written |
| 1 | Definition of done with at least 2 criteria |
| 1 | Every epic pursues an objective |
| 1 | Every story has a category, a design concern and a priority |
| 1 | Every story has a test case |
| 1 | Kind of development chosen |

### Course-specific — 5% of the project grade

| Points | Criterion |
|---|---|
| 1 | The course's own questions answered |

### Plan and references — 5% of the project grade

| Points | Criterion |
|---|---|
| 1 | At least 3 risks with likelihood, impact, mitigation |
| 1 | At least 4 milestones inside the term |
| 1 | At least 5 references |

The course's own questions (the *Course-specific* part):

- **Blockchain design** — Which network and mechanisms the project uses, and why it needs a blockchain at all.

Not applicable in this course (no points, not asked): An advisor is named.

Values that differ from the rubric's defaults: At least 5 references (this course).

## 3. Each member's own grade — Individual contribution

Computed for every member from the member's own rows of the file; the examiner may replace it with an individual score.

| Points | Criterion (per member) |
|---|---|
| 3 | Logged share of hours at least 50% of the planned share |
| 2 | At least 2 work-log entries |
| 2 | Responsible for a module or feature and holding a development role |
| 2 | Work logged in at least 2 task types |

## 4. How the grade is made at this stage

- Project grade: the project parts above, each part scored as points met over points possible, combined by the weights shown.
- Team grade: the *Team and work* part.
- Member grade = 60% project grade + 20% team grade + 20% the member's individual contribution.
- This stage counts 20% of the course project grade; the Final submission counts 80%.
- These shares are the course's defaults from the rubric; the examiner may set other shares for the course, and the grading file records the ones used.

## 5. Record from the first day — needed for the final submission

The final submission is this same file brought up to date, plus *Delivery and evidence*. What cannot be reconstructed later must be recorded as it happens:

- **Work log, by each member, as the work happens.** Every entry is time-stamped by the page and chained to the one before by SHA-256; an entry changed, removed or inserted later shows in the integrity report, and so do: entries stamped in the future or outside the term, more than 12 hours in one entry or in one member's day, five entries within ten minutes, and the same description repeated. An entry names the task type (the engineering process), the story it serves, the hours, what was done and a link to the evidence (commit, file, page, minutes).
- **The GitHub repository**, created before the proposal is handed in, with every member committing under their own GitHub account. Post the proposal to it: the commit message carries the work log's head fingerprint, so the repository's history pins the log. The examiner verifies the repository, the posted file and the fingerprint against GitHub at grading.
- **Evidence links** in the log entries (the final submission requires evidence on at least half of each member's entries).
- **Who owns what**: each module or feature has an owner and a deputy; the planned shares of work sum to 100%. The final submission measures each member's logged hours against the planned share.
- **A tagged release and a test report** at the end (final submission only) — plan for them now in the milestones.

## 6. Common ways to lose points

- A member without name, student number and e-mail; a member with no development role; a module without an owner or an epic.
- The repository address not in the form `https://github.com/owner/name`, or not checked on GitHub from the page before saving.
- Stories told by nobody in particular (every story is told by one of your defined end users or the customer), or without a Given/When/Then acceptance criterion and a test case.
- Scope areas without a deliverable, goals that do not cover every area, objectives without baseline and target.
- Handing in a file at the wrong stage: the Grader grades the file at the stage it records.

