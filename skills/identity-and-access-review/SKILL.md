---
name: identity-and-access-review
description: Review identity, authentication, privilege, service accounts, MFA, and audit events for defensive security. Use for access reviews, incident response, and hardening.
---

# Identity and Access Review

## Workflow
1. Define the identity provider, tenant/domain, approved scope, and relevant time window.
2. Inventory users, privileged roles, service accounts, MFA status, and stale accounts using read-only exports where possible.
3. Review sign-in failures, unusual locations/devices, privilege changes, new credentials, and service-account activity.
4. Correlate events with change tickets, HR/offboarding records, endpoint telemetry, and known automation.
5. Validate least privilege and identify shared or non-expiring credentials.
6. Recommend staged remediation with owner, impact, rollback, and validation.
7. Record evidence and exceptions.

## Safety
Do not disable accounts, revoke sessions, rotate production secrets, or change authentication policies without explicit approval and a rollback plan. Redact tokens and personal data in reports.
