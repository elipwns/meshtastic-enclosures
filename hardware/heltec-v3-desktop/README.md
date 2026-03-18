# Heltec V3 Desktop Node — Build Guide

**Version:** v1.0.0
**Board:** Heltec WiFi LoRa 32 V3
**Status:** ✅ Complete

A simple indoor Meshtastic node designed to sit on a desk. Holds a small LiPo for battery backup, has a clean antenna exit, and a latching power switch. Nothing fancy — just a solid, printable enclosure for a permanent indoor node.

---

## What It Is

- Desktop form factor — flat bottom, stable, tidy
- SMA antenna passthrough on the back/side
- Latching power switch on the outside
- 1000mAh LiPo tucked inside for brief power backup
- Button access holes — the V3 has two buttons (RST and PRG); they're rarely needed in normal operation, so instead of plungers there are small holes you can poke through with a pin, toothpick, or pen

---

## Bill of Materials

See [bom.md](bom.md) for full parts list with links and quantities.

**Summary:**
- Heltec WiFi LoRa 32 V3
- 1000mAh 3.7V LiPo (with JST connector)
- Latching rocker or push switch (panel mount)
- SMA pigtail or antenna with SMA connector
- M3 heat set inserts (×4)
- M3×8 screws (×4)
- 3D printed parts (see STLs below)

---

## Printed Parts

All STLs are in the [`stl/`](stl/) folder.

| File | Material | Notes |
|---|---|---|
| `body.stl` | PETG | Main enclosure shell |
| `tray-v3.stl` | PETG | Board cradle specific to Heltec V3 |
| `lid.stl` | PETG | Top cover |


**Print settings (Bambu Studio / FDM):**
- Layer height: 0.2mm
- Walls: 3
- Infill: 15–20% — gyroid or grid
- Supports: None required
- Material: PETG recommended — better durability and light UV resistance vs PLA

---

## Assembly

1. Install M3 heat set inserts into the body (4 corners) using a soldering iron
2. Slide the Heltec V3 into the tray; it should sit flush
3. Route the SMA pigtail through the antenna hole before seating the board
4. Connect the LiPo to the Heltec's JST port
5. Wire the power switch in-line with the LiPo positive lead (or use Heltec's onboard switch header if preferred)
6. Tuck the LiPo flat under or beside the board
7. Close the lid and secure with M3×8 screws

See [`media/`](media/) for build photos.

---

## Wiring

See [wiring.md](wiring.md) for the full diagram and notes.

**Quick summary:**
- LiPo → power switch → Heltec JST input
- SMA pigtail → Heltec antenna connector (U.FL)
- No other external wiring required for basic node operation

---

## Firmware

See [`firmware/`](firmware/) for Meshtastic config notes specific to this build.

Basic setup:
- Flash Meshtastic firmware for Heltec WiFi LoRa 32 V3 from [meshtastic.org/downloads](https://meshtastic.org/downloads)
- Connect via Bluetooth or USB to configure channel, region, and role
- Recommended role: `CLIENT` for a general node, `ROUTER_CLIENT` if it has good line of sight

---

## Photos

See [`media/`](media/) for completed build photos.
