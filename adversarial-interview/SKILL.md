---
name: adversarial-interview
description: Delegate an independent adversarial review of a proposed concept, project, application, or feature, then help the user decide its fate. Use only when explicitly invoked.
---

# Adversarial Interview

Pressure-test the proposal rather than validating it. This skill may follow a concept or design interview or operate independently.

## Prepare the Review

Identify the documents that most directly express the proposal and its assumptions. Prefer files the user names and relevant documents in `.plans/` if applicable; include other material only when it materially affects the idea being reviewed.

The reviewer must not inherit the parent conversation. If the proposal exists only in the invocation message, pass that text verbatim as neutral review material. If neither the documents nor the invocation contain enough information to identify the proposal, ask the user for the missing artifact or context before delegating.

## Delegate

Spawn one independent subagent with `fork_turns: "none"`. Omit model and reasoning-effort overrides so it inherits the parent thread's model and effort. Supply an override only when the user explicitly requests one.

Give the subagent the relevant file paths and only the minimal neutral context needed to interpret them. Do not disclose the parent's opinions, prior conclusions, or conversational history. Instruct it to:

- read the supplied documents before judging the proposal;
- make the strongest reasonable case against proceeding as proposed;
- challenge the problem framing, premises, claimed value, audience, incentives, feasibility, timing, scope, risks, and opportunity cost where relevant;
- surface contradictions, unsupported assumptions, failure modes, and evidence that would falsify the concept;
- identify materially different alternatives, including simpler approaches and doing nothing;
- distinguish document-supported facts from inference and unknowns;
- rank the most consequential findings and state whether they imply minor revision, fundamental reconception, abandonment, or no material change;
- return a concise review without editing files or taking external actions.

Wait for the subagent to finish. If it reports a genuine information gap, either resolve it from the scoped documents or ask the user; do not fill the gap with invented facts.

## Discuss the Findings

Present the strongest findings faithfully, while independently checking whether the critic overstates any point or relies on unsupported assumptions. Make an initial recommendation when the evidence supports one.

Discuss the review with the user and collaboratively choose among:

- preserve the concept as-is;
- make minor revisions;
- reconceptualize it from first principles;
- scrap it.

The review is advisory. Do not edit documents, revise the proposal, begin planning or implementation, delete work, or take any other follow-on action until the user approves a specific course of action. Approval of one action does not imply approval of others.
