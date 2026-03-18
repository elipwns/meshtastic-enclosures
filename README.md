# Meshtastic Enclosures

A library of 3D printed enclosures for Meshtastic nodes, designed for real-world use and published on MakerWorld.

Each configuration is self-contained — BOM, wiring notes, firmware config, build photos, and a MakerWorld link for print files all in one place.

---

## Configurations

| Config | Board | Power | Version | Status |
|---|---|---|---|---|
| [Heltec V3 Desktop Node](hardware/heltec-v3-desktop/) | Heltec WiFi LoRa 32 V3 | 1000mAh LiPo + power switch | v1.0.0 | ✅ Complete |
| Heltec V4 Desktop Node | Heltec WiFi LoRa 32 V4 | 1000mAh LiPo + power switch | — | 🟡 In progress |
| Heltec V4 Solar Node | Heltec WiFi LoRa 32 V4 | Solar + large LiPo, outdoor | — | 🔲 Planned |

---

## Versioning

Versions follow `MAJOR.MINOR.PATCH`:

- **Major** — breaking change to enclosure body (not backward compatible)
- **Minor** — new feature or supported board variant (e.g. new tray for V4)
- **Patch** — small fixes, tolerances, print setting tweaks

The enclosure body is designed to be shared across board variants where possible. Switching from a V3 to V4 tray should be a simple swap with no body reprint required.

---

## Roadmap

### v1.1.0 — Heltec V4 Tray
Same enclosure body as v1.0.0. New tray to accommodate the Heltec WiFi LoRa 32 V4, which has a slightly different footprint. Swap the tray, keep everything else.

### v2.x — Outdoor / Solar Series
Sealed outdoor enclosures with weatherproofing. The Heltec V4 includes onboard solar charging circuitry, making it the natural target board for a solar-capable node. Planned features:
- IP-rated gasket seal
- External solar input / panel mount
- Larger LiPo capacity
- Pole or wall mount points

---

## Design Philosophy

- **Modular** — main body is shared across board variants; swap tray and lid as needed
- **Printable on any FDM printer** — no supports required where possible
- **PETG** for durability and light UV resistance
- **M3 heat inserts** for repeatable, reliable assembly
- **Button access via holes** — buttons are rarely needed; holes allow poking through with a pin or pen rather than dedicating print volume to plungers
- Designed for real hardware, measured with calipers

---

## Repo Structure

```
hardware/
└── [config-name]/
    ├── README.md        # Full build guide
    ├── bom.md           # Bill of materials with links
    ├── wiring.md        # Wiring diagrams and notes
    ├── bambu/           # Bambu Studio .3mf link + print settings
    ├── firmware/        # Meshtastic config notes
    └── media/           # Photos and assembly shots
```

Print files (.3mf) are hosted on MakerWorld, not stored in this repo.

---

## Tools Used

- **CAD:** Onshape (free, browser-based)
- **Slicer:** Bambu Studio
- **Printer:** Bambu Lab
- **Firmware:** [Meshtastic](https://meshtastic.org)
