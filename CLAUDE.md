# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Hardware design repository for 3D-printed enclosures housing Meshtastic LoRa mesh network nodes. No code, no build tools — this is a documentation and hardware design project. Designs are distributed via MakerWorld; `.3mf` slice files and STLs are **not** stored in this repo.

**Toolchain:** Onshape (CAD) → STL export → Bambu Studio (slicing) → MakerWorld (distribution)

## Repository Structure

Each enclosure configuration lives under `hardware/[board]-[form-factor]/` and is self-contained:

```
hardware/[config]/
├── README.md           # Build guide
├── bom.md              # Bill of materials with sourcing links
├── wiring.md           # Wiring diagram and electrical notes
├── CHANGELOG.md        # Per-config version history
├── MAKERWORLD.md       # Copy/paste content for MakerWorld listing
├── bambu/README.md     # Print settings; references MakerWorld .3mf files
├── firmware/           # Meshtastic flash + config instructions
└── media/              # Organized photos (hero/, detail/, assembly/, powered/, archive/)
```

Root-level `CHANGELOG.md` tracks project-wide releases; per-config changelogs track board-specific changes.

## Design Conventions

- **Modularity:** Main body is shared across board variants; only tray and lid differ per board
- **No supports required** — enforced at the CAD stage
- **Material preference:** PETG (primary), PLA (indoor/budget)
- **Hardware:** M3 heat set inserts in corner pillars + M3×20mm screws
- **Print settings:** 0.2mm layer height, 3 walls, 15–20% gyroid infill

## Versioning

`MAJOR.MINOR.PATCH` where:
- MAJOR = form factor change (desktop → handheld → vehicle)
- MINOR = new board variant within same form factor
- PATCH = fit fixes, print improvements, doc updates

## Adding a New Configuration

Follow the existing `heltec-v3-desktop/` as the template. Every config needs: README, bom.md, wiring.md, CHANGELOG.md, MAKERWORLD.md, bambu/README.md, firmware/meshtastic-config.md, and a media/ folder with at least hero shots.

## Current Configurations

| Status | Config | Notes |
|--------|--------|-------|
| ✅ v1.0.0 | `heltec-v3-desktop` | Published on MakerWorld |
| Planned | `heltec-v4-desktop` | Same body, new tray/lid |
| Planned | Heltec V3/V4 Handheld | Vertical form factor |
| Planned | RAK3401 Outdoor Solar | RAK WisBlock, 1W LoRa, solar, high-gain omni |
| Planned | Chevy Bolt EV Tracker | Vehicle install, hardwired 12V |
