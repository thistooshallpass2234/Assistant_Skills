---
name: web-application-security-testing
description: Perform a structured, authorized web application security review with browser devtools, Burp Suite or OWASP ZAP, curl, and OWASP testing guidance. Use for lab apps and approved assessments.
---

# Web Application Security Testing

## Scope and safety
Test only an application and accounts within the approved scope. Avoid destructive tests, real-user data, denial-of-service, and out-of-scope endpoints. Use test accounts and synthetic data.

## Tools
Browser developer tools, Burp Suite Community/Professional, OWASP ZAP, `curl`, browser storage inspection, dependency scanners, and source review where available.

## Workflow
1. Record base URL, roles, test accounts, excluded paths, and rules of engagement.
2. Map routes, forms, APIs, authentication, session handling, and security headers.
3. Establish a normal baseline request/response before changing one variable.
4. Check access control using two test accounts with different privileges.
5. Review input handling, output encoding, file upload controls, CSRF protections, session cookies, CORS, error handling, and API authorization.
6. Use passive scanning first; enable active checks only when explicitly allowed.
7. Reproduce each suspected issue minimally and retain sanitized request/response evidence.
8. Assess impact and confidence; distinguish confirmed vulnerabilities from observations.
9. Recommend fixes and regression tests.

## Evidence format
Finding ID, endpoint, role, preconditions, sanitized request/response, expected vs actual behavior, impact, confidence, remediation, retest result.

## Guardrails
Do not provide instructions to steal credentials, persist on a third-party system, exfiltrate real data, or bypass authorization outside an approved lab. Redact tokens, cookies, passwords, and personal data from evidence.
