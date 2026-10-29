---
name: packet-analysis-wireshark-tshark
description: Investigate PCAP/PCAPNG files and live captures using Wireshark, tshark, tcpdump, and protocol-aware reasoning. Use for network troubleshooting, incident response, and CTF analysis.
---

# Packet Analysis with Wireshark and TShark

## Inputs
Prefer a PCAP/PCAPNG file, capture time window, network context, and a specific question. Preserve the original evidence and work on a copy.

## Workflow
1. Record file name, size, SHA-256, capture interface/source, and acquisition time if known.
2. Confirm capture readability and packet/time range.
3. Establish baseline: protocols, endpoints, conversations, DNS, TLS, HTTP, and unusual traffic volume.
4. Use display filters to narrow hypotheses; explain the difference between capture filters and display filters.
5. Follow streams only when relevant; account for encryption, missing packets, NAT, and capture loss.
6. Extract artifacts to a separate working directory and document each extraction.
7. Correlate timestamps and endpoints with firewall, DNS, proxy, EDR, and host logs.
8. Validate findings against packet numbers and timestamps.

## Useful commands
- `capinfos sample.pcapng`
- `tshark -r sample.pcapng -q -z io,phs`
- `tshark -r sample.pcapng -Y 'dns || tls.handshake'`
- `tshark -r sample.pcapng -T fields -e frame.number -e frame.time -e ip.src -e ip.dst -e tcp.dstport`

Check installed TShark field names for the local version before relying on a field.

## Reporting
For every claim, include packet number(s), timestamp, relevant endpoints, filter used, and confidence. Do not infer payload content that is not visible in the capture.
