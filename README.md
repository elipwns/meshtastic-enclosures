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
| Heltec V3 Handheld | Heltec WiFi LoRa 32 V3 | LiPo, portable | — | 🔲 Planned |
| Heltec V4 Handheld | Heltec WiFi LoRa 32 V4 | LiPo + optional GPS, portable | — | 🔲 Planned |

---

## Versioning

Versions follow `MAJOR.MINOR.PATCH`:

- **Major** — breaking change to enclosure body (not backward compatible)
- **Minor** — new feature or supported board variant (e.g. new tray for V4)
- **Patch** — small fixes, tolerances, print setting tweaks

The enclosure body is designed to be shared across board variants where possible. Switching from a V3 to V4 tray should be a simple swap with no body reprint required.


---

## Roadmap

### v1.1.0 — Heltec V4 Desktop Tray + Lid
Same enclosure body as v1.0.0. New tray and lid to accommodate the Heltec WiFi LoRa 32 V4, which has a different footprint, repositioned connectors (battery, solar, GNSS), and a PC faceplate over the OLED. The V4 also adds a dedicated 8-pin GNSS connector — tray design will provide clearance for it even if GPS is not used.

**V4 connector notes for tray design:**
- Battery and solar use SH1.25-2P connectors (different from V3's JST-1.25) — both on the bottom edge
- GNSS port is a wide SH1.25-8P connector, also on the bottom edge
- LoRa U.FL connector position may have shifted — verify before finalizing SMA bulkhead placement
- V4 uses native USB-OTG (no CP2102 chip) — same USB-C port location but verify offset

### v1.2.0 — Handheld Series (V3 + V4)
Vertical handheld form factor, designed to be held in one hand like a radio. Separate body from the desktop series — this is a new major form factor.

**Design goals:**
- Comfortable one-handed grip
- Screen visible when raised
- PRG button accessible as a proper tactile press (not just a hole) — it's the primary user button in handheld use
- SMA antenna — stubby or flexible preferred over a long fixed whip
- Larger LiPo than desktop (2000–3000mAh) for all-day use
- Belt clip or loop mount point

**GPS considerations:**
- The V3 can use a UART GPS module (e.g. ATGM336H breakout) wired to GPIO pins — VCC, GND, TX, RX
  - Meshtastic supports this natively; GPIO pin assignment is set in firmware config
  - GPS patch antenna needs placement near the top of the enclosure with clear plastic above it
  - GPS adds meaningful utility to a handheld — live position on the Meshtastic mesh map
- The V4 has a dedicated onboard SH1.25-8P GNSS connector for direct module attachment
  - Same ATGM336H (or compatible) module, wired to the 8-pin connector instead of GPIO
  - V4 firmware can also software-control GPS power to save battery
- GPS integration is a stretch goal for v1 handheld — enclosure should be designed to accommodate it but not require it

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
