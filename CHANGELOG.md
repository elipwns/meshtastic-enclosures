# Changelog

All notable changes to this project will be documented here.

Format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).
Versioning follows `MAJOR.MINOR.PATCH` — see [README](README.md) for scheme details.

---

## [Unreleased] — v1.1.0

### Heltec V4 Desktop Node — In Progress

- New tray with 2mm board inset for wire routing relief around bottom-edge SH1.25-2P battery/solar connectors
- Body shared with V3 (no body changes)
- New lid (investigation needed — saved file may be a V3 copy)
- XY compensation dialed in: 0.25mm offset confirmed too generous for PLA; next test will use smaller value

---

## [1.0.0] — 2026-03-18

### Heltec V3 Desktop Node — Initial Release

First complete enclosure design. Targets the Heltec WiFi LoRa 32 V3 board as a simple indoor desktop Meshtastic node.

**Features:**
- Flat bottom for stable desktop placement
- SMA antenna passthrough
- Latching power switch cutout
- 1000mAh LiPo bay for battery backup
- Button access holes (no plungers — poke through with a pin or pen if needed)
- M3 heat inserts for repeatable assembly
- No supports required

**Files:**
- Body, tray, and lid STLs
- BOM with sourcing links
- Wiring notes
- Firmware config reference
- Build photos
