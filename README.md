### RL Deployment with Real Turtlebot2 
## PowerSheel Commands 
PS C:\Windows\system32> usbipd list

PS C:\Windows\system32> usbipd bind --busid 1-2

PS C:\Windows\system32> usbipd attach --wsl --busid 1-2

## Ros1 Commands
roscore

roslaunch turtlebot_bringup minimal.launch

#or

roslaunch kobuki_node minimal.launch

rosrun urg_node urg_node _port:=/dev/lidar

roslaunch turtlebot_teleop keyboard_teleop.launch

# check devices 
dmesg | grep tty

ls /dev/ttyUSB*
# new tem
decker exec -it ros1_gui_container bash 

source /opt/ros/noetic/setup.bash && cd /home/ros/catkin_ws/ && source devel/setup.bash


## Ros2 Commands 
# Bridge 
  source /opt/ros/humble/setup.bash
  
  source ~/ros_bridge_ws/ros-humble-ros1-bridge/install/local_setup.bash
  
  ros2 run ros1_bridge dynamic_bridge
  
  # or try (See Note2):
  ros2 run ros1_bridge dynamic_bridge --bridge-all-topics
  
# Ros2 
ros2 launch turtlebot3_gazebo turtlebot3_drl_stage9.launch.py

ros2 run turtlebot3_drl real_environment

ros2 run turtlebot3_drl real_agent ddpg ddpg_1_stage_5 1500

./spawn_goal.h 1 1





