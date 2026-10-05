# Wall Navigator - Sydney Interplanetary Rover Initiative Induction Task

Autonomous wall-following ROS 2 node for the `articubot_one` rover inside Gazebo Harmonic.

## Logic Overview
The `wall_navigator_node` subscribes to `/scan` (from the Gazebo `gpu_lidar` sensor) and processes 360° LiDAR range data split into directional sectors (Front, Left, Right):
* **Proportional Wall Tracking:** Uses proportional control to target a stable ~0.6m distance from the left wall, smoothly adjusting `angular.z` without discrete step jitter.
* **Front Obstacle Avoidance:** Triggers active right-hand turns while maintaining forward creep velocity to prevent getting stuck in tight corners.
* **Open Area Search:** Executes gentle curving turns when the left wall is lost to re-acquire the corridor geometry cleanly.

## Video Demonstrations
* **Easy Maze Demo:** https://1drv.ms/v/c/fbc426b162c1e057/IQBs_PRo10SyQqfO6KbyBLVHAYiJoQ-sMCch0Jo0LUnmmiE?e=JvSYYz
* **Complex Maze Demo:** https://1drv.ms/v/c/fbc426b162c1e057/IQA-hW68VYzURpcTziTF9rFSAS58Ip_nYVynga5egBbzAxU?e=ujG3QY

## Prerequisites
* ROS 2 Jazzy
* Gazebo Harmonic (`ros_gz_sim` / `ros_gz_bridge`)
* Ubuntu 24.04 (WSL2)

## How to Build and Run

1. **Build Workspace:**
   cd ~/ros2_ws
   colcon build --symlink-install
   source install/setup.bash 
   

2. **Launch Simulation Environment:**

    export LIBGL_ALWAYS_SOFTWARE=1
    ros2 launch wall_navigator launch_sim.launch.py

3.  **Run Wall Navigator Node:**

    source install/setup.bash
    ros2 run wall_navigator wall_navigator_node    


