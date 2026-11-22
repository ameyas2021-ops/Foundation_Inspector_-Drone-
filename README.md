# Foundation Inspector Drone (fpv_drone_V1)

A small 3-inch FPV quadcopter built to fly into tight spaces, such as crawl spaces and the areas around a building's foundation, and inspect them on camera.

> **Status:** Work in progress. The frame and flight electronics are chosen, but the drone does not fly reliably yet. See [Project status](#project-status) and [Known issues](#known-issues).

## Table of contents

- [Why this project](#why-this-project)
- [Releases](#releases)
- [Hardware](#hardware)
- [Frame history](#frame-history)
- [Wiring](#wiring)
- [Software and firmware](#software-and-firmware)
- [Project status](#project-status)
- [Known issues](#known-issues)
- [Roadmap](#roadmap)
- [Credits](#credits)

## Why this project

Inspecting a foundation often means crawling through tight, dark spaces. A small FPV drone can get a camera in there instead. Crashes are likely in confined spaces, so the build favors a tough frame and parts that are cheap to replace.

## Releases

Each milestone of the build is published as a release.

| Release | What it covers |
|---|---|
| [v0.1.0 — Frame Print](https://github.com/ameyas2021-ops/Foundation_Inspector_-Drone-/releases/tag/v0.1.0) | The 3D-printed Manafly frame, its print files, settings, and photos |
| [v0.2.0 — Parts List](https://github.com/ameyas2021-ops/Foundation_Inspector_-Drone-/releases/tag/v0.2.0) | The full hardware list, with the carbon fiber frame replacing the printed one |

## Hardware

### Flight hardware

| Part | Model | Notes |
|---|---|---|
| Frame | Readytosky 150mm 3-inch carbon fiber | Replaced the 3D-printed frame from v0.1.0 |
| Flight controller | SpeedyBee F405 Mini (20x20) | ICM42688P gyro, barometer, onboard OSD, Bluetooth |
| ESC | SpeedyBee 35A 4-in-1, BLHeli_S | Capacitor soldered to the battery pads |
| FC to ESC link | JST cable | |
| Motors | 4x iFlight XING 1404, ~3800KV | KV to be confirmed |
| Props | 3-inch tri-blade | |
| Receiver | Radiomaster RP3 V2, ExpressLRS 2.4 GHz | Two IPEX antennas; replacement for a unit that died |

### Power and charging

| Part | Model | Notes |
|---|---|---|
| Flight battery | Ovonic 850mAh 4S 80C LiPo, XT30 | x2 |
| Charger | ToolkitRC M4AC (XT60 version) | |
| Radio battery | Radiomaster 18650 pack | Button-top 18650s didn't fit the Pocket |

### Radio

| Part | Model | Notes |
|---|---|---|
| Transmitter | Radiomaster Pocket | Internal ExpressLRS module |

### Unconfirmed

- ToolkitRC M4 Pocket or M6AC charger
- SMA antennas with IPEX-to-SMA pigtails
- Analog FPV camera and VTX

### Planned

- Thermal camera and Raspberry Pi Zero, for the inspection payload
- GPS module
- USB-to-UART adapter

## Frame history

### v0.1.0: 3D-printed Manafly frame (retired)

The first airframe was the [Manafly Beta 3" Generative FPV Drone Frame](https://makerworld.com/en/models/2000546-beta-manafly-3-generative-fpv-drone-frame#profileId-2154440), printed as-is on a Bambu Lab P2S in black PETG. PETG was chosen over PLA because it handles impacts better and flexes instead of shattering. The STL files, Bambu Studio project, and print settings are attached to the [v0.1.0 release](https://github.com/ameyas2021-ops/Foundation_Inspector_-Drone-/releases/tag/v0.1.0).

<p>
  <img src="https://github.com/ameyas2021-ops/Foundation_Inspector_-Drone-/releases/download/v0.1.0/Printed_Frame1" alt="Printed Manafly frame, view 1" width="45%">
  <img src="https://github.com/ameyas2021-ops/Foundation_Inspector_-Drone-/releases/download/v0.1.0/Printed_Frame2" alt="Printed Manafly frame, view 2" width="45%">
</p>

### Current: Readytosky 150mm carbon fiber

The printed frame was replaced with a Readytosky 150mm 3-inch carbon fiber frame in [v0.2.0](https://github.com/ameyas2021-ops/Foundation_Inspector_-Drone-/releases/tag/v0.2.0).

## Wiring

```
4S LiPo (XT30)
     │
 [capacitor]
     │
     ▼
SpeedyBee 35A 4-in-1 ESC ──► 4x XING 1404 motors
     │
  JST cable
     │
     ▼
SpeedyBee F405 Mini FC ──► RP3 V2 ELRS receiver (UART)
     │
     └──► FPV camera + VTX (TBD)
```

- The battery powers the ESC, and the capacitor on the ESC's battery pads absorbs voltage spikes.
- The flight controller gets power and sends motor signals through the JST cable.
- The receiver connects to a UART on the flight controller. *Which UART: TBD.*
- Camera and VTX wiring: *TBD.*

## Software and firmware

| Component | Firmware | Version |
|---|---|---|
| Flight controller | *TBD* | *TBD* |
| ESC | BLHeli_S | *TBD* |
| Receiver | ExpressLRS 2.4 GHz | *TBD* |
| Transmitter | *TBD* (Radiomaster Pocket) | *TBD* |

**Code:** *TBD. Where the code lives, what it does, and how to run it will go here once it's added to the repository.*

## Project status

| Area | Status |
|---|---|
| Frame | ✅ Carbon fiber frame in use |
| Flight electronics | ✅ Parts in hand |
| Radio link | 🟡 Receiver replaced after the first one died |
| Video (camera + VTX) | ❓ Not confirmed |
| Firmware and code | 🔴 Failing |
| Inspection payload | ⏳ Planned |
| First stable flight | ⏳ Not yet |

## Known issues

- **The code keeps failing.** *Details TBD.*
- **The first RP3 receiver died.** It was replaced. *Cause unknown.*
- **Motor KV isn't confirmed.** The motors are believed to be about 3800KV.

## Roadmap

- [ ] Document the firmware setup
- [ ] Get the code working and add it to this repository
- [ ] Confirm and install the FPV camera and VTX
- [ ] First stable hover
- [ ] First crawl-space test flight
- [ ] Add the thermal camera and Raspberry Pi Zero
- [ ] Add GPS

## Credits

- Frame design: [Manafly Beta 3" Generative FPV Drone Frame](https://makerworld.com/en/models/2000546-beta-manafly-3-generative-fpv-drone-frame#profileId-2154440) on MakerWorld
- Built by [@ameyas2021-ops](https://github.com/ameyas2021-ops)
