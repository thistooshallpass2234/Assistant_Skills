---
name: suricata-alert-triage
description: Triage Suricata EVE JSON alerts, validate signatures, and improve IDS/IPS detections. Use for defensive monitoring, PCAP replay, and lab rule tuning.
---

# Suricata Alert Triage

## Workflow
1. Record Suricata version, ruleset source/version, run mode, and EVE log path.
2. Parse EVE JSON; preserve the original log and timestamps.
3. Group alerts by signature, source/destination, destination port, flow ID, and time window.
4. Inspect signature metadata, classification, references, and packet evidence.
5. Check whether the rule matched a known test, benign application, scanner, or actual suspicious behavior.
6. Correlate with Zeek, firewall, endpoint, DNS, and authentication logs.
7. Assign confidence and severity separately; an alert severity field is not a complete risk assessment.
8. Tune rules narrowly and test against both positive and benign samples.
9. Document changes and retain before/after results.

## Example JSON parsing
`jq -r 'select(.event_type=="alert") | [.timestamp,.src_ip,.dest_ip,.alert.signature,.alert.category,.alert.severity] | @tsv' eve.json`

## Safety and quality
Do not suppress a broad signature solely to reduce alert volume. Avoid putting secrets or sensitive payloads in reports. Confirm whether Suricata ran in IDS or IPS mode before recommending operational changes.
