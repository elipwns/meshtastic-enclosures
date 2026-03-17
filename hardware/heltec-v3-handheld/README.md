# Heltec V3 Handheld Enclosure

A compact handheld Meshtastic node built around the Heltec WiFi LoRa 32 V3. Works as a portable unit, desktop node, or clip-to-bag radio.

---

## Overview

**Three-part modular design:**
- `main-body.stl` — the enclosure shell with battery cavity, heat insert pillars, SMA boss, switch boss
- `pcb-tray.stl` — floating tray that cradles the V3 board, located by the case and captured by the lid screws
- `lid.stl` — top face with OLED window, two button holes, four screw holes
- `button-plunger.stl` — captive plunger for PRG/USR buttons, inserts from inside during assembly

---

## Print Settings

| Setting | Value |
|---|---|
| Material | PETG |
| Layer height | 0.2mm |
| Infill | 20% gyroid |
| Supports | None required |
| Perimeters | 3 |

Button plunger: print in TPU 95A for soft feel, or PETG for firm click.

---

## Assembly Order

1. Install M3 heat inserts into the four corner pillars (soldering iron, ~200°C)
2. Stick double-sided foam tape pads into the floor recesses
3. Place battery in cavity, route JST lead and switch wires
4. Wire power switch inline on battery positive
5. Drop PCB tray in, align with pillars
6. Seat Heltec V3 board into tray
7. Route u.FL pigtail through notch, connect to SMA bulkhead
8. Thread SMA bulkhead through boss hole, seat nut in hex pocket, tighten
9. Drop button plungers in from inside over PRG/USR buttons
10. Place lid, run 4x M3 screws through lid + tray into heat inserts
11. Connect antenna

---

See [bom.md](bom.md) for parts list and [wiring.md](wiring.md) for switch wiring details.
