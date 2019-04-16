# GridBasedFastSLAM-gmapping

### Create a catkin_ws in /<YOUR WORKSPACE>
```sh
$ mkdir -p /<YOUR WORKSPACE>/catkin_ws/src
$ cd /<YOUR WORKSPACE>/catkin_ws/src
$ catkin_init_workspace
$ cd ..
$ catkin_make
```
### Clone turtlebot_gazebo and turtlebot_teleop in src
```sh
$ cd src/
$ git clone https://github.com/turtlebot/turtlebot_simulator
$ git clone https://github.com/turtlebot/turtlebot
```
### Install packages dependencies
```sh
$ cd ..
$ source devel/setup.bash
$ rosdep -i install turtlebot_gazebo
$ rosdep -i install turtlebot_teleop
```
### Build the packages
```sh
$ catkin_make
$ source devel/setup.bash
```
### Clone the gmapping package, install its system dependencies, and build your catkin workspace
```sh
$ cd /<YOUR WORKSPACE>/catkin_ws/src
$ git clone https://github.com/ros-perception/slam_gmapping
$ rosdep install gmapping
$ cd..
$ catkin_make
```
### Deploying a Turltebot in a World Environment, e.g., Willow Garage environment
```sh
$ roslaunch turtlebot_gazebo turtlebot_world.launch world_file:=worlds/willowgarage.world
```
### Open a new Terminal-Launch the keyboard teleop node
```sh
$ cd /<YOUR WORKSPACE>/catkin_ws
$ source devel/setup.bash
$ roslaunch turtlebot_teleop keyboard_teleop.launch
```
### Open another Terminal-Run the slam_gmapping node
```sh
$ cd /<YOUR WORKSPACE>/catkin_ws
$ source devel/setup.bash
$ rosrun gmapping slam_gmapping
```
### Open another Terminal-Run rviz and subscribe to different published topics to visualize the map
```sh
$ rosrun rviz rviz

Edit the rviz configuration as follows:

Change the Fixed Frame to map
Keep Reference Frame as default
Add a RobotModel
Add a camera and select the /camera/rgb/image_raw topic
Add a map and select the /map topic
```



