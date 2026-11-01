<img src="Photos/SSG48_banner.png" alt="drawing" width="5000"/>

<div align="center">

# SSG48 adaptive electric gripper
[![License: apache](https://img.shields.io/badge/Licsence-apache-yellow.svg)](https://opensource.org/license/apache-1-1/)  ![Issues](https://img.shields.io/github/issues/PCrnjak/SSG-48-adaptive-electric-gripper) ![release](https://img.shields.io/github/v/release/PCrnjak/SSG-48-adaptive-electric-gripper) [![ROS2](https://img.shields.io/badge/ROS-2-blueviolet?logo=ros)](https://github.com/Lass6230/ssg48_adaptive_electric_gripper_ros2)  [![Python](https://img.shields.io/badge/Python-API-yellow?logo=python&logoColor=black)](https://github.com/PCrnjak/Spectral-BLDC-Python/tree/main)  [![Docs](https://img.shields.io/badge/DOCS-GitHub%20Pages-brightgreen)](https://source-robotics.github.io/SSG48-gripper-docs/page1_about_the_gripper/)

## [▶️YouTube🔴 Video of Gripper in Action!](https://www.youtube.com/shorts/DQgi8Ua-VAU)

</div>

## URDF and MuJoCo models

**[Open the SSG48 model guide and downloads](description/)**

The `description/` folder opens instructions specifically for SSG48:
standalone gripper downloads, both jaw options, mounting and open/close controls.
The maintained source is nested at `description/source/`, pinned to **v2.13.0**.
For an existing clone, run `git submodule sync --recursive` followed by
`git submodule update --init --recursive`; for a new clone use
`git clone --recurse-submodules`. Model ZIP downloads work without Git.



## 📖 Project Overview

**SSG-48 adaptive electric gripper** is a gripper based on [Spectral micro BLDC drivers](https://source-robotics.com/products/spectral-micro-bldc-controller). It is a gripper capable of controlling its gripping force, making it perfect for assembly tasks and human-robot collaboration. Force can be adjusted from 5 N to 80 N allowing you to grasp a wide range of items; from delicate and soft to rigid and sturdy.

Mechanical files and firmware are open source allowing you to add a custom griping tool and attach it to any robotic arm or robot. Gripper software is also open-source. Gripper has a stroke of 48 mm and a mass of 400g.

## ⚒️How to build / Where to buy?

You can buy SSG48 adaptive electric gripper on our website: https://source-robotics.com/products/compliant-gripper

If you want to Source all the parts yourself and build your own follow these steps:

* Source all the parts from the [BOM](https://github.com/PCrnjak/SSG-48-adaptive-electric-gripper/tree/main/BOM)
* Follow [Assembly instructions](https://github.com/PCrnjak/SSG-48-adaptive-electric-gripper/tree/main/Assembly%20manual) or [Video instructions](https://www.youtube.com/watch?v=127zXHKuqIg) to assemble your gripper
* Follow [DOCS](https://source-robotics.github.io/SSG48-gripper-docs/page1_about_the_gripper/) to get your gripper up and running.

## 📚Documentation:

- [Product website](https://source-robotics.com/products/compliant-gripper)
- [GUI software](https://github.com/PCrnjak/SSG-gripper-GUI) 
- [Building instructions](https://github.com/PCrnjak/SSG-48-adaptive-electric-gripper/tree/main/Assembly%20manual)
- [BOM](https://github.com/PCrnjak/SSG-48-adaptive-electric-gripper/tree/main/BOM)
- [DOCS](https://source-robotics.github.io/SSG48-gripper-docs/page1_about_the_gripper/)
- [Python API](https://github.com/PCrnjak/Spectral-BLDC-Python/tree/main)
- [ROS2 package for SSG48 gripper](https://github.com/Lass6230/ssg48_adaptive_electric_gripper_ros2) /// [ROS2 package for MSG gripper](https://github.com/BiomechatronicsLab/source_robotics_msg_gripper_ros2)
- [Current URDF & MuJoCo models](description/)


## 💻Quick start code example

```python
import Spectral_BLDC as Spectral
import time

Communication1 = Spectral.CanCommunication(bustype='slcan', channel='COM20', bitrate=1000000)
Motor1 = Spectral.SpectralCAN(node_id=0, communication=Communication1)

Motor1.Send_Clear_Error()
Motor1.Send_gripper_calibrate()
time.sleep(4)

temp_var = 0
while True:
   if temp_var == 0:
      Motor1.Send_gripper_data_pack(50,100,700,1,1,0,0) 
      temp_var = 1
   elif temp_var == 1:
      Motor1.Send_gripper_data_pack(240,100,700,1,1,0,0) 
      temp_var = 0

   message, UnpackedMessageID = Communication1.receive_can_messages(timeout=0.2) 

   if message is not None:
      print(f"Message is: {message}")
      print(f"Node ID is : {UnpackedMessageID.node_id}")
      print(f"Message ID is: {UnpackedMessageID.command_id}")
      print(f"Error bit is: {UnpackedMessageID.error_bit}")
      print(f"Timestamp is: {message.timestamp}")

   time.sleep(3)
```


## 🌐 More about the SSG48 Adaptive Electric Gripper

| YouTube | Hackaday | Instagram | Twitter |
|--------|----------|-----------|---------|
| [![YouTube](https://img.shields.io/badge/YouTube-FF0000?logo=youtube&logoColor=white)](https://www.youtube.com/channel/UCp3sDRwVkbm7b2M-2qwf5aQ) | [![Hackaday](https://img.shields.io/badge/Hackaday-000000?logo=hackaday&logoColor=white)](https://hackaday.io/project/191860-parol6-desktop-robotic-arm) | [![Instagram](https://img.shields.io/badge/Instagram-E4405F?logo=instagram&logoColor=white)](https://www.instagram.com/source_robotics/) | [![Twitter](https://img.shields.io/badge/Twitter-1DA1F2?logo=twitter&logoColor=white)](https://twitter.com/SourceRobotics) |

| Discord | Forum | Blog |
|--------|-------|------|
| [![Discord](https://img.shields.io/badge/Discord-5865F2?logo=discord&logoColor=white)](https://discord.com/invite/prjUvjmGpZ) | [![Forum](https://img.shields.io/badge/Forum-0A0A0A)](https://discourse.source-robotics.com/) | [![Blog](https://img.shields.io/badge/Blog-Source%20Robotics-blue)](https://source-robotics.com/blogs/blog) |




## ⚠️ Safety, Liability & Disclaimer
This project includes experimental software, hardware designs, and assembly documentation that are still under development and may contain bugs, errors, or incomplete features. By using, building, or modifying this project, you acknowledge that:

* You use this project entirely at your own risk
* You are solely responsible for safe assembly, testing, and operation
* No guarantee is made regarding correctness, safety, or reliability
* The authors are not responsible for any damage, injury, or loss resulting from the use or misuse of this project
* Hardware performance and safety depend on user assembly, component quality, calibration, and handling, which cannot be guaranteed
* This project is provided “as is.” If you choose to build a device yourself using these files, designs, or instructions, you do so without any warranties or guarantees, including regarding safety, reliability, or suitability for any particular purpose.

THIS PROJECT INVOLVES LETHAL VOLTAGES AND OTHER SERIOUS HAZARDS THAT CAN CAUSE SEVERE INJURY. YOU MUST READ THE FULL [SAFETY WARNING AND DISCLAIMER DOCUMENT](SAFETY_WARNING_AND_DISCLAIMER.md)  BEFORE USING ANY PROJECT FILES. BY PROCEEDING, YOU ACKNOWLEDGE AND ACCEPT ALL RISKS AND AGREE TO USE THIS PROJECT ENTIRELY AT YOUR OWN RESPONSIBILITY.


## 💸Support the project

The majority of this project is open source and freely available to everyone. Your assistance, whether through donations or advice, is highly valued. Thank you!

 [![General badge](https://img.shields.io/badge/PayPal-00457C?style=for-the-badge&logo=paypal&logoColor=white)](https://paypal.me/PCrnjak?locale.x=en_US)
[![General badge](https://img.shields.io/badge/Patreon-F96854?style=for-the-badge&logo=patreon&logoColor=white)](https://www.patreon.com/PCrnjak)

## 🛡️ Licensing
Project is under Apache 2.0 Licence
