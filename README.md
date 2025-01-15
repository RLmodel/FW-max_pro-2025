# FW-max_pro-2025
![c4c9035fdcd25](https://github.com/user-attachments/assets/76a4f99c-fdc7-4e19-baa7-63afe3f70a4f)


added cmd_vel

<br/>

## tested environment

- ubuntu 22.04
- ROS2 Humble

<br/>

## dependencies

<br/>

```bash
sudo apt install ros-humble-nav-msgs
sudo apt install ros-humble-rqt-robot-steering
```

<br/>

## clone && build && launch

<br/>

- source ROS2 environment

```bash
source /opt/ros/humble/setup.bash
```

<br/>

- move to {workspace}/{source_folder}

```bash
cd ~/ros2_ws/src
```

<br/>

- clone packages

```bash
git clone https://github.com/RLmodel/FW-max_pro-2025.git
```

<br/>

- move to workspace

```bash
cd ~/ros2_ws
```

<br/>

- colcon build && source install folder

```bash
colcon build --packages-select --symlink-install yhs_can_interfaces
colcon build --packages-select --symlink-install yhs_can_control
source install/setup.bash
```

<br/>

- ip link up && set bitrate

```bash
sudo ip link set can0 up type can bitrate 500000
```

<br/>

- launch

```bash
ros2 launch yhs_can_control yhs_can_control.launch.py
```

<br/>

- cmd_vel control test

```bash
rqt_robot_steering
```

<br/>

## Debug

- check can connection

```bash
ifconfig -a | grep can
```
<br/>

- check can message

```bash
candump can0
```

<br/>


