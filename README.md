# Autonomous Robot

This is an Autonomous Robot, which is made using ROS2, and it can navigate using SLAM (Similtanious Localization and Mapping) technology.

# Basic Robot URDF

[first_urdf_robot.webm](https://github.com/c1ph3r-fsocitey/Autonomous_Robot/assets/109020327/aed04b55-98ce-4107-984b-bbf5cf0c60bb)

# Robot with Camera and Lidar Sensor

https://github.com/c1ph3r-fsocitey/Autonomous_Robot/assets/109020327/a4ebe990-71cb-4d72-9268-e0019bc63400

# Working of the Robot

[SLAM_Working.webm](https://github.com/c1ph3r-fsocitey/Autonomous_Robot/assets/109020327/e88dada2-21bb-4579-ba1d-a2764fd48572)

## Usage 

### Step 1: Insalling ROS2 Humble

To make sure that this code works, please install ROS2 (Humble) first, details of which can be found [here](https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debians.html)

### Step 2: Cloning the repository
clone the repository using the code below
```
git clone https://github.com/c1ph3r-fsocitey/Autonomous_Robot
```
### Step 3: Navigating to the directory
```
cd Autonomous_Robot
```

### Step 4: Build the workspace using colcon build 
```
colcon build --symlink-install
```
--symlink-install is used to make sure that any changes in the code are automatically picked up by colcon builder, and building the workspace is not nessecarry again

### Step 5: Run the code
using the following commands, run the robot for localisation and mapping
```
ros2 launch my_bot launch_sim.launch.py world:=dev_ws/src/my_bot/worlds/obstacles.world 
```
```
ros2 launch slam_toolbox online_async_launch.py params_file:=dev_ws/src/my_bot/config/mapper_params_online_async.yaml use_sim_time:=true
```
```
ros2 launch nav2_bringup navigation_launch.py use_sim_time:=true
```
```
ros2 run teleop_twist_keyboard teleop_twist_keyboard 
```
```
rviz2
```
