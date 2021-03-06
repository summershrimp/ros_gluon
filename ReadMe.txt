README.md
Gluon ROS packages
This is the Gluon ROS package designed by Lison Li. These packages support Moveit!, RViz and LAN communication with Gluon.

1. Download and install
Download ros packages for gluon

then manually copy package folders gluon gluon_control gluon_moveit_config and cm_moveit into a catkin_ws/src.

$ catkin_make

2. Set up enviroment
Source all setup.bash files to set up your enviroment.

# System configure ROS environment variables automatically every time you open a ternimal
echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
source ~/.bashrc

3. Simulation and Control
Before ROS control, make sure that your manipulator is in the "homing" position. Connect your gluon to your Lan network(192.168.1.xxx)

If you are using a virtual machine running Linux, turn off graphics hardware acceleration, otherwise gazebo may not start properly.

3.1 Rviz Control Mode:
Show the urdf model of gluon in rviz, then drag the scroll bar of each axis in rviz to control the movement of the manipulator.

roslaunch gluon display.launch

3.2 Moveit+Rviz Control Mode:
Display the gluon model in rviz, then use the rviz interface of moveit to drag the manipulator for motion planning, click the "execute" button in moveit, and control the gluon to move with the virtual manipulator.

roslaunch gluon_moveit_config cm_demo.launch

3.3 Moveit Tutorials
Cartesian Paths example and control gluon

roslaunch moveit_tutorials move_group_interface_tutorial.launch