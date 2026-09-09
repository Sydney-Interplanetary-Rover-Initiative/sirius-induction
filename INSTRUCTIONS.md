# Welcome to SIRI Software's Induction
First of all, welcome to SIRI Software's induction task. This task will provide you with the motivation to get you to "self learn" ROS2 and prove your capabilities to the software team. The induction task varies in difficulty depending on how many members we currently have. There's a total of 3 difficulty levels: "Very Hard", "Hard", and "Medium" difficulty. Currently this induction task is rated:

**Hard**

If it shows "Hard" or "Very Hard" there, don't fret! The good news is the more you understand about ROS2 the more you **will** inevitably progress. If you're the type to be up for challenging problems, you'd sure love the extra challenge!

## Instructions
We have provided you with a `wall_navigator` package containing 2 worlds: `maze_complex.world` and `maze_easy.world`. Both these maps contain a green starting area alongside a colored cube. 

Your task is to setup a robot that will **spawn** on the green starting area and **autonomously** search for the red cube by successfully navigating through 2 mazes. You are not allowed to hard code the exact turns to search for the cube. This means that your algorithm needs to contain some kind of maze searching algorithm (at minimum it is recommended to be at least as complex as a simple wall follower). 

Once the cube has been found, the robot should stop a distance away from the cube. The distance to stop from the cube needs to be supplied as a ROS2 node parameter. Note that to make this task easier, this distance *does not need to be in meters* (it could be some dimensionless number that is directly proportional to the distance).

This implementation requires you to use 3D SLAM (not 2D SLAM, some examples of 2D SLAM systems are `slam_toolbox`, Google Cartographer 2D, etc.). The 3D SLAM system needs to use at least **1 depth camera**. Finally, you need to generate a Nav2 costmap using the 3D SLAM system and the Nav2 costmap should be used to determine whether there is a wall or not in your maze solving algorithm.

Finally, the implementation should work on ROS2 Jazzy and you are required to use the new Gazebo. Instead of having to write multiple nodes manually, a launch file should be written to launch everything needed in one go. To launch a different map, either a separate launch file can be launched or a launch file parameter can be passed in to select which map to load (this should be documented in the README).


### Deliverables
During your implementation, you should *fork* this repository and invite both of the software leads to your repository:
- wwij0922@uni.sydney.edu.au
- myip5150@uni.sydney.edu.au

Make sure to document how to run your robot in the README. An explanation of how your code works should also be put in the README.

After completion, email the leads with a **link** to your repository and attach a video (uploaded to OneDrive shared with both leads) showing the completion of each of the 2 mazes (thus 2 videos total, one for each maze).

The leads will try to get back to you as quickly as possible. And once we've verified your completion, we'll have a meeting (likely in-person) where we'll review your code and provide feedback. During this meeting, be sure to bring your laptop and ensure that you can run your code.

## Tips
To aid in your implementation, we have provided you with some resources. First, it is highly recommended to finish both playlists of Articulated Robotics.
- https://www.youtube.com/watch?v=2lIV3dRvHmQ&list=PLunhqkrRNRhYYCaSTVP-qJnyUPkTxJnBt
- https://www.youtube.com/watch?v=OWeLUSzxMsw&list=PLunhqkrRNRhYAffV8JDiFOatQXuU-NnxT

Apart from that, it is recommended to read the tutorial section of the official ROS2 documentation (Beginner and Intermediate is usually enough).

- https://docs.ros.org/en/jazzy/Tutorials.html

You might also notice that the `articubot_one` repository is provided as a git submodule. It is recommended not to edit anything in this repository. You can instead call the various launch files, or load the URDF description found in the `articubot_one` repository. 

Finally, our [wiki](https://siri-wiki.netlify.app) might help provide some clues. In particular, the debugging guide may help. 

A tip is to use reference code as much as possible. From the reference code, be sure to understand how it works and **incrementally** change the code to fit your needs. 

AI use is generally fine as long as you understand what you are doing.
