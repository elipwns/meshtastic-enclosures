# Print Files — Heltec V3 Desktop Node

Print files are published on MakerWorld, not stored in this repository.

## Get the Files

**MakerWorld listing:** [Meshtastic Enclosure — Heltec WiFi LoRa 32 V3 Desktop Node](https://makerworld.com/en/models/2542854-meshtastic-enclosure-heltec-wifi-lora-32-v3#profileId-2799773)

The listing includes two print profiles:

| Profile | Material | Notes |
|---|---|---|
| PETG | PETG | Recommended — better durability and light UV resistance |
| PLA | PLA | Alternative — easier to print, fine for indoor desktop use |

---

## Print Settings

| Setting | Value |
|---|---|
| Layer height | 0.2mm |
| Walls | 3 (PETG) / 4 (PLA) |
| Infill | 15–20% |
| Supports | Not required |

---

## Material Notes

**PETG** is the recommended material. It handles heat better than PLA and is more impact resistant — a better long-term choice if the node will be moved around or sit near a window.

**PLA** is a perfectly valid choice for a desktop node that lives in a stable indoor environment. Avoid leaving a PLA print in a hot car or in direct sunlight — it can warp above ~60°C. Bump walls to 4 for a little extra rigidity since PLA is more brittle than PETG.

---

## Maintaining Both Profiles

When a design change is made, both `.3mf` files need to be updated and re-uploaded to MakerWorld:
1. Make the change in Onshape
2. Export updated STLs
3. Re-slice in Bambu Studio for PETG → save `.3mf` → upload to MakerWorld (PETG profile)
4. Switch filament to PLA, adjust wall count → save `.3mf` → upload to MakerWorld (PLA profile)

---

## For Non-Bambu Slicers

Both `.3mf` files can be opened in Orca Slicer and PrusaSlicer — geometry and settings should import cleanly. If you run into issues, open a GitHub issue and STLs can be exported on request.
