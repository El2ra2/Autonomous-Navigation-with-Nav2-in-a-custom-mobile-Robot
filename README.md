# Autonomous-Navigation-with-Nav2-in-a-custom-mobile-Robot
Created a custom mobile differential drive Robot and used Nav2 for autonomous navigation, avoiding static and dynamic obstacles while reaching a goal. 

To setup, build basic libraries and dependencies- colcon, ros2-jazzy, gazebo harmonic, rviz, nav2, SLAM toolbox. Copy and paste the ROS2_Workspace in your directory.

Steps to build and run the simulation- 

-Launch our Robot Description Nodes, RViz and Gazebo through the launch file display.launch.py. Open a new terminal and execute the lines below.

colcon build
. install/setup.bash
ros2 launch sam_bot_description display.launch.py


-Launch the async_slam_toolbox_node of slam_toolbox using the package’s built-in launch files. Open a new terminal and then execute the following lines:

ros2 launch slam_toolbox online_async_launch.py use_sim_time:=true

-Now launch Nav2 using the nav2_bringup’s built-in launch file, navigation_launch.py. We will use my custom Nav2 parameters. Open a new terminal and execute the following:

ros2 launch nav2_bringup navigation_launch.py params_file:=sam_bot_description/config/nav2_params.yaml use_sim_time:=true


