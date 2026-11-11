# TIL (Today I Learned) & Field Notes

Quick reference notes, hardware quirks, CLI one-liners, and operational tips for WiFi Pineapples, Hak5 gear, OpenWrt routers, and DEFCON tradecraft.

---

## WiFi Pineapple & Wireless Auditing

### Always Scope PineAP Filters First
Before enabling PineAP in a lab or authorized engagement, set both **Client Filter** and **SSID Pool Filter** to `Allow` (whitelist) mode. Leaving them in `Deny` (blacklist) mode in a dense RF environment will cause collateral associations from non-in-scope devices.

### Managing WiFi Pineapple via Termux / Android USB-C
When connected via USB-C Ethernet to a WiFi Pineapple Mark VII:
- Default management subnet: `172.16.42.0/24`
- Pineapple web UI: `http://172.16.42.1:1471`
- SSH access: `ssh root@172.16.42.1`

### Checking Monitor Mode & Frame Injection Support
```bash
# List wireless PHYs and supported interface modes
iw list | grep -A 10 "Supported interface modes"

# Put wlan1 into monitor mode using ip/iw (without airmon-ng killing NetworkManager)
ip link set wlan1 down
iw dev wlan1 set type monitor
ip link set wlan1 up
```

---

## GoHakMe / OpenWrt Travel Routers

### Captive Portal Bypass When DNS Rebinding Protection is Enabled
OpenWrt's `dnsmasq` enables `rebind_protection` by default, which blocks private IP responses (`10.x.x.x`, `192.168.x.x`) from upstream DNS servers—often breaking hotel and conference captive portals.
To temporarily log in to a captive portal:
1. Disable VPN kill-switch briefly or use the router's repeater login helper.
2. Temporarily allow upstream private DNS resolution or navigate directly to `http://neverssl.com` or `http://captive.apple.com`.
3. Re-enable `rebind_protection` and WireGuard immediately after authenticating.

---

## DEFCON & Conference Tradecraft

### SAO (Shitty Add-On) V1.69bis Pinout Reference
When building or probing conference badge add-ons (2x3 2.54mm header):
```text
  [1: VCC (3.3V)]  [2: GND]
  [3: SDA (I2C)]   [4: SCL (I2C)]
  [5: GPIO1]       [6: GPIO2]
```
*(Always verify with a multimeter before plugging an unknown SAO into an expensive badge!)*

### Detecting Evil Twins & Deauth Floods
Watch for sudden spikes in `802.11 Deauthentication` (`0xC0`) or `Disassociation` (`0xA0`) management frames paired with a new BSSID advertising the same SSID on a different channel or with mismatched RSN/WPA capabilities.
