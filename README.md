# TRAP

> **Tactical Reconnaissance, Auditing & Penetration** — A curated collection of field kits, configurations, notes, and workflows for wireless auditing, hardware implants, and hacker conference survival (WiFi Pineapples, Hak5/GoHakMe gear, DEFCON, RF/SDR, and portable lab setups).

---

##Disclaimer & Legal Notice

All material in this repository is strictly for **authorized security auditing, defensive research, CTF competitions, and educational lab environments**. Only test networks, RF spectrum, and hardware that you own or have explicit written authorization to assess. See [SECURITY.md](./SECURITY.md) for responsible disclosure and operational guidelines.

---

## Overview

**TRAP** serves as a central hub for portable security hardware, field operations, and conference tradecraft:

1. **Wireless Auditing & Hak5 Gear (`wifi-pineapple/`, `hak5/`)**
   - WiFi Pineapple setup, PineAP configurations, module notes, and defensive detection strategies.
   - USB Rubber Ducky, Bash Bunny, Key Croc, Shark Jack, Packet Squirrel, and LAN Turtle payload templates and defensive hardening.
   - GoHakMe / portable travel router configurations (OpenWrt, WireGuard/Tailscale, captive portal handling).

2. **DEFCON & Conference Tradecraft (`defcon/`)**
   - Conference hardening checklists (burner devices, Faraday pouches, cellular/WiFi/BLE isolation).
   - Village resources (Wireless Village / RFCTF, Hardware Hacking Village, Packet Hacking Village, Lockpick Village).
   - Badge hacking notes (SAOs / Shitty Add-Ons, I2C, UART, SWD/JTAG pinouts).

3. **RF, SDR & Bluetooth (`rf-sdr/`)**
   - Software Defined Radio (HackRF, Flipper Zero, RTL-SDR, Proxmark3) frequency references and lab notes.
   - BLE / Wi-Fi reconnaissance (Kismet, Bettercap, hcxdumptool) and rogue AP detection.

4. **Field Lab & Termux Workflows (`termux-field-kit/`)**
   - Running headless auditing and monitoring tools from Android / Termux on the go.
   - USB OTG serial, UART debugging, and external wireless adapter management.

---

## Repository Structure

| File / Directory | Description |
| :--- | :--- |
| [`README.md`](./README.md) | Project overview, quick-start guides, and hardware index |
| [`ARCHITECTURE.md`](./ARCHITECTURE.md) | Directory layout, hardware stack architecture, and network topologies |
| [`ROADMAP.md`](./ROADMAP.md) | Planned guides, hardware modules, and scripts |
| [`TIL.md`](./TIL.md) | Field notes, quick tips, CLI one-liners, and "Today I Learned" snippets |
| [`SECURITY.md`](./SECURITY.md) | Rules of engagement, OPSEC guidelines, and vulnerability reporting |
| [`CONTRIBUTING.md`](./CONTRIBUTING.md) | Guidelines for adding new hardware profiles, payloads, or field notes |
| [`CHANGELOG.md`](./CHANGELOG.md) | Version history and documentation updates |

---

## Quick Reference: Essential Field Kit

### Core Hardware Stack
- **Wireless Auditing:** WiFi Pineapple (Mark VII / Tactical), Alfa AWUS036ACM / AWUS036ACH (mt76x2u / rtl8812au)
- **Travel & Isolation:** GL.iNet OpenWrt Travel Router (Beryl AX / Slate AX) with Always-On WireGuard
- **Multi-Tool / RF / RFID:** Flipper Zero, Proxmark3 Easy/RDV4, HackRF One + PortaPack
- **Mobile Command:** Android device running Termux + Nethunter / USB-C OTG Ethernet & Serial adapters

### Common Field Sanity Checks
Before operating in an untrusted environment (e.g., DEFCON / hotel networks):
- [ ] Disable auto-connect on all saved Wi-Fi SSIDs (`Preferred Network Offload` / karma mitigation)
- [ ] Disable Bluetooth, NFC, AirDrop / Quick Share, and Wi-Fi Direct when not actively in use
- [ ] Verify VPN kill-switch and DNS-over-HTTPS / DNS-over-TLS on travel router
- [ ] Use USB data blockers ("charge-only" adapters) on any public power port
