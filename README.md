# Ollama Cybersecurity Skills Library

A modular, editable skill starter pack for a local cybersecurity assistant (including Ollama + Open WebUI). Skills are Markdown instructions, not executable plugins and not proof that a tool is installed.

## Included skill areas

- Task triage and authorization
- Network reconnaissance (authorized labs)
- Web application security testing
- Wireshark/TShark packet analysis
- Zeek network detection
- Suricata alert triage
- Incident response and timelines
- Volatility 3 memory forensics
- Disk and file forensics
- Malware static triage
- YARA detection engineering
- Vulnerability management
- DISA STIG / NIST RMF support
- Python security automation
- CTF and cyber-range challenge authoring
- Threat intelligence and IOC analysis
- Identity and access reviews
- Secure code review

## Recommended repository layout

```text
ollama-cybersecurity-skills/
├── README.md
├── SYSTEM_PROMPT.md
├── WORKFLOW.md
├── skills/
│   ├── cybersecurity-task-triage/SKILL.md
│   ├── authorized-network-recon/SKILL.md
│   └── ... one folder per skill
└── templates/
    ├── finding-template.md
    └── incident-timeline-template.csv
```

## How to use this with a local model

### Option A — Open WebUI Skills feature
If your Open WebUI version exposes Workspace > Skills, create/import skills using its supported interface. The exact import support varies by version. If it does not import a folder directly, create a skill and paste the corresponding `SKILL.md` contents. Keep each skill focused; select only the few relevant to the current task.

### Option B — Knowledge collection
Upload `SKILL.md` files into an Open WebUI Knowledge collection. Attach the collection to your model. Add a short system instruction telling the model to search the collection before technical tasks and cite the skill file it used. Retrieval behavior depends on model/tool support and Open WebUI configuration.

### Option C — Prompt-only workflow
Paste `SYSTEM_PROMPT.md` into the model's system prompt and include the relevant `SKILL.md` in a conversation or task prompt. This works without agent tool-calling but requires you to provide the skill text.

### Option D — Local repository workflow
Clone this repository on your Windows host or Kali/SIFT VM. Keep the Git repository as the source of truth, and copy or upload selected skills into Open WebUI when needed. Do not give an LLM unrestricted shell access just because a skill mentions a command.

## Important distinction: instructions vs tools

A skill describes how to use tools. It does not install Nmap, Volatility, Zeek, Suricata, YARA, Burp, or other utilities. Install tools separately in the appropriate VM/container and verify versions with `--version` or the tool's help command.

## Safe operating model

1. Use a dedicated lab VM/network and snapshots.
2. Start with read-only analysis and dry-run modes.
3. Require explicit confirmation for destructive or state-changing actions.
4. Preserve original evidence; hash files and log exact commands.
5. Never run unknown binaries on your host.
6. Scope active tests to systems you own or have written authorization to assess.
7. Treat model output as a hypothesis until verified by actual output or trusted documentation.

## Maintenance

- Review upstream tool syntax and current official documentation.
- Add a tested example and a known limitation to each skill.
- Keep tool-specific notes in `references/` when a skill grows.
- Use Git branches/commits for changes and record the date tested.
- Do not paste private logs, credentials, tokens, or sensitive evidence into public repositories.
