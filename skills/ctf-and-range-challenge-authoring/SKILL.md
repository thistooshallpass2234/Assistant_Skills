---
name: ctf-and-range-challenge-authoring
description: Create safe, reproducible cybersecurity training challenges with objectives, hints, artifacts, scoring, solution validation, and reset instructions. Use for a personal lab or authorized training range.
---

# CTF and Cyber Range Challenge Authoring

## Design requirements
- Target one or two measurable learning objectives.
- State the environment, difficulty, required tools, expected time, and allowed scope.
- Use synthetic identities, credentials, logs, packets, binaries, and domains.
- Keep intentionally vulnerable services isolated from the internet and host networks.
- Include a deterministic reset procedure and a clean solution-validation path.
- Avoid real secrets, public IP targets, destructive payloads, or uncontrolled persistence.

## Challenge package
1. `README.md`: scenario, scope, learning objectives, setup, rules.
2. `challenge/`: synthetic artifacts or intentionally vulnerable app.
3. `hints.md`: staged hints that do not immediately reveal the answer.
4. `solution.md`: instructor-only walkthrough and exact validation steps.
5. `tests/`: checks that verify the challenge is solvable and the flag is correct.
6. `reset.sh` or equivalent: safe cleanup/reset script with explicit target directory.
7. `manifest.json`: versions, hashes, expected flag format, and dependencies.

## Validation
- Rebuild from a clean snapshot.
- Solve using only documented scope and supplied artifacts.
- Verify every command and flag against actual output.
- Test hints for progressive usefulness.
- Confirm no route to the host, personal files, or external systems.
- Record known unintended solutions and false leads.

## Output
Provide learner-facing materials separately from instructor materials. Never include the answer or flag in learner-facing hints unless explicitly requested.
