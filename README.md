# Initial commands (broadcast with option A):

cd catkin_ws
source devel/setup.bash
export TURTLEBOT3_MODEL=burger

## Opening Gazebo:

roslaunch turtlebot3_gazebo turtlebot3_world.launch

## Launching RViz navigation:

roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:=$HOME/map.yaml

## Refining map:

1. use the 2D Pose Estimate tool (green arrow)
2. launch teleop: roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
3. move the turtlebot a little bit

## Ros topics

### Listing ros topics

rostopic list

### show one topic

rostopic echo /"topic name"
example: rostopic echo /move_base/status

### info on one topic

rostopic info /"topic name"

## Launching Waypoints script
rosrun turtlebot3_waypoints turtlebot3_waypoints.py

## ROS bags

### Record rosbag

rosbag record /"package_names" -O "bag_path"
Example:
rosbag record /imu /move_base/goal -O ./ROS_Simulation_Framework_II

### Open and inspect rosbag

rqt_bag "bag_path"

### Replay the bags

rosbag play "rosbag_path"
