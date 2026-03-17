# Meshtastic Enclosures

A library of 3D printed enclosures for Meshtastic nodes, designed for real-world use and built to be published on MakerWorld.

Each configuration is self-contained — BOM, wiring notes, STLs, firmware config, and build photos all in one place.

---

## Configurations

| Config | Board | Power | Status |
|---|---|---|---|
| [Heltec V3 Handheld](hardware/heltec-v3-handheld/) | Heltec WiFi LoRa 32 V3 | 1000mAh LiPo + power switch | 🟡 In progress |
| Heltec V4 Handheld | Heltec WiFi LoRa 32 V4 | LiPo + solar input | 🔲 Planned |
| Heltec V4 Solar Node | Heltec WiFi LoRa 32 V4 | Solar + large LiPo, outdoor | 🔲 Planned |

---

## Design Philosophy

- Modular — main body is reusable across board configs, swap tray + lid
- Printable on any FDM printer, no supports required where possible
- PETG for durability, TPU plunger for button feel
- M3 heat inserts for repeatable assembly
- Designed for real hardware, measured with calipers

---

## Repo Structure

```
hardware/
└── [config-name]/
    ├── README.md        # Full build guide
    ├── bom.md           # Bill of materials with links
    ├── wiring.md        # Wiring diagrams and notes
    ├── stl/             # Print-ready STL files
    ├── firmware/        # Meshtastic config notes
    └── media/           # Photos and assembly shots
```

---

## Tools Used

- **CAD:** Onshape (free, browser-based)
- **Slicer:** Bambu Studio
- **Printer:** Bambu Lab
- **Firmware:** [Meshtastic](https://meshtastic.org)
