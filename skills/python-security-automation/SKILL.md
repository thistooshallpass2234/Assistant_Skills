---
name: python-security-automation
description: Design reliable Python helpers for log parsing, IOC enrichment, evidence hashing, CSV/JSON transformation, and repeatable security workflows. Use for defensive automation and lab tooling.
---

# Python Security Automation

## Design rules
- Prefer Python standard library unless a dependency clearly adds value.
- Use explicit input/output paths and never overwrite source evidence by default.
- Handle malformed records and missing fields without silently discarding them.
- Keep secrets out of source code and logs.
- Use deterministic output, timestamps, structured logging, and clear exit codes.
- Add type hints, docstrings, and tests for parsing logic.
- Include dry-run mode for operations that change state.

## Workflow
1. Define input schema, output schema, and success criteria.
2. Create a small representative test fixture, including malformed and empty cases.
3. Implement a single-purpose function and validate assumptions.
4. Add error handling and summary counts.
5. Compare output with a known manual sample.
6. Document dependencies and execution instructions.
7. Review for path traversal, command injection, unsafe deserialization, and accidental data disclosure.

## Output expectations
Provide complete code, supported Python version, install steps, example invocation, sample output, tests, and limitations. Do not claim the script was executed unless actual execution output is available.
