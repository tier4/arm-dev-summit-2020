# Exercise 3: NDT Scan Matching

The purpose of this exercise is to show some features of Autoware's localization, which is achieved through a method called NDT Scan Matching. 

## Automatic self-pose estimation using GNSS
In the past, it was necessary to manually set the initial pose of the ego-vehicle, or to have recorded data containing a manually set initial pose. It is now possible for Autoware to estimate the initial pose of the ego-vehicle automatically using GNSS sensor data. This is a new feature that will be added to Autoware.Auto in the near future.

1. Open two terminal windows and run the following commands in *both* terminals
```
cd /home/autoware/autoware.proj
source ./install/setup.bash
``` 
2. In the first terminal, launch RViz
```
roslaunch autoware_launch autoware.launch rosbag:=true map_path:=/home/autoware/handson/ex3/maps
```
3. In the second terminal, play the rosbag file and then click on the RViz icon to bring the RViz window to the front
```
rosbag play --clock /home/autoware/handson/ex3/sample.bag -r 0.2
```
Whilst still in the 2D TopDownOrth view, we can see the recorded LiDAR sensor data being displayed, and then after a few seconds, the NDT Scan Matching algorithm uses recorded GNSS data to establish an initial pose that is then used to match up the LiDAR sensor data with the high-definition pointcloud map data loaded into memory.

TODO: Add a screenshot showing a TopDownOrth view of the ego-vehicle + LiDAR and map

## Pose estimation without GNSS initial pose
If GNSS data is not available, then the initial pose of the ego-vehicle can be manually set using RViz (something that we will come back to in the next exercise). For now, let's see what happens if we try to replay a rosbag with GNSS sensor data removed.

4. Open two new terminal windows and run the following commands in *both* terminals
```
cd /home/autoware/autoware.proj
source ./install/setup.bash
``` 
5. In the first terminal, launch RViz
```
roslaunch autoware_launch autoware.launch rosbag:=true map_path:=/home/autoware/handson/ex3/maps
```
6. In the second terminal, play the rosbag file and then click on the RViz icon to bring the RViz window to the front
```
rosbag play --clock /home/autoware/handson/ex3/sample.bag -r 0.2
```
7. Whilst still in the 2D TopDownOrth view, you will note that the ego vehicle does not appear as before. To see the ego-vehicle, pause the rosbag playback and change the Target Frame of the view to "base_link".
- In the Views panel on the left side of the window, double-click the Target Frame value and select "base_link"
- Click the "Zero" button

TODO: Add image showing TopDownOrth, but with the Target View set to "base_link"

The view now shows the ego-vehicle and the recorded LiDAR sensor data, but the HD map is not displayed because it's impossible for the NDT Scan Matching algorithm to match the LiDAR sensor data to the map's pointcloud data without an initial pose.

TODO: Add a screenshot showing a TopDownOrth view of the ego-vehicle + LiDAR without the map showing

1. Repeat steps 4-6, but this time hit the spacebar to pause the rosbag's playback after about 5 seconds.

2. Go back to RViz, scroll the map to the approximate position of where the ego-vehicle should be (behind the stop line of the intersection), then click the "2D Pose Estimate" button, then click and hold the left mouse button in the desired position and drag in the direction that the ego-vehicle is facing.

3.  Go back to the second terminal and hit spacebar to resume playback

Given an initial pose, the NDT Scan Matching algorithm is now able to match the sensor data with the map's pointcloud data. 

| Next |
| ---- |
| [Exercise 4: Simulation testing with dummy objects](exercise4.md) |
