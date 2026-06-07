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

## Charts

# Scrum Retrospective Methods

A **sprint retrospective** is a ceremony held at the end of every sprint where the Scrum team reflects on how they worked together and identifies improvements for the next sprint. Attendees are the development team, Scrum Master (facilitator), and Product Owner. Managers and external stakeholders should not attend — the space must be psychologically safe for honest conversation.

---

## 1. Start, Stop, Continue

The most common and beginner-friendly format. Simple and actionable.

| Column       | Question                                                      |
| ------------ | ------------------------------------------------------------- |
| **Start**    | What should we begin doing that we aren't doing yet?          |
| **Stop**     | What are we doing that isn't adding value or is causing harm? |
| **Continue** | What is working well that we should keep doing?               |

**Best for:** new teams, quick retros, teams that want clear action items.

---

## 2. 4Ls — Liked, Learned, Lacked, Longed For

A more reflective format that surfaces both emotional and process-level feedback.

| Column         | Question                                             |
| -------------- | ---------------------------------------------------- |
| **Liked**      | What did you enjoy or appreciate this sprint?        |
| **Learned**    | What new knowledge or skills did you gain?           |
| **Lacked**     | What was missing that would have helped?             |
| **Longed For** | What do you wish we had — tools, processes, support? |

**Best for:** teams wanting deeper insight beyond just what went wrong.

---

## 3. Mad, Sad, Glad

A feelings-first format that surfaces emotional state before moving to solutions. Encourages psychological safety.

| Column   | Question                                     |
| -------- | -------------------------------------------- |
| **Mad**  | What frustrated or angered you this sprint?  |
| **Sad**  | What disappointed you or didn't go as hoped? |
| **Glad** | What made you happy or feel proud?           |

**Best for:** teams experiencing tension or low morale, or when the previous sprint was particularly difficult.

---

## 4. Starfish

An evolution of Start/Stop/Continue with more nuance — avoids binary thinking.

| Column          | Meaning                            |
| --------------- | ---------------------------------- |
| **Keep doing**  | Working well, must continue        |
| **More of**     | Good, but needs amplifying         |
| **Less of**     | Not ideal, but don't stop entirely |
| **Stop doing**  | Counterproductive, discontinue     |
| **Start doing** | New ideas to introduce             |

**Best for:** mature teams who find Start/Stop/Continue too blunt.

---

## 5. What Went Well / Even Better If (WWW/EBI)

A simple positive-framing format. "Even Better If" is less confrontational than "What went wrong".

| Column             | Question                                              |
| ------------------ | ----------------------------------------------------- |
| **What Went Well** | Successes and strengths from the sprint               |
| **Even Better If** | What could have been improved — framed constructively |

**Best for:** teams where psychological safety is still being established, or when morale needs protecting.

---

## 6. Sailboat (or Speed Boat)

A visual metaphor-based format. The team imagines a sailboat trying to reach an island (the goal).

| Element          | Represents                           |
| ---------------- | ------------------------------------ |
| **Island**       | The team's goal or vision            |
| **Wind (sails)** | Things helping the team move forward |
| **Anchors**      | Things slowing the team down         |
| **Rocks**        | Upcoming risks or obstacles          |

**Best for:** teams struggling with alignment on goals, or mid-project check-ins.

---

## 7. Five Whys

A root cause analysis technique. Rather than treating symptoms, the team drills into _why_ a problem occurred.

**Process:**

1. State a problem from the sprint
2. Ask "Why did this happen?" → answer
3. Ask "Why?" again → dig deeper
4. Repeat up to 5 times until the root cause is found
5. Address the root cause, not the symptom

**Example:**

```
Problem: We missed the sprint goal
Why? → Two stories weren't finished
Why? → They were blocked waiting for backend API
Why? → API team had conflicting priorities
Why? → No shared sprint planning between teams
Root cause → Cross-team dependency not surfaced early enough
```

**Best for:** recurring problems, post-incident reviews, teams in a rut.

---

## 8. DAKI — Drop, Add, Keep, Improve

Similar to Starfish but structured around explicit decisions.

| Column      | Meaning                                   |
| ----------- | ----------------------------------------- |
| **Drop**    | Practices to remove entirely              |
| **Add**     | New practices to introduce                |
| **Keep**    | Things working well to maintain           |
| **Improve** | Things worth doing but needing refinement |

**Best for:** teams wanting clear, structured decision-making from their retro.

---

## 9. Timeline Retrospective

The team reconstructs the sprint as a timeline of events — facts, feelings, and observations plotted in order.

**Process:**

1. Draw a horizontal timeline of the sprint
2. Each team member adds sticky notes: events, blockers, wins, and how they felt at each point
3. Identify patterns — where did energy drop? Where did problems cluster?
4. Discuss and agree on actions

**Best for:** long sprints, sprints with many moving parts, or when the team can't remember what happened.

---

## 10. Team Radar / Health Check

The team scores themselves across a set of dimensions (e.g. the 5 Scrum values) on a scale, then discusses the gaps.

**Common dimensions:**

- Courage
- Commitment
- Focus
- Openness
- Respect

Each dimension is scored (e.g. 1–5) by every team member independently, then results are discussed as a group.

**Best for:** measuring team health over time, identifying cultural or process drift.

---

## Choosing the Right Format

| Situation                           | Recommended format    |
| ----------------------------------- | --------------------- |
| New team, first retro               | Start, Stop, Continue |
| Low morale or team tension          | Mad, Sad, Glad        |
| Recurring problems                  | Five Whys             |
| Goal alignment issues               | Sailboat              |
| Want nuance beyond stop/start       | Starfish              |
| Psychological safety still building | WWW / EBI             |
| Tracking team health over time      | Health Check / Radar  |
| Sprint had many events to unpack    | Timeline              |

---

## Tips for Running a Good Retro

- **Rotate the format** — using the same method every sprint leads to stale responses
- **Timebox it** — typically 45–90 mins for a 2-week sprint
- **Always end with action items** — each item needs an owner and a target sprint
- **Review previous actions first** — did last sprint's actions actually happen?
- **Psychological safety is non-negotiable** — no blame, no managers in the room, retro content stays in the team

---

# Scrum Charts & Metrics

Charts are used in Scrum to track progress, forecast delivery, and identify problems early. They are typically reviewed during the daily standup, sprint planning, and retrospective.

---

## 1. Burndown Chart

Tracks **remaining work** over time within a sprint. The line should trend down to zero by the end of the sprint.

| Axis           | Represents                                     |
| -------------- | ---------------------------------------------- |
| X (horizontal) | Time — sprint days                             |
| Y (vertical)   | Work remaining (story points, hours, or tasks) |

**What to look for:**

- Line tracking close to the ideal = healthy sprint
- Flat line = team is blocked or not updating the board
- Line going up = scope creep (new work added mid-sprint)
- Sharp drop at the end = work left to the last minute

**Used in:** daily standup (progress check), retrospective (did we over/under-commit?)

---

## 2. Burnup Chart

Tracks **completed work** over time, with a separate line showing total scope. The opposite perspective to burndown.

| Line               | Represents                                   |
| ------------------ | -------------------------------------------- |
| **Completed work** | Cumulative story points done — trends upward |
| **Scope line**     | Total work in the sprint or backlog          |

**Advantage over burndown:** scope changes are immediately visible — if the scope line jumps up, new work was added. A burndown chart hides this by just resetting the total.

**Used in:** stakeholder updates, sprint planning, release forecasting.

---

## 3. Flow Diagram

Shows how work items move through **each stage of the workflow** over time. Each stage is a coloured band.

**What to look for:**

- Bands of **even width** = healthy, steady flow
- A band that **widens** = work is piling up at that stage (bottleneck)
- A band that **narrows** = that stage is draining faster than it's being fed
- **Cycle time** = vertical distance between when an item enters and exits a stage

**Used in:** identifying bottlenecks, measuring flow efficiency, ongoing workflow monitoring.
