# Moving_Robot
Second Task of Smart Methods training 

Steps of tasaks:

Part 1

First I Install ROS 1 on Remote PC and used this codes

$ sudo apt update\
$ sudo apt upgrade\
$ wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_melodic.sh \
$ chmod 755 ./install_ros_melodic.sh \
$ bash ./install_ros_melodic.sh

Second I Install Dependent ROS 1 Packages by this code

$ sudo apt-get install ros-melodic-joy ros-melodic-teleop-twist-joy \\\
  ros-melodic-teleop-twist-keyboard ros-melodic-laser-proc \\\
  ros-melodic-rgbd-launch ros-melodic-depthimage-to-laserscan \\\
  ros-melodic-rosserial-arduino ros-melodic-rosserial-python \\\
  ros-melodic-rosserial-server ros-melodic-rosserial-client \\\
  ros-melodic-rosserial-msgs ros-melodic-amcl ros-melodic-map-server \\\
  ros-melodic-move-base ros-melodic-urdf ros-melodic-xacro \\\
  ros-melodic-compressed-image-transport ros-melodic-rqt* \\\
  ros-melodic-gmapping ros-melodic-navigation ros-melodic-interactive-markers
  
  Third I Install TurtleBot3 Packages by this codes 
  
$ sudo apt-get install ros-melodic-dynamixel-sdk\
$ sudo apt-get install ros-melodic-turtlebot3-msgs\
$ sudo apt-get install ros-melodic-turtlebot3

Part 2

First I Install Simulation Package by this codes

$ cd ~/catkin_ws/src/ \
$ git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git \
$ cd ~/catkin_ws && catkin_make\

Second I Launch Simulation World (TurtleBot3 World)

$ export TURTLEBOT3_MODEL=burger\
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch

![WhatsApp Image 2021-07-05 at 7 35 01 AM (2)](https://user-images.githubusercontent.com/86194970/124419596-7be5ea00-dd66-11eb-87c3-454c7934c7ad.jpeg)

Third I Run SLAM Node by codes

$ export TURTLEBOT3_MODEL=burger\
$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping

Fourth I Run Teleoperation Node 

$ export TURTLEBOT3_MODEL=burger\
$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

![WhatsApp Image 2021-07-05 at 7 35 01 AM](https://user-images.githubusercontent.com/86194970/124420149-a1bfbe80-dd67-11eb-9fad-12df9acf2fd0.jpeg)

Finally I Save the Map by this code and get this results

$ rosrun map_server map_saver -f ~/map

![WhatsApp Image 2021-07-05 at 7 35 38 AM](https://user-images.githubusercontent.com/86194970/124420263-e4819680-dd67-11eb-9790-4345741dd9f0.jpeg)

![WhatsApp Image 2021-07-05 at 7 35 01 AM (1)](https://user-images.githubusercontent.com/86194970/124420284-eba8a480-dd67-11eb-9aca-d77770d97355.jpeg)

