# Hagen 

### From source

Install instructions for Ubuntu Bionic.

1. Install at least one simulator,
   [Gazebo](http://gazebosim.org/tutorials?cat=install) 

1. Install the appropriate ROS 2 version as instructed
   [here](https://index.ros.org/doc/ros2/Installation/Linux-Install-Debians/).

1. Clone Hagen

        mkdir -p ~/ws/src
        cd ~/ws/src
        git clone https://github.com/GPrathap/autonomous_mobile_robots.git

1. Install dependencies:

        cd ~/ws
        rosdep install --from-paths src --ignore-src -r -y

1. Build and install:

        cd ~/ws
        colcon build

## Run

### Gazebo-classic

If you had Gazebo installed when compiling Hagen's packages, Gazebo support
should be enabled.

1. Setup environment variables (the order is important):

        . /usr/share/gazebo/setup.sh
        . ~/ws/install/setup.bash

    > *Tip*: If the command `ros2 pkg list | grep hagen_gazebo` comes up empty
      after setting up the environment, Gazebo support wasn't correctly setup.

2. Launch the Diffdrive robot :

        ros2 launch hagen_gazebo hagen.launch.py

3. Launch the car_like robot :

        ros2 launch hagen_gazebo hagen_car.launch.py

Acknowledgement

    https://automaticaddison.com, https://github.com/winstxnhdw/AutoCarROS2