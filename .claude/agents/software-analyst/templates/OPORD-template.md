---
opord-id: OPORD-[YYYY-MM-DD]-[topic-slug]
date: [YYYY-MM-DD]
prepared-by: software-analyst
reviewed-by: [PM name]
---

# OPORD: [Mission Name]

## S — SITUATION

### Current State (AS-IS)

[What exists today — system, process, business area, deficiencies]

### Environmental Factors

- Team size: [n engineers, PMs, QA]
- Existing tools: [relevant tools/systems]
- Key constraints: [time, budget, technical debt, regulatory]

### Friendly Forces

[Adjacent teams, prior work, shared resources available]

### Problem Statement

[Concise. Derived from 5 Whys root cause. Why this matters to the business.]

---

## M — MISSION

**[WHO] will [DO WHAT] [WHERE] by [WHEN] in order to [WHY/BUSINESS OUTCOME].**

_Derived from JTBDs: [JOB-1, JOB-2...]_

---

## E — EXECUTION

### Concept of Operations

[High-level strategic direction — not implementation details]

### Tasks by Role

| Role        | Tasks | Owner | By When |
| ----------- | ----- | ----- | ------- |
| PM          |       |       |         |
| Engineering |       |       |         |
| QA          |       |       |         |
| Stakeholder |       |       |         |

### Decision Points

| Decision | Options | Authority | By When |
| -------- | ------- | --------- | ------- |

### Definition of Done

- [ ] [measurable criterion 1]
- [ ] [measurable criterion 2]

---

## A — ADMIN / LOGISTICS

### Timeline

| Milestone | Description | Target Date | Owner |
| --------- | ----------- | ----------- | ----- |

### Dependencies

| Dependency | Team/System | Status | Risk if Late |
| ---------- | ----------- | ------ | ------------ |

### Resources

- Budget: [amount or TBD]
- Environments: [dev/staging/prod]
- Tooling: [licenses, services]

### Risk Register

| #   | Risk | Likelihood   | Impact       | Mitigation |
| --- | ---- | ------------ | ------------ | ---------- |
| R1  |      | High/Med/Low | High/Med/Low |            |
| R2  |      |              |              |            |
| R3  |      |              |              |            |

---

## C — COMMAND / SIGNAL

### Decision Authority

| Decision Type | Authority   | Escalation     |
| ------------- | ----------- | -------------- |
| Scope changes | [PM]        | [Sponsor]      |
| Architecture  | [Tech Lead] | [Eng Director] |
| Budget        | [Sponsor]   | [Executive]    |

### Communication Cadence

| Meeting       | Frequency | Participants | Purpose          |
| ------------- | --------- | ------------ | ---------------- |
| Standup       | Daily     | [roles]      | Status, blockers |
| Sprint Review | Biweekly  | [roles]      | Demo, feedback   |

### Artifact Location

`.claude/agents/software-analyst/specs/`

### Escalation Path

[How issues are raised and who resolves at each level]
