# sbg_ins_with_ntrip

#### Packages
Ntrip client: https://github.com/LORD-MicroStrain/ntrip_client
SBG systems ROS2 driver: https://github.com/SBG-Systems/sbg_ros2_driver

#### Build
```bash
colcon build
```
#### Run
```bash
# first terminal to run the node that connects to the Ntrip server and publishes RTCM corrections
source install/setup.bash
ros2 launch ntrip_client ntrip_client_launch.py host:=caster.centipede.fr mountpoint:=STJEA username:=centipede password:=centipede
# second terminal to run the sbg systems node that listens to the RTCM corrections
source install/setup.bash
ros2 launch sbg_driver sbg_device_launch.py 
```

#### Parameters
The position of the primary and secondary antennas relative to the INS needs to be specified in the /sbg_ros2_driver/config/sbg_device_uart_default.yaml file
