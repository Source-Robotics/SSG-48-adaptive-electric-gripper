<p align="center">
  <img src="Photos/SSG48_banner.png" alt="SSG-48 adaptive electric gripper" width="100%">
</p>

<h1 align="center">SSG-48</h1>

<p align="center">
  <b>Open-source 3D-printed adaptive electric gripper.</b><br>
  Every move sets where the jaws go, how fast, and how hard they press.
</p>

<p align="center">
  <a href="https://source-robotics.com/products/compliant-gripper"><b>Buy</b></a>&nbsp;&nbsp;·&nbsp;&nbsp;
  <a href="https://docs.source-robotics.com/SSG48-gripper-docs/"><b>Documentation</b></a>&nbsp;&nbsp;·&nbsp;&nbsp;
  <a href="https://docs.source-robotics.com/SSG48-gripper-docs/latest/build/"><b>Build guide</b></a>&nbsp;&nbsp;·&nbsp;&nbsp;
  <a href="https://github.com/Source-Robotics/SSG-48-adaptive-electric-gripper/releases/latest"><b>Download</b></a>&nbsp;&nbsp;·&nbsp;&nbsp;
  <a href="https://discord.com/invite/prjUvjmGpZ"><b>Discord</b></a>
</p>

<p align="center">
  <a href="https://github.com/Source-Robotics/SSG-48-adaptive-electric-gripper/releases/latest"><img src="https://img.shields.io/github/v/release/Source-Robotics/SSG-48-adaptive-electric-gripper?style=flat-square&color=143952&label=release" alt="Release"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-CERN--OHL--S--2.0-143952?style=flat-square" alt="License licence"></a>
  <a href="https://discord.com/invite/prjUvjmGpZ"><img src="https://img.shields.io/discord/1072498136284667955?style=flat-square&logo=discord&logoColor=white&label=discord&color=292B37" alt="Discord"></a>
</p>

<div align="center">

| **48 mm** | **8 to 80 N** | **180 mm/s** | **440 g** | **24 V, CAN** |
|:-:|:-:|:-:|:-:|:-:|
| stroke | grip force, set by the current | per jaw, at most | mass | on one M8 cable |

</div>

## Project overview

<table>
  <tr>
    <td width="55%" valign="middle">
      The SSG-48 adaptive electric gripper is a gripper based on
      <a href="https://source-robotics.com/products/spectral-micro-bldc-controller">Spectral Micro BLDC drivers</a>.
      It is a gripper capable of controlling its gripping force, making it perfect for assembly tasks and
      human-robot collaboration. The force can be adjusted from 8 N to 80 N, allowing you to grasp a wide range of
      items, from delicate and soft to rigid and sturdy.
      <br><br>
      The mechanical files and the firmware are open source, allowing you to add a custom gripping tool and attach
      it to any robotic arm or robot. The gripper software is also open source. The gripper has a stroke of 48 mm
      and a mass of 440 g.
      <br><br>
      <a href="https://www.youtube.com/shorts/DQgi8Ua-VAU"><b>&#9654;&#xFE0E;&nbsp; Watch the SSG-48 in action</b></a>
    </td>
    <td width="45%" valign="middle">
      <a href="https://www.youtube.com/shorts/DQgi8Ua-VAU"><img src=".github/readme/video.jpg" alt="Watch the SSG-48 in action on YouTube" width="100%"></a>
    </td>
  </tr>
</table>

## Start here

| I want to | Go to |
|---|---|
| **Buy an assembled gripper** | [source-robotics.com](https://source-robotics.com/products/compliant-gripper) |
| **Build my own** | [BOM](BOM/) · [print files](Gripper%20STL%20parts/) · [assembly manual](Assembly%20manual/) · [assembly video](https://www.youtube.com/watch?v=127zXHKuqIg) · [cables](Assembly%20manual/Building_cables.md) · [build guide](https://docs.source-robotics.com/SSG48-gripper-docs/latest/build/) |
| **Set it up and make it move** | [Quick start](https://docs.source-robotics.com/SSG48-gripper-docs/latest/quick-start/) · [Motor GUI](https://motorgui.com/), in the browser ([guide](https://docs.source-robotics.com/SSG48-gripper-docs/latest/05-setup/motor-gui/)) |
| **Program it** | [Python API](https://github.com/Source-Robotics/Spectral-BLDC-Python) ([first program](https://docs.source-robotics.com/SSG48-gripper-docs/latest/06-operation/python/#the-first-program)) · [ROS 2 package](https://github.com/Lass6230/ssg48_adaptive_electric_gripper_ros2) · [MSG gripper's ROS 2 package](https://github.com/BiomechatronicsLab/source_robotics_msg_gripper_ros2), which drives the SSG-48 too · [CAN and UART commands](https://docs.source-robotics.com/SSG48-gripper-docs/latest/reference/) |
| **Simulate it** | [URDF and MuJoCo models](ssg48_description/) |
| **Put it on a robot** | [PAROL6 and PAR6](https://docs.source-robotics.com/SSG48-gripper-docs/latest/06-operation/robots/) · [UR5 adapter plate](STEPS/UR5%20adapter%20plate/) · [PAROL6 gripper cable](https://source-robotics.com/products/gripper-cable) |

## In this repository

| Folder | What is in it |
|---|---|
| [`Gripper STL parts`](Gripper%20STL%20parts/) | every printed part of both hardware versions (`V1`, `V2`), and the coupler connectors for PAROL6, PAR6 and your own robot |
| [`gripper jaws`](gripper%20jaws/) | the fin-ray fingers and their jaw plate, STL and STEP |
| [`STEPS`](STEPS/) | the STEP files: the body parts, the whole gripper, the jaw plate template, the pinch jaws, the generic coupler connector and the UR5 adapter plate |
| [`BOM`](BOM/) | the bill of materials, with a shop link and a reference image for every part but the screws |
| [`Assembly manual`](Assembly%20manual/) | the assembly manual (PDF), the guide to building the cables and a motor datasheet |
| [`ssg48_description`](ssg48_description/) | the guide to the URDF and MuJoCo models, from [robot_descriptions](https://github.com/Source-Robotics/robot_descriptions) |

The [latest release](https://github.com/Source-Robotics/SSG-48-adaptive-electric-gripper/releases/latest) has the print
files, the STEP files, the jaws, the assembly manual and the BOM as ready downloads.

## Community

Ask in [Discussions](https://github.com/orgs/Source-Robotics/discussions), chat on
[Discord](https://discord.com/invite/prjUvjmGpZ), report a bug in
[Issues](https://github.com/Source-Robotics/SSG-48-adaptive-electric-gripper/issues), and follow Source Robotics:

[![Discord](https://img.shields.io/discord/1072498136284667955?style=flat-square&logo=discord&logoColor=white&label=discord&color=143952)](https://discord.com/invite/prjUvjmGpZ)
[![Discussions](https://img.shields.io/badge/discussions-ask_a_question-143952?style=flat-square&logo=github&logoColor=white)](https://github.com/orgs/Source-Robotics/discussions)
[![YouTube](https://img.shields.io/badge/youtube-%40source--robotics-143952?style=flat-square&logo=youtube&logoColor=white)](https://www.youtube.com/@source-robotics)
[![Instagram](https://img.shields.io/badge/instagram-%40source__robotics-143952?style=flat-square&logo=instagram&logoColor=white)](https://www.instagram.com/source_robotics/)
[![X](https://img.shields.io/badge/x-%40SourceRobotics-143952?style=flat-square&logo=x&logoColor=white)](https://x.com/SourceRobotics)
[![LinkedIn](https://img.shields.io/badge/linkedin-Source_Robotics-143952?style=flat-square&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik0yMC40NDcgMjAuNDUyaC0zLjU1NHYtNS41NjljMC0xLjMyOC0uMDI3LTMuMDM3LTEuODUyLTMuMDM3LTEuODUzIDAtMi4xMzYgMS40NDUtMi4xMzYgMi45Mzl2NS42NjdIOS4zNTFWOWgzLjQxNHYxLjU2MWguMDQ2Yy40NzctLjkgMS42MzctMS44NSAzLjM3LTEuODUgMy42MDEgMCA0LjI2NyAyLjM3IDQuMjY3IDUuNDU1djYuMjg2ek01LjMzNyA3LjQzM2MtMS4xNDQgMC0yLjA2My0uOTI2LTIuMDYzLTIuMDY1IDAtMS4xMzguOTItMi4wNjMgMi4wNjMtMi4wNjMgMS4xNCAwIDIuMDY0LjkyNSAyLjA2NCAyLjA2MyAwIDEuMTM5LS45MjUgMi4wNjUtMi4wNjQgMi4wNjV6bTEuNzgyIDEzLjAxOUgzLjU1NVY5aDMuNTY0djExLjQ1MnpNMjIuMjI1IDBIMS43NzFDLjc5MiAwIDAgLjc3NCAwIDEuNzI5djIwLjU0MkMwIDIzLjIyNy43OTIgMjQgMS43NzEgMjRoMjAuNDUxQzIzLjIgMjQgMjQgMjMuMjI3IDI0IDIyLjI3MVYxLjcyOUMyNCAuNzc0IDIzLjIgMCAyMi4yMjIgMGguMDAzeiIvPjwvc3ZnPg%3D%3D)](https://www.linkedin.com/company/source-robotics/)
[![Blog](https://img.shields.io/badge/blog-source--robotics.com-143952?style=flat-square&logo=rss&logoColor=white)](https://source-robotics.com/blogs/blog)

## Safety, liability and disclaimer

This project includes experimental software, hardware designs, and assembly documentation that are still under development and may contain bugs, errors, or incomplete features. By using, building, or modifying this project, you acknowledge that:

* You use this project entirely at your own risk
* You are solely responsible for safe assembly, testing, and operation
* No guarantee is made regarding correctness, safety, or reliability
* The authors are not responsible for any damage, injury, or loss resulting from the use or misuse of this project
* Hardware performance and safety depend on user assembly, component quality, calibration, and handling, which cannot be guaranteed
* This project is provided “as is.” If you choose to build a device yourself using these files, designs, or instructions, you do so without any warranties or guarantees, including regarding safety, reliability, or suitability for any particular purpose.

> [!WARNING]
> THIS PROJECT INVOLVES LETHAL VOLTAGES AND OTHER SERIOUS HAZARDS THAT CAN CAUSE SEVERE INJURY. YOU MUST READ THE FULL [SAFETY WARNING AND DISCLAIMER DOCUMENT](SAFETY_WARNING_AND_DISCLAIMER.md)  BEFORE USING ANY PROJECT FILES. BY PROCEEDING, YOU ACKNOWLEDGE AND ACCEPT ALL RISKS AND AGREE TO USE THIS PROJECT ENTIRELY AT YOUR OWN RESPONSIBILITY.

## Licensing

Project is under the [CERN Open Hardware Licence Version 2 - Strongly Reciprocal](LICENSE) (CERN-OHL-S-2.0). Until 4 November 2026 it was under Apache-2.0.

## Versions

Which release and hardware version you have, and what works with it: [VERSIONS.md](VERSIONS.md).
