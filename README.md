# iqr_ptz_robot
jackal + imu + ptz + gps + hokuyo

## DEPEND
- [JACKAL ROS DRIVER](https://github.com/jackal)
- [IMU ROS DRIVER](https://github.com/I-Quotient-Robotics/jy901_driver)

## How to use
- compile & environment setup
  ```bash
  cd ~/catkin_ws
  catkin build
  source ~/catkin_ws/devel/setup.bash
  ```
- start jackal and sensor 's ros driver
  ```bash
  roslaunch iqr_ptz_bringup bringup.launch #You can modify this file to activate different sensors.
  ```
  then, you can view all of the topic
  ```bash
  rostopic list
  ```
- visualization
  ```bash
  roslaunch iqr_ptz_description view_robot.launch
  ```
- mapping 
  ```bash
  roslaunch iqr_ptz_navigation mapping.launch viz:=true
  ```
  
- save map
  ```bash
  roscd iqr_ptz_navigation/maps
  rosrun map_serve map_save -f [map_name]
  ```
- navigation
  ```bash
  roslaunch iqr_ptz_navigation navigation.launch viz:=true map_name:=[map_name]
  ```
