# installation-instructions

Packages Install:
=======
Anaconda install:
----
1. `wget -P /tmp https://repo.anaconda.com/archive/Anaconda3-2020.07-Linux-x86_64.sh`
2. `bash /tmp/Anaconda3-2020.02-Linux-x86_64.sh`
3. `source ~/.bashrc`
4. `conda update --all`

**Anaconda uninstall**:
1. `rm -rf ~/anaconda3 ~/.condarc ~/.conda ~/.continuum`
2. Open the ~/.bashrc file and remove the Anaconda directory from the PATH environment variable:
```
# !! Contents within this block are managed by 'conda init' !!
__conda_setup="$('/home/linuxize/anaconda3/bin/conda' 'shell.bash' 'hook' 2> /dev/null)"
if [ $? -eq 0 ]; then
    eval "$__conda_setup"
else
    if [ -f "/home/linuxize/anaconda3/etc/profile.d/conda.sh" ]; then
        . "/home/linuxize/anaconda3/etc/profile.d/conda.sh"
    else
        export PATH="/home/linuxize/anaconda3/bin:$PATH"
    fi
fi
unset __conda_setup
```

Setup conda virtual enviroment with Cuda and pytorch
----
1. `conda create -n bb python numpy scipy` create a conda environment
2. `conda activate bb` to enter into environment
3. `conda install pytorch torchvision cudatoolkit=10.2 -c pytorch` install pytorch and cuda
4. Check if enviroment has GPU available - if output is true GPU is being used.
```
Python
import torch
torch.cuda.is_available()
```

**Uninstall environment**: 
`conda remove --name bb --all` verify it is removed with `conda env --list`

Install Gym
----
1. `conda activate bb`
2. `pip install gym`

ROS2-Foxy stuff
=====
Install Gazebo 11 
---
http://gazebosim.org/tutorials?tut=ros2_installing&cat=connect_ros 

Useful ROS2 command
---
**For python** 
1. Create new package using (will contain empty dummy node) `ros2 pkg create --build-type ament_python --node-name my_node my_package`
2. Create new custom interfaces using `ros2 pkg create --build-type ament_cmake my_interfaces`
**For general**
1. Install ros dependencies `rosdep install -i --from-path src --rosdistro foxy -y --reinstall`
2. Publish message `ros2 topic pub --once /topic/message std_msgs/msg/String '{msg: 'string'}'`
3. Call service `ros2 service call /topic/service /custom_interfaces/srv/my_srv '{data: data here, more_data: more data here, ...}'`
**Gazebo**
1. kill all gazebo processes `killall -9 gzserver`
2. Convert URDF -> SDF `gz sdf -p urdf_file.urdf > sdf_converted_file.sdf`
3. Run gazebo world `gazebo --verbose /opt/ros/foxy/share/gazebo_plugins/worlds/gazebo_ros_diff_drive_demo.world`
