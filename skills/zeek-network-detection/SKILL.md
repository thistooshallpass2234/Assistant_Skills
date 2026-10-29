---
name: zeek-network-detection
description: Use Zeek logs and scripts to investigate network behavior, establish baselines, and develop detections. Use for PCAP analysis, hunt hypotheses, and lab telemetry.
---

# Zeek Network Detection

## Core logs
`conn.log`, `dns.log`, `http.log`, `ssl.log`/`tls.log` depending on version, `files.log`, `notice.log`, `weird.log`, and `smtp.log` when generated.

## Workflow
1. Record Zeek version, input PCAP, command line, and output directory.
2. Process a copy of the PCAP and confirm logs were generated.
3. Establish baselines for endpoints, duration, bytes, services, DNS query patterns, and TLS metadata.
4. Form a specific hunt hypothesis (for example, periodic outbound connections or unusual DNS failures).
5. Filter logs using `zeek-cut`, `jq`, Python, or the available log viewer.
6. Correlate UIDs and timestamps across logs; preserve timezone assumptions.
7. Validate the hypothesis in packet data and other telemetry.
8. Document false-positive conditions and tune the detection.

## Example
`zeek -r sample.pcapng Log::default_logdir=zeek-out`

Exact options vary by installation. Check `zeek --help` and local documentation.

## Output
Hypothesis, relevant log fields, observed records, timeline, supporting packet references, false positives, detection logic, and next steps. Treat indicators as leads, not proof of maliciousness.
