# Scrum

Scrum is an [agile](/processes/agile.md) framework designed for development teams, emphasizing flexibility, continuous improvement, and the ability to adapt quickly to change. It promotes empirical process control, relying on transparency, inspection, and adaptation. Scrum organizes work into short, fixed-length iterations called sprints, typically lasting one to four weeks, allowing for frequent feedback and adjustments.

## Members

### Scrum Master

The Scrum Master is a servant-leader responsible for establishing Scrum as defined in the Scrum Guide and helping everyone understand Scrum theory, practices, rules, and values. They aid the team in optimizing the Scrum process, facilitate Scrum events, remove impediments, and coach the team towards self-management and cross-functionality.

### Product Owner

The Product Owner is accountable for maximizing the value of the product resulting from the work of the Scrum Team. They own the product, define its vision, manage the Product Backlog, and are in charge of the product's direction. This includes clearly expressing Product Backlog items, ordering them to best achieve goals and missions, and ensuring the Product Backlog is transparent, visible, and understood.

### Developer

Developers are the individuals within the Scrum Team who are committed to creating any aspect of a usable Increment each Sprint. This role is inclusive, regardless of the specific work performed (e.g., programmers, testers, UI designers, database specialists). They are self-organizing and cross-functional, collectively possessing all the skills necessary to create value.

## Events

### Sprint

A Sprint is a fixed-length time-box of one month or less during which a "Done," usable, and potentially releasable Increment is created. Sprints have consistent durations throughout a development effort, enabling predictability. They are the heart of Scrum, where ideas are turned into value, allowing for frequent inspection and adaptation.

### Sprint Planning

Sprint Planning is the event that kicks off a Sprint. The Developers, Product Owner, and Scrum Master collaborate to define what will be completed in the upcoming Sprint (the Sprint Goal) and how that work will be achieved. Developers estimate the complexity of selected Product Backlog items, often using techniques like story points, which are a relative measure of effort.

### Daily Scrum

The Daily Scrum is a 15-minute time-boxed event for the Developers. It is held daily during the Sprint to inspect progress toward the Sprint Goal and adapt the Sprint Backlog as necessary, adjusting the upcoming planned work. Developers often discuss what they worked on yesterday, what they will work on today, and any impediments they face, fostering communication and accountability.

### Sprint Review

The Sprint Review is held at the end of the Sprint to inspect the Increment and adapt the Product Backlog if needed. The Scrum Team presents the results of their work to key stakeholders, and progress toward the Product Goal is discussed. It's a collaborative session where feedback is gathered, and the Product Backlog is refined based on what was learned during the Sprint.

### Sprint Retrospective

The Sprint Retrospective is a final event of the Sprint, providing an opportunity for the Scrum Team to inspect itself and create a plan for improvements to be enacted during the next Sprint. The team discusses what went well, what could be improved, and what they will commit to changing in their processes, tools, and interactions to increase effectiveness. Retrospectives can follow different [methods](retro.md).

## Artifacts

### Product Backlog

The Product Backlog is an emergent, ordered list of what is needed to improve the product. It is the single source of work undertaken by the Scrum Team, managed by the Product Owner. It contains features, functions, requirements, enhancements, and fixes that constitute the changes to be made to the product in future releases.

### Sprint Backlog

The Sprint Backlog is composed of the Product Backlog items selected for the Sprint, the plan for delivering them, and the Sprint Goal. It is a real-time, highly visible picture of the work that the Developers plan to accomplish during the Sprint to achieve the Sprint Goal.

### Sprint Goal

The Sprint Goal is a single objective for the Sprint. It is created during the Sprint Planning event and provides flexibility in terms of the exact work needed to achieve it. The Sprint Goal helps the Scrum Team focus and work together rather than on separate initiatives.

### Increment

An Increment is a concrete stepping stone toward the Product Goal. Each Increment builds upon all prior Increments and is a "Done," usable, and potentially shippable product. Multiple Increments may be created within a Sprint, and their sum is presented at the Sprint Review.

### Definition of Done

The Definition of Done is a formal description of the state of the Increment when it meets the quality measures required for the product. It provides a shared understanding of what it means for work to be complete, ensuring transparency and quality. The Developers can iterate on and refine the Definition of Done at any time.

#### Example

1. Code has been reviewed by at least one other developer.
2. Unit tests are written for new functions.
3. The Product Owner has been informed of the completion.
4. The story is marked as Done on the board.

**Issue 1 - No definition of test coverage threshold**

The criterion "unit tests are written for new functions" is too vague. It doesn't
specify how much coverage is required, meaning a single trivial test could satisfy
this criterion while leaving critical logic untested.

**Issue 2 - No integration or end-to-end testing requirement**

The DoD only mentions unit tests. There is no requirement to verify the story works
correctly within the broader system, meaning integration bugs could slip through
undetected.

**Issue 3 - No requirement for working, deployable software**

There is no criterion that the software actually builds, runs, or is deployed to a
test or staging environment. Code could be merged but broken in the broader codebase.

**Issue 4 - Only one reviewer required**

Requiring only one reviewer is a weak quality gate, particularly for complex or
high-risk stories. It also doesn't specify the reviewer's seniority or familiarity
with the codebase.

**Issue 5 - Marking as Done on the board is not a quality criterion**

Item 4 is purely administrative — it describes a workflow action, not a quality
standard. A story being marked Done on a board does not mean it meets any
meaningful quality bar.

### Velocity

Velocity is an optional, but commonly used, metric in Scrum that measures the amount of work (e.g., story points) a Scrum Team can complete in a Sprint. It is primarily used for forecasting and planning future Sprints, not as a measure of productivity for individuals or to pressure teams.

## Anti Patterns

### Zombie Scrum

Zombie Scrum refers to situations where teams mechanically go through the motions of Scrum events (Daily Scrum, Sprint Review, Retrospective) and use its artifacts (Product Backlog, Sprint Backlog) but fail to embrace the core values and principles of Scrum. This often results in a lack of true agility, transparency, and continuous improvement, leading to a superficial implementation of the framework.

### Dark Scrum

Dark Scrum occurs when Scrum is misused as a tool to pressure or control development teams, often by stakeholders or management. This typically manifests as an excessive focus on increasing velocity, setting unrealistic Sprint Goals, or micro-managing the team's work, undermining the principles of self-management, sustainable pace, and quality that Scrum advocates.
