# slambot_cartographer
## Installation
The package was made using [ROS2 Humble](https://docs.ros.org/en/humble/index.html)
## Dependencies
You need to have installed:
<br>
1. ros-xacro:
   ```console
   sudo apt install ros-<distro>-xacro
   ```
2. cartographer:
   ```console
   sudo apt install ros-<distro>-cartographer
   ```
3. cartographer-ros:
   ```console
   sudo apt install ros-<distro>-cartographer-ros
   ```

## :hammer: How to build
To build the packages in this repository follow these steps:
1. `cd` into an existing or create a new [workspace](https://docs.ros.org/en/foxy/Tutorials/Beginner-Client-Libraries/Creating-A-Workspace/Creating-A-Workspace.html)
   ```console
   mkdir -p ros_ws/src
   ```
2. clone this repository in the `src` folder of your workspace
   ```console
   cd ros_ws/src
   ```
   ```console
   git clone https://github.com/odobot/slambot_cartographer.git
   ```
3. Naviage back to the workspace folder
   ```console
   cd ../
   ```
4. build the workspace using the [colcon](https://colcon.readthedocs.io/en/released/reference/verb/build.html) build tool
   ```console
   colcon build --symlink-install
   ```
5. source the `setup.bash` file
   ```console
   source install/setup.bash
   ```
6. You can add the `setup.bash` file on the bashrc script file, just open the file and add it at end:
    ```console
    gedit ~/.bashrc
    ```
    ```console
    source ~/ros_ws/install/setup.bash
    ```

## :movie_camera: Rviz
To view the urdf in rviz open 3 terminals:
<br>
On the first terminal (needs to the terminal you sourced your setup.bash file in) type: 
```console
  ros2 launch slambot_cartographer rplidar.launch.py
  ```
Second terminal
 ```console
  rviz2
  ```
In rviz for the Fixed frame use `base_link`. Add LaserScan at the Displays, under the topic add `/scan` to view the laser data


## 🎥 All in one
To launch rviz2 and view the robot_description and map, use this command:
 ```console
  ros2 launch slambot_cartographer complete.launch.py