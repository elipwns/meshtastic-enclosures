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
   - **Do not bottom out the screw during test fit** — this pulls inserts out. Lower the pillar height until the screw stops with thread engagement remaining
2. Stick double-sided foam tape pads into the floor recesses
3. Place battery in cavity, route JST lead and switch wires
4. Solder wires to switch leads before installing switch
5. Insert power switch from inside the case into the boss pocket, actuator through the exterior slot
6. Drop PCB tray in, align with pillars
7. Seat Heltec V3 board into tray
8. Route u.FL pigtail through notch, connect to SMA bulkhead
9. Thread SMA bulkhead through boss hole, seat nut in hex pocket, tighten
10. Drop button plungers in from inside over PRG/USR buttons
11. Place lid, run 4x M3 screws through lid + tray into heat inserts
12. Connect antenna

---

## V1 Lessons Learned

- **Pillar height drives USB-C slot alignment** — if the slot doesn't line up, adjust pillar height in the model, not the slot position
- **Heat inserts:** do not bottom out the screw during first assembly — pulls the insert clean out. Use a screw length stop or be conservative on depth
- **Switch:** insert from inside the case, solder leads before installing. Inserting from outside risks melting the boss with the iron
- **Tray:** floating design (located by case walls, captured by lid screws) works well — easy to iterate tray independently without reprinting the body
- **Prototype clearances:** generous tolerances throughout made first assembly straightforward. Tighten on V2 based on what actually feels loose

---

## Planned V2 Changes

- [ ] Screw length stop inside pillar bore to prevent insert pull-out
- [ ] Lid underside ribs to sandwich PCB from above
- [ ] Tighter tolerances on battery cavity and tray fit
- [ ] Lid retention ribs for PCB
- [ ] Heltec V4 tray + lid variant (same body)

---

See [bom.md](bom.md) for parts list and [wiring.md](wiring.md) for switch wiring details.
