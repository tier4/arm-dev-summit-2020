# Exercise 4: Simulation testing with dummy objects

The purpose of this exercise is to become familiar with Autoware's planning simulator, which can be used for a variety of things such as validating vector maps (containing metadata about the road layout, traffic rules etc) and verifying Autoware's route planning functionality.

For this exercise, we will only need to use a single terminal window.

## Run RViz and set initial and goal poses
1. Open a terminal window, navigate to the Autoware.IV install directory and run the following command:
   
```
source ./install/setup.bash
```

2. Run RViz with the following command:

```
roslaunch autoware_launch planning_simulator.launch vehicle_model:=lexus sensor_model:=aip_xx1 map_path:=/home/autoware/handson/ex4/maps
```

![](images/exercise4/rviz.png)


1. Set the initial pose of the ego-vehicle
- Click “2D Pose estimate” button in the toolbar, or hit the “P” key
![](images/exercise4/toolbar_2D_pose.png)

- Click and hold the left-mouse button, and then drag to set the direction of the pose
![](images/exercise4/initial_pose.png)

4. Set the goal pose of the ego-vehicle
- Click the “2D Nav Goal” button in the toolbar, or hit the “G” key
![](images/exercise4/toolbar_2D_navgoal.png)

- Click and hold the left-mouse button, and then drag to set the direction of the pose
![](images/exercise4/goal_pose.png)

5. Confirm initial pose, goal pose and route are displayed

![](images/exercise4/poses_route.png)

---

## Adding and removing dummy obstacles, both moving and stationary
6. Add a dummy car
- Click the “2D Dummy Car” button in the toolbar, or hit the “K” key
![](images/exercise4/toolbar_2D_dummy_car.png)
- Click and hold the left-mouse button, and then drag to set the direction of the pose
![](images/exercise4/dummy_car_moving.png)

7. Add a dummy pedestrian
- Click the “2D Dummy Pedestrian” button in the toolbar, or hit the “L” key
![](images/exercise4/toolbar_2D_dummy_pedestrian.png)
- Click and hold the left-mouse button, and then drag to set the direction of the pose
![](images/exercise4/dummy_pedestrian_moving.png)

8. Make dummy pedestrians and dummy vehicles stationary, and add a stationary dummy vehicle
- In the [Tool Properties] panel in the lower-left, under [2D Dummy Car], set Velocity to 0
- Click the “2D Dummy Car” button
- Click and hold the left-mouse button, and then drag to set the direction of the pose
- In the [Tool Properties] panel in the lower-left, under [2D Dummy Pedestrian], set Velocity to 0
![](images/exercise4/tool_properties.png)

9. Remove all dummy objects
- Click “Delete All Objects” button in the toolbar, or hit the “D” key
![](images/exercise4/toolbar_delete_all_objects.png)
- Click the display

---

## "Number One, Engage!"
10.  Adjust RViz viewpoint to ThirdPersonFollower to change from a top-down 2D view to a 3D view
- In the Views panel on the left side of the window, click the Type dropdown box and select "ThirdPersonFollower"
- Double-click the Target Frame value and select "base_link"
- Click the “Zero” button
![](images/exercise4/views_properties.png)

![](images/exercise4/thirdpersonfollowerview.png)

11.  Use the Autoware Web UI to start the ego vehicle moving
- Open a browser and go to http://localhost:8085/autoware_web_controller
![](images/exercise4/autoware_web_ui.png)

- Under "Vehicle Engage”, click the "Engage" button
- Under “Autoware Engage: Connected”, click the “Engage” button
![](images/exercise4/autoware_web_ui_engage.png)

- In the Web UI, Autoware State will change from "WaitingForEngage" to "Driving" and the ego-vehicle should now start moving along the route to the goal pose
  
![](images/exercise4/autoware_ui_engaged.png)




