# Meshtastic Config — Heltec V3 Desktop Node

This covers flashing and configuring the Heltec WiFi LoRa 32 V3 for use as a desktop Meshtastic node. Settings are tuned for a fixed indoor node — always-on, plugged in or on LiPo backup, acting as a general mesh participant.

---

## 1. Flashing Firmware

**Easiest method — Web Flasher (no install required):**

1. Open [flasher.meshtastic.org](https://flasher.meshtastic.org) in Chrome or Edge (must be Chromium-based)
2. Connect Heltec V3 via USB-C
3. Select device: **Heltec WiFi LoRa 32 V3**
4. Select latest stable release
5. Click Flash — takes ~1 minute
6. Power cycle the board after flashing

**If the web flasher doesn't detect the board:**
- Try a different USB cable (many are charge-only — you need data capable)
- Install the CH340 or CP2102 driver if on Windows
- Hold the PRG button while plugging in to force bootloader mode

---

## 2. Initial Setup (Meshtastic App)

Download the Meshtastic app on iOS or Android. Connect via Bluetooth on first boot — the device will appear as `Meshtastic_XXXX`.


### Required settings

| Setting | Recommended Value | Notes |
|---|---|---|
| Region | `US` | Sets frequency to 915MHz — **must match your country** |
| Device name | Something identifiable | Shows up in the app and on other nodes' maps |
| Node role | See below | |

### Node Role

For this desktop enclosure, choose based on placement:

| Role | Use when... |
|---|---|
| `CLIENT` | Node is on a desk, used actively, no special placement |
| `ROUTER_CLIENT` | Node has good line of sight — window, elevated, or roof — helps relay messages |
| `ROUTER` | Fixed, always-on, not used for direct messaging — pure relay node |

A desktop node near a window is a good candidate for `ROUTER_CLIENT`. It participates in the mesh and helps relay for nearby nodes without requiring you to do anything extra.

---

## 3. Radio Settings

Defaults are fine to start. Leave these alone until you understand the mesh in your area:

| Setting | Default | Notes |
|---|---|---|
| Modem preset | `LONG_FAST` | Good balance of range and throughput for most use |
| Transmit power | Max (30 dBm) | Fine for desktop use indoors |
| Hop limit | 3 | Standard — increase only if your mesh is sparse |


---

## 4. Display & Power Settings

The V3 has a small OLED display. For a desktop node left running, these settings help:

| Setting | Recommended | Notes |
|---|---|---|
| Screen timeout | 30–60 seconds | No reason to leave it on constantly |
| Bluetooth timeout | 0 (never) | Keep BT always available for app access |
| Power save mode | Off | Node is on LiPo backup or USB — keep radio always active |

---

## 5. Channels

Out of the box the node joins the default public channel (`LongFast`). This is fine for connecting to your local mesh.

If you want a private channel for messaging with specific people:
- Add a secondary channel with a shared name + PSK (pre-shared key)
- Share the QR code with whoever you want on that channel
- The node will receive and relay traffic on all configured channels

---

## 6. Useful Tips

- **Find your local mesh:** Check [meshtastic.liamcottle.net](https://meshtastic.liamcottle.net) for a live map of nodes in your area
- **V3 vs V4 firmware:** Always verify you're flashing the V3 variant — V4 firmware will not work on V3 hardware
- **Screen on button press:** The PRG button wakes the display — accessible via the button hole in the enclosure
- **USB-C stays accessible:** The enclosure keeps the USB-C port exposed for firmware updates and serial config without disassembly

