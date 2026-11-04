# SSG-48 versions

Which SSG-48 you have, and which files, firmware and manual go with it.

## Releases

| Release | Date | What it is | Firmware | Files |
|---|---|---|---|---|
| **V2** | 2026-11-04 | the SSG-48 as sold today: hardware V2, the "large bearing" body, with the V1 parts too; more jaws, the cable guide, the URDF and MuJoCo models | Spectral 107 | [download](https://github.com/Source-Robotics/SSG-48-adaptive-electric-gripper/releases/tag/V2) |
| V1.1 | 2024-06-02 | the first official release, tested with PAROL6 | Spectral 101, 104 to 107 | [tag](https://github.com/Source-Robotics/SSG-48-adaptive-electric-gripper/releases/tag/V1.1) |

## Which version do I have?

| | What differs | How to tell |
|---|---|---|
| Hardware V2 or V1 | V2 has the "large bearing" body, lid, gear and magnet shaft: a larger bearing on the pinion for a stiffer, longer-lasting mechanism; the electronics, the motor, the rail, the jaw plates, the coupler connectors and the control are the same | a gripper from the shop is a V2; a self-built one is the version of its printed parts (folder `V1` or `V2` in [Gripper STL parts](Gripper%20STL%20parts/)) |
| Release V2 or V1.1 | V2 carries the parts of both hardware versions; V1.1 is the version tested with PAROL6 | either works with Spectral firmware 107 and the current manual |

## What works together

The driver firmware, the bootloader, the Python library, the ROS 2 drivers and the manual for each firmware release:
[Versions and compatibility](https://docs.source-robotics.com/SSG48-gripper-docs/latest/appendix/compatibility/) in the manual.
