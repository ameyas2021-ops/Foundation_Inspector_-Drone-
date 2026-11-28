# Foundation Inspector Drone

A small 3-inch quadcopter built to go where people don't want to: the tight, dark spaces under a building's foundation.

> **Status:** In progress. The drone is built, configured and arms, but it does not hover stably yet.

## Why I'm building this

I watched construction workers fixing my home's foundation, and saw that some of them didn't want to go underneath, whether from fear of getting hurt or from claustrophobia. So I'm developing a drone that can go under there for them. The goal is a tool that makes their job safer and easier.

## Goals

- Fly a small, tough drone into crawl spaces and the confined areas around a foundation, so workers don't have to.
- Carry a thermal camera and a Raspberry Pi Zero to inspect what's down there.
- Eventually map out underground spaces, with GPS to tie findings to a location.
- Keep parts cheap and easy to replace, since crashes in tight spaces are likely.

## Hardware

- Frame: Readytosky 150mm 3-inch carbon fiber (replaced a 3D-printed frame)
- Flight controller and ESC: SpeedyBee F405 Mini stack, 35A BLHeli_S 4-in-1
- Motors: 4x iFlight XING 1404, ~3800KV, with 3-inch tri-blade props
- Receiver and radio: Radiomaster RP3 V2 (ExpressLRS) and Radiomaster Pocket
- Battery: Ovonic 850mAh 4S, XT30
- Firmware: Betaflight 4.5.5

The full list is in the [v0.2.0 release](https://github.com/ameyas2021-ops/Foundation_Inspector_-Drone-/releases/tag/v0.2.0).

## What has happened so far

Each milestone is published as a [release](https://github.com/ameyas2021-ops/Foundation_Inspector_-Drone-/releases).

| Release | Summary |
|---|---|
| v0.1.0 — Frame Print | Printed the Manafly 3-inch frame in PETG. |
| v0.2.0 — Parts List | Chose the flight electronics, power system and radio, and moved to a carbon fiber frame. |
| v0.3.0 — Power-Up and Bench Build | Soldered the stack and motors and powered up for the first time. Fixed a charge-only USB cable and a loose FC to ESC cable. |
| v0.4.0 — Radio, Receiver and Arming | Wired and bound the ELRS receiver. The first receiver died and was replaced. Cleared the arming flags, and the drone armed. |
| v0.5.0 — Firmware and Configuration | Lowered rates and PIDs, raised the throttle limit, updated to Betaflight 4.5.5 and applied a tune preset. |
| v0.6.0 — Flight Testing and Altitude Runaway | First flights. The drone climbed into a tree and broke the printed frame, so the build moved to carbon fiber. A motor wire was repaired and the motor later replaced. |
| v0.7.0 — Retest and Motor Solder Joint Failure | Retested with the new settings. A motor solder joint broke, and ways to prevent it are being evaluated. |

## Open issues

- **Altitude runaway:** after throttling up and back down, the drone keeps climbing. The leading cause is a high motor idle value (dshot_idle_value lowered from 550 to 400), and it still needs an outdoor test with props on.
- **Motor scraping sound:** all four motors started making a slight scraping sound after the rebuild. Cause not found yet.
- **Motor wiring:** two wire failures so far, so the motor wires need strain relief.

## Next steps

1. Fix the motor solder joint and add strain relief to the motor wires.
2. Test the new idle value outdoors, with props on, in Angle mode.
3. Get a stable hover.
4. Add the thermal camera, Raspberry Pi Zero and GPS.
5. Work toward mapping underground spaces.

## Credits

- Frame design (v0.1.0): [Manafly Beta 3" Generative FPV Drone Frame](https://makerworld.com/en/models/2000546-beta-manafly-3-generative-fpv-drone-frame#profileId-2154440) on MakerWorld
- Built by [@ameyas2021-ops](https://github.com/ameyas2021-ops)
