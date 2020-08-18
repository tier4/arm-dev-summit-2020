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

6. Add an Image panel that shows the recorded camera image data with perception data from the LiDAR sensor overlaid on top. 
- RViz toolbar -> Add -> by topic -> /sensing -> /camera ->

![](images/exercise3/add_sensor_fusion_image_view.png)

7. Return to the second terminal and hit the space bar again to resume playback, then return to RViz. Your RViz view should hopefully look similar to the image below

![](images/exercise3/sensor_fusion_one_camera.png)

8. Now, we've just displayed data from a single camera, but the rosbag actually contains data from six (!) cameras, so let's see what those six cameras look like when shown all together.

![](images/exercise3/sensor_fusion_six_cameras.png)

| Next |
| ---- |
| [Exercise 4: Traffic Light Recognition](exercise4.md) |
