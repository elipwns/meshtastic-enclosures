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
- 1000mAh LiPo mounted to the floor of the enclosure on foam tape pads
- Button access holes — the V3 has two buttons (RST and PRG); they're rarely needed in normal operation, so instead of plungers there are small holes you can poke through with a pin, toothpick, or pen

---

## Bill of Materials

See [bom.md](bom.md) for full parts list with links and quantities.

**Summary:**
- Heltec WiFi LoRa 32 V3
- 1000mAh 3.7V LiPo (with JST connector)
- Micro mini slide switch (panel mount)
- SMA pigtail or antenna with SMA connector
- M3 heat set inserts (×4)
- M3×20mm screws (×4)
- 3D printed parts (see below)

---

## Printed Parts

Print files are hosted on MakerWorld — see [`bambu/README.md`](bambu/README.md) for the link and print settings.

**MakerWorld listing:** [Meshtastic Enclosure — Heltec WiFi LoRa 32 V3 Desktop Node](https://makerworld.com/en/models/2542854-meshtastic-enclosure-heltec-wifi-lora-32-v3#profileId-2799773)

| Part | Material | Notes |
|---|---|---|
| `body` | PETG | Main enclosure shell |
| `tray-v3` | PETG | Board cradle specific to Heltec V3 |
| `lid` | PETG | Top cover |

**Print settings:**
- Layer height: 0.2mm
- Walls: 3
- Infill: 15–20% — gyroid or grid
- Supports: None required
- Material: PETG recommended — better durability and light UV resistance vs PLA

---

## Assembly

1. Install M3 heat set inserts into the body (4 corners) using a soldering iron
2. Press the slide switch into its cutout in the enclosure wall
3. Solder wires to the switch terminals
4. Apply a small dab of hot glue around the base of the switch and over the solder joints — this locks the switch in place and provides strain relief for the wires
5. Stick two 12×12mm foam tape pads onto the battery shelf on the floor of the enclosure
6. Press the LiPo onto the foam tape pads — it should sit flat and secure
7. Slide the Heltec V3 into the tray; it should sit flush
8. Route the SMA pigtail through the antenna hole before seating the board
9. Connect the LiPo to the Heltec's JST port
10. Connect the switch wires in-line with the LiPo positive lead
11. Close the lid and secure with M3×20mm screws

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

---

## Photos

See [`media/`](media/) for completed build photos.
