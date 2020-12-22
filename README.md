# Installation Instructions

## Requirements:
### 1. Follow instructions to install latest stable release of Ignition: 

`https://ignitionrobotics.org/docs/dome/install_ubuntu`

add the following line to you bashrc. Run,

`sudo gedit ~/.bashrc`

add the follow,

`export IGN_GAZEBO_PHYSICS_ENGINE_PATH=/lib/x86_64-linux-gnu/ign-physics-2/engine-plugins`

### 2. Follow instructions to install latest stable release of Foxy ROS2 from binaries: 

i. First install everything labeled under "Install Developent tools and ROS Tools": 

`https://index.ros.org/doc/ros2/Installation/Foxy/Linux-Development-Setup/`

ii. Secondly follow installation guide for Foxy desktop version binaries here: 

`https://index.ros.org/doc/ros2/Installation/Foxy/Linux-Install-Debians/`

iii. Set new bashrc environment variables for ROS2. Run, 

`sudo gedit ~/.bashrc`

add the following line and save/exit,

`export ROS_OS_OVERRIDE='ubuntu:20.04:focal'`

Now run, `sudo gedit ~/.bash_aliases`

Add the following line and save/exit,

`alias source_ros='. /opt/ros/foxy/setup.bash'`

### 3. Install ignition-gym and dependencies,

i. install stable binaries for ignition-gym from robotology: 

`https://robotology.github.io/gym-ignition/master/installation/stable.html`

ii. Install IdynTree dependencies from: https://github.com/robotology/idyntree

`sudo apt-get install libeigen3-dev libxml2-dev coinor-libipopt-dev qtbase5-dev qtdeclarative5-dev qtmultimedia5-dev qml-module-qtquick2 qml-module-qtquick-window2 qml-module-qtmultimedia qml-module-qtquick-dialogs qml-module-qtquick-controls qml-module-qt-labs-folderlistmodel qml-module-qt-labs-settings`



