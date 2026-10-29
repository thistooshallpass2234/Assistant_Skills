---
name: disk-and-file-forensics
description: Preserve and examine disk images, file metadata, deleted-file indicators, browser artifacts, and filesystem timelines using standard forensic utilities. Use for authorized DFIR and lab cases.
---

# Disk and File Forensics

## Evidence handling
- Preserve the original; use a forensic copy or read-only mount.
- Calculate and record cryptographic hashes before and after processing.
- Document acquisition method, source, operator, timestamps, and custody transfers.
- Do not mount unknown evidence read-write.

## Tool families
Autopsy/Sleuth Kit (`mmls`, `fls`, `icat`, `istat`, `tsk_recover`), `file`, `xxd`/`hexdump`, `exiftool`, Plaso/log2timeline, KAPE where appropriate, and browser-specific parsers.

## Workflow
1. Identify image format and partitions.
2. Determine filesystem and offsets before attempting extraction.
3. Build a file inventory and timeline.
4. Search for artifacts using documented terms and explain search limitations.
5. Extract relevant items to a separate evidence directory.
6. Hash extracted artifacts and preserve original paths/metadata.
7. Correlate timestamps carefully, including timezone and clock skew.
8. Verify key conclusions with a second tool or raw bytes where feasible.

## Reporting
Include image hash, partition/filesystem offsets, original path, artifact hash, relevant byte/record offsets, parser/tool version, and confidence. Never invent an offset or claim a deleted file is recoverable without evidence.
