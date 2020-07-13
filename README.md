# installation-instructions

# Install ROS2 foxy distro

# Install Gazebo 11 
http://gazebosim.org/tutorials?tut=ros2_installing&cat=connect_ros 

# Useful ROS2 command
---
## For python 
1. Create new package using (will contain empty dummy node) `ros2 pkg create --build-type ament_python --node-name my_node my_package`
2. Create new custom interfaces using `ros2 pkg create --build-type ament_cmake my_interfaces`
## For general
1. Install ros dependencies `rosdep install -i --from-path src --rosdistro foxy -y --reinstall`
2. Publish message `ros2 topic pub --once /topic/message std_msgs/msg/String '{msg: 'string'}'`
3. Call service `ros2 service call /topic/service /custom_interfaces/srv/my_srv '{data: data here, more_data: more data here, ...}'`
## Gazebo
1. kill all gazebo processes `killall -9 gzserver`
2. Convert URDF -> SDF `gz sdf -p urdf_file.urdf > sdf_converted_file.sdf`
3. Run gazebo world `gazebo --verbose /opt/ros/foxy/share/gazebo_plugins/worlds/gazebo_ros_diff_drive_demo.world`
