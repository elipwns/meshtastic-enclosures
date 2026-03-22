# Bill of Materials — Heltec V4 Desktop Node

| Part | Spec | Qty | Notes |
|---|---|---|---|
| Heltec WiFi LoRa 32 V4 | 915MHz (US) | 1 | Flash with Meshtastic `heltec-v4` firmware |
| LiPo battery | 3.7V 1000mAh, 50.7 × 30 × 6.88mm, JST 1.25mm 2-pin | 1 | Same fit as V3 build |
| Micro mini slide switch | Panel mount, inline on battery positive | 1 | Cuts all power without software shutdown |
| SMA bulkhead | SMA female panel mount | 1 | 6.6mm hole, 7.96mm hex nut across flats |
| u.FL to SMA pigtail | ~100mm | 1 | Routes from board U.FL to bulkhead |
| Antenna | 915MHz flexible or rigid SMA | 1 | |
| M3 brass heat inserts | M3 × 4mm OD ~4.4mm | 4 | One per corner pillar |
| M3 screws | M3 × 20mm | 4 | Through lid + tray into inserts |
| Double-sided foam tape | ~12 × 12mm pads | 2 | Battery cushion / anti-rattle |

---

## Battery Note

The enclosure is designed around the **1000mAh Liter Energy 703048** (50.7 × 30 × 6.88mm). This fits with comfortable clearance.

A **2000mAh battery** (e.g. JLJLUP LP103450, ~100 × 34 × 10mm) also fits physically — tighter install but the lid closes cleanly. **Watch the connector:** many 2000mAh cells ship with a JST 2.0mm (JST-PH) plug, which may not match your board's JST port. You'll need to either source one pre-terminated with the correct connector, or cut and re-solder. Stick with 1000mAh if you want a drop-in install.

Any 3.7V LiPo with the correct JST connector will work as long as it fits within the battery shelf dimensions.

---

## Where to Buy

- **Heltec V4:** [heltec.org](https://heltec.org) or AliExpress — search "Heltec WiFi LoRa 32 V4"
- **LiPo battery (1000mAh):** Amazon — search "Liter Energy 703048" or "1000mAh 3.7V JST"
- **LiPo battery (2000mAh):** Amazon — search "JLJLUP LP103450 2000mAh" or "2000mAh 3.7V JST"
- **Slide switch:** Amazon or AliExpress — search "micro mini slide switch panel mount"
- **SMA bulkhead:** Amazon or AliExpress — search "SMA female panel mount bulkhead"
- **u.FL pigtail:** Amazon — search "u.FL to SMA pigtail 100mm"
- **Antenna:** Rokland, Amazon — 915MHz SMA
- **M3 heat inserts:** Amazon — search "M3 brass heat insert 4mm"
- **M3 screws:** Amazon — M3 × 20mm socket head or pan head

---

## JST Note

The Heltec V4 uses a **JST 1.25mm 2-pin** connector — same as the V3. Always double-check polarity before first power-on.
