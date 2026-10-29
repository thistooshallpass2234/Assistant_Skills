---
name: incident-response-and-timeline
description: Structure a defensive incident investigation from alert validation through containment, eradication, recovery, and lessons learned. Use for simulated or real incidents.
---

# Incident Response and Timeline

## Priorities
Protect people and critical services, preserve evidence, follow the organization's incident response plan, and avoid destroying volatile evidence unnecessarily.

## Workflow
1. Validate the alert and record who reported it, when, affected assets, and business impact.
2. Create an incident ID and maintain a decision/action log.
3. Define scope and severity using the organization's policy.
4. Preserve relevant logs and evidence with hashes, source, timestamps, and chain-of-custody notes.
5. Build a UTC-normalized timeline while retaining original timestamps and timezone metadata.
6. Assess likely initial access, execution, persistence, privilege use, lateral movement, and data access using available evidence.
7. Recommend containment proportionate to impact; identify dependencies and business approvals.
8. Determine eradication and recovery steps, credential/key rotation needs, and validation criteria.
9. Monitor for recurrence and produce an after-action report.

## Timeline fields
UTC timestamp, original timestamp/timezone, source, host/user, event, evidence reference, interpretation, confidence.

## Guardrails
Do not claim attribution from a single indicator. Do not delete files, wipe systems, disable accounts, or isolate production hosts without explicit authorization and an appropriate response process. Escalate suspected active compromise according to the user's incident plan.
