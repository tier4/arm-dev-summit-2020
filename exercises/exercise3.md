# Exercise 3: Object detection and sensor fusion

1. Open the autoware.launch file, which should be located in the following folder:
~/AutowareArchitectureProposal/src/launcher/autoware_launch/launch

2. Under the `<!-- Perception -->` section, edit the following line as follows:

From:
```xml
<arg name="mode" value="lidar"/>
```

To:
```xml
<arg name="mode" value="camera_lidar_fusion"/>
```

3. Open two terminals, and run the following commands in the first terminal:
```
cd ~/AutowareArchitectureProposal
source ./devel/setup.bash
roslaunch autoware_launch autoware.launch map_path:=~/ARMDevSummit2020_AutowareWorkshop/ex3/maps rosbag:=true
```

4. In the second terminal, run the following commands, then hit the space bar to pause rosbag playback:
```
cd ~/AutowareArchitectureProposal
source ./devel/setup.bash
rosbag play --clock ~/ARMDevSummit2020_AutowareWorkshop/ex3/ex3.bag -r 1 
```

5. In RViz, switch to ThirdPersonFollower view and adjust the view to your preference.

6. Return to the second terminal and hit the space bar again to resume playback, then return to RViz.

| Next |
| ---- |
| [Exercise 4: Traffic Light Recognition](exercise4.md) |
