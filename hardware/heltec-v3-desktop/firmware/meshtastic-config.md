# Meshtastic Config — Heltec V3

## Flashing

1. Go to [flasher.meshtastic.org](https://flasher.meshtastic.org) in Chrome or Edge
2. Connect Heltec V3 via USB-C
3. Select device: **Heltec WiFi LoRa 32 V3**
4. Flash latest stable release

## Basic Config (via Meshtastic app)

| Setting | Value |
|---|---|
| Region | US (915MHz) |
| Node role | CLIENT (handheld) or ROUTER (fixed node) |
| Device name | Set to something identifiable |
| Bluetooth | Enabled for app pairing |

## Notes

- V3 and V4 require different firmware variants — do not flash V4 firmware onto V3
- Screen wakes on button press (PRG button)
- If screen is unresponsive after flash, check for corrosion on the display flex cable connector on the board
