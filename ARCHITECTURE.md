# Architecture & Organization

This document outlines the structural layout of the **TRAP** repository and how field kits, network topologies, and hardware documentation are organized.

---

## 1. Planned Directory Layout

```text
trap/
├── docs/
│   ├── wifi-pineapple/     # PineAP configs, OOB management, tactical deployment
│   ├── hak5-ecosystem/     # Shark Jack, Key Croc, Bash Bunny, Packet Squirrel, C2
│   ├── gohakme-travel/     # OpenWrt travel routers, VPN tunnels, captive portal bypass
│   ├── defcon-survival/    # OPSEC checklists, village guides, badge & SAO specs
│   └── rf-sdr/             # Flipper Zero, HackRF, Proxmark3, Kismet setups
├── configs/
│   ├── openwrt/            # Sanitized network, firewall, and WireGuard templates
│   ├── kismet/             # Wardriving and WIDS/WIPS configuration files
│   └── termux/             # Shell aliases, tmux layouts, and USB OTG helper scripts
├── scripts/                # Defensive monitoring, PCAP triage, and setup helpers
└── README.md
```

---

## 2. Standard Field Network Topology

When operating in hostile or untrusted RF environments (such as conferences or field assessments), devices follow a segmented architecture:

```mermaid
flowchart LR
    Untrusted["Untrusted Upstream (Hotel / Conf Wi-Fi / WAN)"]
    TravelRouter["GoHakMe / OpenWrt Travel Router (Firewall + WireGuard)"]
    MgmtDevice["Operator Device (Termux / Laptop)"]
    AuditGear["Auditing Gear (WiFi Pineapple / SDR / Sensor)"]

    Untrusted -->|WAN / WISP| TravelRouter
    TravelRouter -->|Isolated VLAN / WG Tunnel| MgmtDevice
    MgmtDevice -->|Management Interface (USB-C / Ethernet)| AuditGear
```

### Design Principles
- **Out-of-Band (OOB) Management:** Always manage auditing appliances (like the WiFi Pineapple or Packet Squirrel) over wired USB-C Ethernet or a dedicated management interface rather than exposing management portals over untrusted Wi-Fi.
- **Zero Secrets in Repo:** All configuration files in this repository use placeholder variables defined in [`.env.example`](./.env.example). Never commit real PSKs, WireGuard private keys, or Cloud C2 tokens.
- **Reproducible Setups:** Scripts and configs should be idempotent and compatible with lightweight Linux environments (Debian, Alpine, OpenWrt, and Android/Termux).
