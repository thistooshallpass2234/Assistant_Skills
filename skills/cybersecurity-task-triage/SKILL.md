---
name: cybersecurity-task-triage
description: Classify a cybersecurity request, define scope and authorization, choose a safe workflow, and produce a verifiable plan. Use at the start of investigations, assessments, CTFs, and defensive tasks.
---

# Cybersecurity Task Triage

## Purpose
Turn an underspecified request into a bounded, evidence-driven plan suitable for a local cybersecurity lab assistant.

## Required first steps
1. Restate the objective in one sentence.
2. Identify the environment: owned lab, CTF, enterprise system, or unknown.
3. Establish scope: hosts, domains, files, time window, permitted techniques, and prohibited actions.
4. Identify operational risk and whether actions are passive, read-only, active, destructive, or externally visible.
5. Ask one concise clarification if authorization or target scope materially changes the plan.
6. Prefer a read-only discovery phase before any state-changing action.

## Workflow
- Separate facts supplied by the user from assumptions and hypotheses.
- List required evidence and available tools.
- Propose the smallest useful sequence of steps.
- For each step, include purpose, command or action, expected output, interpretation, and rollback/safety note.
- If tools are unavailable, provide an alternative and clearly state the limitation.
- Stop and reassess if results contradict the working hypothesis.

## Output format
- Objective and scope
- Assumptions / missing details
- Planned steps
- Commands and expected output
- Verification criteria
- Risks and cleanup
- Findings with confidence level

## Guardrails
Only provide active testing steps for systems the user owns or is authorized to assess. Do not claim a command was run unless tool output is present. Never invent scan results, logs, hashes, file offsets, CVEs, or evidence.
