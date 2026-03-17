# Wiring — Heltec V3 Handheld

## Power Switch

The micro slide switch is wired inline on the **battery positive** wire. This cuts all power to the board without requiring a software shutdown.

```
Battery (+) ──── Switch IN
                 Switch OUT ──── Heltec JST 1.25 (+)
Battery (-) ─────────────────── Heltec JST 1.25 (-)
```

**Switch placement:** mounted in a boss on the back face of the enclosure. Terminals are accessible from the interior cavity. Wires route through a slot in the boss into the battery layer.

## Antenna

- u.FL connector is on the end of the V3 board opposite the USB-C port, centered
- u.FL pigtail routes through the notch in the PCB tray
- SMA bulkhead mounts in the right wall boss
- Hex nut seats in the interior hex pocket to prevent spinning during tightening

## JST Note

Heltec V3 uses **JST 1.25mm 2-pin** connector — not JST-PH (2.0mm). Verify before purchasing batteries or pigtails.
