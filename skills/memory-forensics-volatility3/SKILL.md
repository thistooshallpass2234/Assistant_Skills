---
name: memory-forensics-volatility3
description: Analyze authorized memory images using Volatility 3 to identify processes, network artifacts, injected code indicators, handles, and suspicious execution. Use for DFIR labs and incident investigations.
---

# Memory Forensics with Volatility 3

## Preserve and identify
- Work on a copy of the memory image.
- Record SHA-256, size, acquisition source/time, OS details if known, and Volatility version.
- Do not assume a plugin name or output schema without checking the installed version.

## Workflow
1. Confirm the image path and hash.
2. Run `vol -h` and inspect available plugins.
3. Identify OS/kernel context using the relevant supported plugin.
4. Enumerate processes and parent-child relationships.
5. Inspect command lines, loaded modules, handles, network connections, and suspicious process relationships where supported.
6. Compare process/network artifacts against known-good baselines and disk/log evidence.
7. For suspicious PIDs, use targeted plugins and preserve complete output.
8. Record plugin name, exact command, output file, and interpretation.

## Common starting points
Depending on image and plugin availability, investigate `windows.info`, `windows.pslist`, `windows.pstree`, `windows.cmdline`, `windows.netscan`, and `windows.dlllist`. Check `vol -h` for exact names and requirements.

## Interpretation
A process missing from one listing is not alone proof of hiding. Network artifacts can be stale or incomplete. Explain plugin limitations and corroborate findings with multiple sources.
