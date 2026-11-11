# Roadmap

Planned additions and milestones for the **TRAP** documentation and toolkit.

---

## Phase 1: Foundation & Core Docs (Current)
- [x] Initialize core repository structure and documentation (`README.md`, `ARCHITECTURE.md`, `SECURITY.md`, `TIL.md`)
- [x] Establish baseline configuration templates (`.env.example`, `.gitignore`, `.editorconfig`)
- [ ] Create directory structure for `docs/`, `configs/`, and `scripts/`

## Phase 2: WiFi Pineapple & GoHakMe / Hak5 Guides
- [ ] **WiFi Pineapple Field Guide:** Initial hardening, USB-C OTG tether via Termux/Android, PineAP filter rules (strict SSID/MAC scoping), and pcap capture workflows.
- [ ] **GoHakMe / OpenWrt Travel Kit:** Configuring GL.iNet / OpenWrt routers for MAC randomization, TTL normalization, DNS leak prevention, and WireGuard tunneling.
- [ ] **Cloud C2 Self-Hosting:** Running a self-hosted Hak5 Cloud C2 instance over a private WireGuard mesh.

## Phase 3: DEFCON & Conference Survival
- [ ] **Pre-Flight OPSEC Checklist:** Device prep before arriving in Las Vegas (burner profiles, eSIM setups, hardware kill-switches).
- [ ] **Blue Team / Rogue AP Detection:** Using Kismet and `hcxdumptool` / `bettercap` defensively to identify Evil Twin / KARMA / MANA attacks in real time.
- [ ] **Hardware & Badge Village Reference:** SAO (Shitty Add-On) 6-pin standard pinout, UART/I2C logic analyzer cheat sheets.

## Phase 4: Termux & Mobile Integration
- [ ] **Termux Pocket Rig:** Controlling external radios and Hak5 gear directly from an Android phone over USB-C OTG.
- [ ] **Automated PCAP Triage:** Lightweight shell/Python scripts to summarize beacon frames, probe requests, and EAPOL handshakes from field captures.
