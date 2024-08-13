# Launch-TurtleBot-navigation
Through that link, you'll find directions and commands that are very helpful: https://emanual.robotis.com/docs/en/platform/turtlebot3/quick-start/

## Begin with the first four commands:

Open the terminal using Ctrl+Alt+T, then enter the following commands one by one.
```
$ sudo apt update
$ sudo apt upgrade
$ wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_noetic.sh
$ chmod 755 ./install_ros_noetic.sh 
$ bash ./install_ros_noetic.s
```
eache one of this commend in single line " notic that the third one is sooo long commend .


## second Install Dependent ROS Packages

```
$ sudo apt-get install ros-noetic-joy ros-noetic-teleop-twist-joy \
  ros-noetic-teleop-twist-keyboard ros-noetic-laser-proc \
  ros-noetic-rgbd-launch ros-noetic-rosserial-arduino \
  ros-noetic-rosserial-python ros-noetic-rosserial-client \
  ros-noetic-rosserial-msgs ros-noetic-amcl ros-noetic-map-server \
  ros-noetic-move-base ros-noetic-urdf ros-noetic-xacro \
  ros-noetic-compressed-image-transport ros-noetic-rqt* ros-noetic-rviz \
  ros-noetic-gmapping ros-noetic-navigation ros-noetic-interactive-markers
```
this commend is also long and you should write it in one line.
## Install TurtleBot3 Packages

Install TurtleBot3 via Debian Packages.
```
$ sudo apt-get install ros-kinetic-dynamixel-sdk
$ sudo apt-get install ros-kinetic-turtlebot3-msgs
$ sudo apt-get install ros-kinetic-turtlebot3
```

## Install Simulation Package

he TurtleBot3 Simulation Package requires turtlebot3 and turtlebot3_msgs packages as prerequisite. Without these prerequisite packages, the Simulation cannot be launched.
```
$ cd ~/catkin_ws/src/
$ git clone -b noetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
$ cd ~/catkin_ws && catkin_make
```
## Launch Simulation World

Three simulation environments are prepared for TurtleBot3.

1.Empty World

2.TurtleBot3 World

3.TurtleBot3 House

### i have choose the second "TurtleBot3 World" one so i will run this command

```
$ export TURTLEBOT3_MODEL=waffle
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
```
<img src="https://github.com/user-attachments/assets/99da42c4-a3ae-45a5-8de3-bac576b29d82">
<img src="https://github.com/user-attachments/assets/5727c111-d8e9-4c57-a28e-f79c861b942e">

## Opening SLAM
```
roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
```
<img src="https://github.com/user-attachments/assets/89c19619-dab2-47da-b325-78e8920955f7">
create a map and save it

```
rosrun map_server map_saver -f ~/map
```
then run this command:

```
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```
<img src="https://github.com/user-attachments/assets/da681ab4-7542-46e0-87f8-0594f76e620b">

# navigation
start the navigation and load the saved map, using this command:

```
roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:='/home/muh/map.yaml'

```
<img src="https://github.com/user-attachments/assets/f3c26786-ad9c-4d08-9534-0c459e6ed1c1">
now You can then move the robot !
<img src="https://github.com/user-attachments/assets/838d0fae-5313-4f18-81ef-b4a147277b04">


