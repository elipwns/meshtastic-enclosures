# Wiring — Heltec V4 Desktop Node

Same circuit as the V3 build. The only physical difference is the power port placement on the V4 board, which shifts the switch cutout location on the enclosure wall.

---

## Power Switch

The micro mini slide switch is wired inline on the **battery positive** wire. This cuts all power to the board without requiring a software shutdown.

```
Battery (+) ──── Switch IN
                 Switch OUT ──── Heltec JST (+)
Battery (-) ─────────────────── Heltec JST (-)
```

The switch press-fits into its cutout in the enclosure wall. After soldering, apply a small dab of hot glue around the base of the switch and over the solder joints. This locks the switch in place and provides strain relief — prevents the wires from flexing at the joint during use.

<!-- TODO: Note exact switch cutout location on V4 body once confirmed -->

---

## Antenna

- U.FL connector is on the V4 board <!-- TODO: confirm location relative to USB-C port -->
- Route the u.FL pigtail through the notch in the PCB tray before seating the board
- SMA bulkhead mounts in the 6.6mm hole in the enclosure wall
- The hex pocket on the interior face seats the SMA nut to prevent spinning during tightening
- Tighten the SMA bulkhead nut from the outside once the pigtail is connected

---

## Button Access

The V4 has RST and PRG buttons. In normal Meshtastic operation these are rarely needed. The enclosure provides small access holes aligned to each button — use a pin, toothpick, or pen to reach them if required.

---

## JST Note

<!-- TODO: Confirm V4 JST connector size before finalizing this section -->
Verify polarity before connecting. Always double-check before first power-on.
