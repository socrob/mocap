optitrack mocap (motion capture system)
===

NOTE: This document does not explain details, it asumes that you are already familiar with mocap.

Instructions on how to record your dataset:

mocap calibration
===

Turn on switch, mocap PC, open motive and click calibrate

start wanding, set ground plane, put a marker somewhere in the testbed.


PC rosbag record
===

connect your PC to the same network as the mocap PC

mocap ip: 192.168.0.2
set a fixed ip for your PC, for example : 192.168.0.5

make sure you can ping mocap pc

        ping 192.168.0.2

if you can't ping make sure mocap firewall is off

Install vrpn software

        sudo apt-get install ros-kinetic-vrpn
        sudo apt-get install ros-kinetic-vrpn-client-ros

clone this repo in your catkin workspace, compile it and source it:

        cd $ROS_WORKSPACE
        git clone https://github.com/socrob/mocap.git
        catkin build
        source ~/.bashrc
        
launch vrpn client node:

        roslaunch mbot_mocap mocap.launch

open rviz, set fixed frame to map, add tf topic
