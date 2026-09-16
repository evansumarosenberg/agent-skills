---
name: concept-interview
description: Interview the user to clarify the high-level concept for a new project, application, or feature before specification or implementation planning. Use only when explicitly invoked.
---

# Concept Interview

Establish what is being proposed, for whom, why it matters, and what kind of project it is. The result is a concept document, not a specification, contract, requirements list, or implementation plan.

## Interview

Ask one focused question at a time. Let each answer guide the next question, and discuss an answer when useful before moving on. Continue until the important unknowns and materially different interpretations are resolved.

Cover, as relevant:

- the problem, opportunity, or desired outcome and why the project should exist;
- the intended users, including whether it is personal, shared, or public;
- whether other people may operate, maintain, or contribute to it;
- its expected posture and lifespan: one-off, disposable, personal software, teaching exercise, internal/shared tool, open source, or another model;
- the essential experience or capability that makes the concept distinct;
- high-level success signals, boundaries, non-goals, and consequential constraints;
- existing context or alternatives that materially shape the concept.

Adapt rather than mechanically asking every topic. Stay at concept level. Defer detailed features, interfaces, architecture, technology choices, milestones, acceptance criteria, and other specification or planning details unless they expose a concept-level constraint. Do not prematurely turn exploratory answers into commitments.

When the concept appears coherent, summarize it briefly and ask one final question to confirm or correct the understanding. Resolve any resulting ambiguity before writing the document.

## Concept Document

Use the active project directory as the project root unless the user identifies another directory. Before creating project files, check whether the directory is empty and whether Git is already initialized. If it is empty and not already a Git repository, run `git init` there.

Create `.plans/` at the project root. Ensure the root `.gitignore` contains `/.plans/`, preserving existing entries and avoiding duplicates.

Write the agreed concept to `.plans/concept.md`. If that file already describes a different concept, choose a short descriptive filename instead of overwriting it. Keep the document concise and provisional. Capture:

- the working title and concept summary;
- the problem or opportunity and desired outcome;
- intended users and likely contributors or maintainers;
- project posture, audience, distribution, and expected lifespan;
- core experience or capabilities at a high level;
- success signals, boundaries, non-goals, and concept-level constraints;
- unresolved questions or assumptions that should carry into later specification work.

Include only sections that add useful information. Clearly label unresolved points; do not invent answers. Report the written path to the user.
