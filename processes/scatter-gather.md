# Scatter-Gather Problem

## What is it?

Scatter-gather is a development process where a feature is broken down into individual tasks that are **scattered** to separate team members, and only once every piece is complete are they **gathered** back together, merged, and tested.

```
Feature → [Task A → Dev 1]
        → [Task B → Dev 2]  → merge → integrate → test → deploy
        → [Task C → Dev 3]
```

The core problem: **if even one piece is not completed, the whole feature is undeployable**. The more pieces a feature is split into, the more ways there are to fail.

| Parts split out | Possible outcomes | Successful outcomes |
| --------------- | ----------------- | ------------------- |
| 1               | 2                 | 1 (50%)             |
| 2               | 4                 | 1 (25%)             |
| 3               | 8                 | 1 (12.5%)           |
| 5               | 32                | 1 (3%)              |

## Impact on Code Delivery

- **Delayed testing** — end-to-end testing can't happen until every piece is finished
- **Late surprises** — integration issues only surface at the end, causing rework that further delays delivery
- **Obscured status** — no single person knows when the whole feature will be done
- **Time spread** — work is distributed across individual to-do lists rather than done in true parallel, so features take longer than expected
- **Silos form** — developers specialise in narrow fragments; work queues for specialists, blocking progress

## How Vertical Slicing Prevents It

Vertical slicing means delivering one **complete, end-to-end slice** of functionality at a time rather than splitting work horizontally by technical layer or specialism.

| Scatter-Gather (horizontal)                                             | Vertical Slicing                                                  |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------- |
| Dev 1 does all DB work, Dev 2 does all API work, Dev 3 does all UI work | Team delivers one thin end-to-end feature together, then the next |
| Nothing ships until all layers are done                                 | Each slice is independently deployable                            |
| Integration happens at the end                                          | Integration happens continuously                                  |

It prevents scatter-gather in four ways:

1. **One feature in flight at a time** — the whole team focuses on completing one deployable unit before moving to the next, eliminating the "all pieces must finish before anything ships" dependency chain

2. **Late integration is eliminated** — a vertical slice runs end-to-end from the start, so integration and testing happen continuously; issues are caught immediately rather than after everything is built

3. **Silos are broken down** — instead of work being assigned along skill lines, the team works together across the full stack on each slice, reducing specialist queuing and spreading knowledge

4. **Status becomes clear** — because only one feature is in flight at a time and it is always runnable, progress is transparent and lead time is as short as possible

## In Distributed Systems (separate concept, same name)

Scatter-Gather is also an **architectural pattern** where:

- A **coordinator** fans out a request to multiple workers in parallel (scatter)
- It then **collects and merges** their responses (gather)
- Used in: search engines (query multiple shards), map-reduce, API aggregation gateways

```
Client → Coordinator → [Worker A]
                     → [Worker B]  → Coordinator aggregates → Response
                     → [Worker C]
```
