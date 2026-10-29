# Workflow: GitHub skills → Ollama → Open WebUI

## 1. Keep GitHub as the source of truth
Create a private repository first if you may later add internal procedures or lab notes. Commit the generic starter files, then make changes on a branch. Never commit credentials, live tokens, private PCAPs, malware samples you are not licensed to distribute, or identifiable incident records.

## 2. Pick the integration route

### Open WebUI Skills
Best when your installed version supports the Skills workspace. Make one skill per directory and keep the frontmatter name/description accurate. If your version lacks bulk import, add skills through the UI one at a time.

### Knowledge Base
Best for a library of reference instructions. Upload selected Markdown files, attach the collection to your model, and tell the model to retrieve relevant skill documents before giving tool-specific guidance. Smaller models may need a direct instruction to search knowledge rather than assuming retrieval happens automatically.

### System prompt + per-task file
Best for a simple, predictable baseline. Keep `SYSTEM_PROMPT.md` short. At the beginning of a task, provide only the matching skill, e.g. `skills/packet-analysis-wireshark-tshark/SKILL.md`.

## 3. Create model presets
Suggested presets:
- Cybersecurity Generalist: triage + system prompt
- DFIR Analyst: packet analysis, Zeek, incident response, memory forensics, disk forensics
- Detection Engineer: Suricata, Zeek, YARA, IOC analysis
- Security Engineer: vulnerability management, STIG/RMF, identity review, secure code review
- Lab Challenge Builder: CTF/range authoring + task triage

Avoid attaching all skills to every preset at once. More context is not automatically better, especially for smaller local models.

## 4. Keep execution separate
Initially, have the model propose commands and explain expected results. Run commands yourself in Kali, SIFT, or a disposable VM. If you later add tool calling, expose narrow allowlisted functions rather than unrestricted shell access. Require confirmation before actions that change system state.

## 5. Validate before trusting
Use a small benchmark set:
- Ask for a scoped Nmap plan against a host-only lab target.
- Ask the model to parse a short synthetic Suricata EVE JSON record.
- Ask it to build a UTC timeline from synthetic logs.
- Ask it to explain a Volatility 3 command while checking plugin names against local `vol -h`.
- Ask it to create a safe CTF plan with a reset procedure.
Score correctness, invented claims, scope discipline, and clarity. Save prompts and actual outputs so you can compare model/prompt changes.

## 6. Keep skills current
Record `tested_on`, tool version, OS, and a short validation example in each skill as you customize it. Review upstream official docs after major releases. Treat copied community skill repositories as untrusted code and instructions: inspect before importing.
