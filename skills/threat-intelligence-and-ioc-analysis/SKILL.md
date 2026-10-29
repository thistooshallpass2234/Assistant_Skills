---
name: threat-intelligence-and-ioc-analysis
description: Evaluate indicators of compromise and open-source threat intelligence with provenance, confidence, time context, and defensive use. Use for alert enrichment, hunting, and incident triage.
---

# Threat Intelligence and IOC Analysis

## Workflow
1. Record the IOC exactly as observed, including source, timestamp, and context.
2. Normalize carefully: domain casing, URL components, IP format, file hash type, and timestamp timezone.
3. Check internal telemetry and trusted sources available to the analyst.
4. Distinguish source reputation from evidence that the IOC is related to this incident.
5. Evaluate freshness, confidence, possible shared hosting/CDNs, sinkholes, and false positives.
6. Correlate with endpoint, DNS, proxy, email, and network events.
7. Recommend proportionate controls and a monitoring period.
8. Record source URLs and retrieval dates for external intelligence.

## Guardrails
Do not attribute an incident to a threat actor from a single IP, domain, or hash. Do not visit suspicious links from a normal workstation. Avoid submitting private indicators or files to public services without authorization.
