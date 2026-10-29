---
name: secure-code-review
description: Review source code and configuration for common security weaknesses, unsafe defaults, secrets exposure, and dependency risks. Use for Python, shell, web application, IaC, and CI/CD reviews.
---

# Secure Code Review

## Workflow
1. Identify language, framework, entry points, trust boundaries, and sensitive data flows.
2. Review authentication, authorization, input validation, output encoding, cryptography, file/path handling, process execution, logging, and error handling.
3. Search for hard-coded secrets and unsafe configuration; do not print secrets in the report.
4. Check dependencies and lockfiles with an appropriate SCA tool.
5. Use SAST tools as aids, not as final proof.
6. Trace each suspected issue to reachable code and explain preconditions and impact.
7. Recommend a minimal patch and regression test.
8. Re-run relevant tests and scanners where execution is available.

## Finding format
File and line, vulnerable pattern, exploit preconditions, impact, confidence, minimal fix, test case. Quote only the code necessary to explain the issue and protect secrets.
