---
name: stig-and-rmf-compliance
description: Support defensive hardening and compliance work using DISA STIGs, SCAP where applicable, NIST RMF, control evidence, and remediation tracking. Use for security engineering and audit preparation.
---

# STIG and RMF Compliance Support

## Workflow
1. Identify system type, operating system/version, baseline, classification, boundary, and applicable STIG release.
2. Obtain the authoritative current STIG/checklist and record its version/date.
3. Map each requirement to the system's actual configuration and evidence.
4. Classify results as pass, fail, not applicable, or not reviewed; document rationale.
5. Use approved SCAP/STIG automation where supported, but manually review context-dependent checks.
6. For each failure, record the rule ID, evidence, risk, corrective action, owner, and target date.
7. Retest after remediation and retain before/after evidence.
8. Map relevant findings to RMF controls and authorization artifacts without claiming an authorization decision.

## Evidence standards
Include command/tool used, timestamp, host context, sanitized output, configuration path, STIG version, rule ID, and reviewer notes.

## Guardrails
Do not fabricate compliance. A scanner result does not automatically establish full compliance. Confirm that automated changes are approved and reversible before applying them to a real system.
