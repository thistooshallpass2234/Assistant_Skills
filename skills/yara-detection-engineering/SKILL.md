---
name: yara-detection-engineering
description: Create, test, and maintain YARA rules for authorized malware triage and threat hunting. Use when turning observed artifacts into reusable file detections.
---

# YARA Detection Engineering

## Workflow
1. Define the family/campaign or behavior the rule is intended to detect.
2. Identify stable, discriminative strings or byte patterns from multiple known samples.
3. Avoid overly generic strings, timestamps, file paths, and single weak indicators.
4. Use file-type or size constraints only when justified by evidence.
5. Write a descriptive rule name, metadata, references, and a clear condition.
6. Test against known-positive samples and a representative benign corpus.
7. Measure false positives and document known blind spots.
8. Version the rule and retain test results.

## Example skeleton
```yara
rule Lab_Suspicious_Sample_Example
{
  meta:
    description = "Example template; not a production detection"
    author = "Your Name"
    date = "2026-10-28"
    confidence = "low"

  strings:
    $marker = "replace_with_observed_unique_marker" ascii

  condition:
    uint16(0) == 0x5A4D and $marker
}
```

This is a template, not a claim that the marker is malicious. Replace it with validated sample evidence.

## Quality checks
Run the installed YARA version's syntax/test command, test positives and negatives, and inspect rule matches before deploying. Avoid destructive actions based only on a YARA hit.
