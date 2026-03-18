# Wiring — Heltec V3 Desktop Node

## Power Switch

The micro mini slide switch is wired inline on the **battery positive** wire. This cuts all power to the board without requiring a software shutdown.

```
Battery (+) ──── Switch IN
                 Switch OUT ──── Heltec JST 1.25 (+)
Battery (-) ─────────────────── Heltec JST 1.25 (-)
```

The switch mounts in the enclosure wall. Both terminals are accessible from the interior cavity for soldering. Route wires cleanly to avoid pinching when closing the lid.

---

## Antenna

- U.FL connector is on the end of the V3 board opposite the USB-C port, centered
- Route the u.FL pigtail through the notch in the PCB tray before seating the board
- SMA bulkhead mounts in the 6.6mm hole in the enclosure wall
- The hex pocket on the interior face seats the SMA nut to prevent spinning during tightening
- Tighten the SMA bulkhead nut from the outside once the pigtail is connected

---

## Button Access

The V3 has two buttons: **RST** (reset) and **PRG** (program/boot). In normal Meshtastic operation these are rarely needed. The enclosure provides small access holes aligned to each button — use a pin, toothpick, or pen to reach them if required.

---

## JST Note

Heltec V3 uses **JST 1.25mm 2-pin** — not JST-PH (2.0mm). Verify polarity before connecting. Most Heltec-compatible LiPos are wired correctly but always double-check before first power-on.
