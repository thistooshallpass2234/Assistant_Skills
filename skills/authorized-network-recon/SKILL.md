---
name: authorized-network-recon
description: Plan and interpret scoped network discovery and service enumeration using Nmap and common network utilities. Use for owned lab ranges, CTF targets, and explicitly authorized assessments.
---

# Authorized Network Reconnaissance

## Tools
Nmap, `ip`, `ss`, `ping`, `traceroute`/`tracepath`, `dig`, `host`, `curl`, `nc`, `tcpdump`.

## Preconditions
- Confirm target IPs/CIDRs and written or explicit authorization.
- Confirm allowed scan intensity, time window, and exclusions.
- Prefer a lab VLAN or isolated VM network for practice.

## Workflow
1. Record scope and timestamp.
2. Check local interface, route, and DNS context.
3. Start with low-impact host discovery where permitted.
4. Enumerate only approved TCP/UDP ports; explain UDP uncertainty.
5. Use service/version detection only where permitted and useful.
6. Save raw output (`-oA`) and record exact command, tool version, and target scope.
7. Validate important findings with a second source or targeted manual check.
8. Translate results into assets, exposed services, evidence, and remediation.

## Example for an isolated lab
`nmap -sV -sC -oA scan-lab 192.168.56.10`

This example is for a host in a controlled lab. Do not expand the target range without approval.

## Interpretation notes
- `open|filtered` and `filtered` are not proof that a service is absent.
- Service fingerprints can be wrong; corroborate before reporting.
- A port number alone does not prove the service identity.
- Keep raw outputs; do not paste secrets or sensitive production data into public services.

## Deliverable
A table with host, port/protocol, observed service, evidence, confidence, risk, and recommended validation/remediation.
