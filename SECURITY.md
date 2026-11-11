# Security Policy & Rules of Engagement

## 1. Authorized Use Only
The documentation, configurations, and scripts contained in **TRAP** are designed strictly for:
- Authorized penetration testing and red/blue/purple team engagements.
- Personal home labs and isolated Faraday/RF test benches.
- Capture The Flag (CTF) competitions (e.g., DEFCON Wireless Village / RFCTF).
- Defensive research, rogue AP detection, and personal OPSEC hardening.

**Never** deploy active wireless interception, deauthentication, or impersonation tools (such as PineAP KARMA/Evil Twin modules) against networks or devices without explicit written permission.

## 2. Operational Security (OPSEC) & Secret Hygiene
Contributors and operators must ensure sensitive data is never committed to this repository:
- **No Credentials:** Never commit WPA PSKs, enterprise certificates, SSH keys, WireGuard private keys, or Hak5 Cloud C2 tokens.
- **No Identifiable Captures:** Sanitize all `.pcap` / `.pcapng` examples and logs. Redact real BSSIDs, client MAC addresses, and geolocation (GPS/wigle) data unless generated in a synthetic lab environment.
- **Use `.env` Files:** Store local device IPs, interface names, and tokens in `.env` (which is ignored by git) based on [`.env.example`](./.env.example).

## 3. Reporting Security Issues
If you discover a leaked credential, vulnerability in a script in this repo, or an unsafe default configuration, please open an issue or contact the repository maintainer directly so it can be remediated and rotated immediately.
