# FPI Skills

**Verification-oriented control loops for AI coding agents.**

FPI Skills is a small Claude Code / Cowork plugin that turns open-ended agent work into bounded, auditable workflows. Instead of asking an agent to “keep working until it is done,” the toolkit requires a verifiable completion condition, repeated real checks, explicit stop rules, and human approval before irreversible actions.

This repository is useful as an AI-evaluation portfolio example because it focuses on **how to supervise an agent**, not just how to prompt one.

## Core skills

### `/fpi:goal` — define evidence before action

Converts a user objective into:

- one explicit goal,
- a machine-verifiable definition of done,
- out-of-scope boundaries,
- a list of potentially irreversible actions that require later approval.

Good completion criteria are observable, for example:

```text
npm test and npm run build pass, and /api/quotes returns HTTP 200 with a valid payload.
```

A vague criterion such as “make it work” is rejected because it cannot be independently verified.

### `/fpi:loop` — verify → act → verify

Runs bounded work cycles toward the saved goal. Every cycle must:

1. state the immediate sub-goal,
2. take one concrete action,
3. run the real test/build/check tied to the definition of done,
4. record whether the check passed or failed.

Hard safeguards include:

- **8-cycle default cap** to prevent unbounded execution,
- **no-spinning rule**: the same failure twice stops the loop for diagnosis,
- **human approval gate** for push, deploy, production migration, deletion, messaging, publishing, access changes, or secrets,
- **cost awareness**: run the smallest useful check while iterating, then the full suite at the end,
- **cycle log** for post-hoc auditability.

### `/fpi:ship` — evidence-gated code readiness

Detects the repository stack and drives the relevant quality gates toward green:

- tests,
- type checking,
- lint,
- build.

It stops before commit, push, deploy, or production migrations and returns the diff summary plus a proposed Conventional Commit message for human review.

## Why this matters for AI model evaluation

The same failure modes seen in coding agents appear in broader AI systems:

- claiming success without evidence,
- repeating an ineffective strategy,
- drifting away from the requested objective,
- taking irreversible actions too early,
- optimizing for a plausible narrative rather than a verified result.

FPI Skills encodes countermeasures directly into the agent workflow:

| Failure mode | Control |
| --- | --- |
| Vague success claim | Verifiable definition of done |
| Repeated failed reasoning | Stop after the same failure twice |
| Infinite/autonomous looping | Hard cycle cap |
| Goal drift | Saved goal + explicit out-of-scope list |
| Unsafe side effects | Human approval for irreversible actions |
| “Looks correct” without evidence | Real tests/build/checks required |
| Opaque trajectory | Per-cycle audit log |

This is a compact example of **human-in-the-loop agent evaluation, explicit rubrics, failure detection, and bounded autonomy**.

## Repository structure

```text
plugins/fpi/skills/
├── goal/SKILL.md
├── loop/SKILL.md
└── ship/SKILL.md
```

Each skill is implemented as a declarative agent instruction with constrained tool access and explicit behavioral rules.

## Install in Claude Code

```text
/plugin marketplace add Francosimon53/fpi-claude-skills
/plugin install fpi@fpi-skills
```

## Design principles

1. **Verification beats confidence.** A model saying it is done is not evidence.
2. **Stop conditions are part of the architecture.** Autonomy without a termination rule is a reliability defect.
3. **Repeated failure should trigger diagnosis, not more tokens.**
4. **Irreversible operations remain human decisions.**
5. **The work trace should be auditable after the fact.**

## Portfolio relevance

FPI Skills complements my larger AI systems projects by showing the control layer around agent behavior: how goals are operationalized, how completion is tested, when an agent must stop, and where human approval remains mandatory.
