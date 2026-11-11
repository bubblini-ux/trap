# Contributing to TRAP

Contributions of field notes, hardware guides, defensive detection rules, and configuration templates are welcome!

## How to Contribute
1. **Sanitize Everything:** Double-check that your contribution contains no real MAC addresses, SSIDs from private networks, API keys, or personal IPs.
2. **Test Your Commands:** Verify CLI commands and configs on actual hardware or clean OpenWrt/Linux/Termux environments before submitting.
3. **Keep Docs Modular:**
   - Quick tips and one-liners go in [`TIL.md`](./TIL.md).
   - Structural changes go in [`ARCHITECTURE.md`](./ARCHITECTURE.md).
   - Notable additions should be logged under `[Unreleased]` in [`CHANGELOG.md`](./CHANGELOG.md).
4. **Ethical Framing:** Include both offensive mechanics and defensive detection/mitigation notes whenever documenting an attack technique.
