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
| Wireless Tracker — Chevy Bolt EV | Heltec Wireless Tracker (HTIT) | Hardwired 12V → 5V buck converter | — | 🔲 Planned |

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
- Battery and solar use SH1.25-2P connectors — both on the bottom edge of the board (awkward placement, acknowledged by Heltec)
- Wire routing solution: board is positioned 2mm further inward than V3 tray to give wires room to bend up from the bottom-edge connectors without being pinched against the tray wall
- GNSS port is a wide SH1.25-8P connector, also on the bottom edge — needs clearance in tray floor even if unused
- LoRa U.FL connector position may have shifted — verify before finalizing SMA bulkhead placement in lid
- V4 uses native USB-OTG (no CP2102 chip) — USB-C port shifts 2mm inward with board; verify cable reach with multiple cable types before finalizing

**V4 tray design decisions made:**
- Board inset 2mm further from USB-C wall vs V3 tray — gives wire bend relief for battery/solar connectors
- No underside component relief cutout needed — V4 PCB underside is clean, unlike V3 which required a cutout for surface mount components
- Same switch wiring approach as V3: SH1.25-2P connector on battery lead, switch inline on positive wire
- Do not use header pins for battery — must go through onboard BMS via the dedicated battery connector

### v1.2.0 — Handheld Series (V3 + V4)
Vertical handheld form factor, designed to be held in one hand like a radio. Separate body from the desktop series — this is a new major form factor.

**Design goals:**
- Comfortable one-handed grip
- Screen visible when raised
- PRG button accessible as a proper tactile press (not just a hole) — it's the primary user button in handheld use
- SMA antenna — stubby or flexible preferred over a long fixed whip
- Larger LiPo than desktop (2000–3000mAh) for all-day use
- Belt clip or loop mount point

**GPS — handheld only, not planned for desktop series:**
- Hardware on hand: ATGM336H UART GPS breakout modules with ceramic patch antenna
- V3 wiring: solder directly to GPIO pins (VCC, GND, TX, RX) — configure pin assignment in Meshtastic firmware
- V4 wiring: use an SH1.25-8P pigtail cable — connector plugs into the V4's dedicated GNSS port, bare leads solder to the GPS breakout pads
  - SH1.25 connector assortment kit (2P–10P) covers all V4 connectors — search "SH1.25 cable connector assortment kit" (~$10)
- GPS patch antenna needs a clear plastic window above it — design a shallow pocket in the lid or top of the body
- V4 firmware supports software-controlled GPS power off to save battery
- GPS integration is a stretch goal for v1 handheld — enclosure should accommodate it but not require it

### v2.x — Outdoor / Solar Series
Sealed outdoor enclosures with weatherproofing. The Heltec V4 includes onboard solar charging circuitry, making it the natural target board for a solar-capable node. Planned features:
- IP-rated gasket seal
- External solar input / panel mount
- Larger LiPo capacity
- Pole or wall mount points

### v3.x — Vehicle Series — Chevy Bolt EV (Wireless Tracker)
Permanent hardwired install in a Chevy Bolt EV using the Heltec Wireless Tracker (HTIT-Tracker). GPS is onboard — no external module needed. Always-on node, completely hidden, clean install.

**Power:**
- Tap directly from the 12V accessory battery with an inline fuse
- Bolt EV 12V stays topped up automatically by the HV traction battery — effectively always available
- 12V → 5V buck converter → USB-C into the Wireless Tracker board
- No switch needed — always-on by design; draw is negligible vs available capacity

**Placement:**
- Front trunk (frunk) — hidden, no interior clutter, completely invisible install
- Primary goal: looks like nothing was done to the car

**Antenna:**
- Antenna routing TBD pending physical inspection of frunk space
- Options: external antenna through a grommet, or internal antenna stuck to underside of hood (LoRa and GPS frequencies pass through plastic/fiberglass without issue)
- Wireless Tracker has separate U.FL ports for LoRa and GNSS — both can run external antennas if needed

**Notes:**
- Separate MakerWorld post from desktop/handheld series — different board, different use case
- Enclosure needs to be compact and mountable inside the frunk
- No display access required — node runs headless, configured via Meshtastic app over Bluetooth

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
