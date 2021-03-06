# Exercise 2: RViz basics and replaying a rosbag
The purpose of this exercise is to gain familiarity with the basic functionality of RViz and how to replay a rosbag. [RVIz](http://wiki.ros.org/rviz) is a 3D visualization tool for the ROS middleware that Autoware is based on, and [rosbag](http://wiki.ros.org/rosbag) is the file format used to record and playback data from a ROS-based system.

## Launch RViz, start and pause rosbag playback
1. Open two terminal windows and run the following commands in *both* terminals
```
cd /home/autoware/autoware.proj
source ./install/setup.bash
``` 
2. In the first terminal, launch RViz
```
roslaunch autoware_launch logging_simulator.launch vehicle_model:=lexus sensor_model:=aip_xx1 map_path:=/home/autoware/handson/ex2/maps
```
3. In the second terminal, play the rosbag file
```
rosbag play --clock /home/autoware/handson/ex2/sample.bag -r 0.2
```
4. In the still active second terminal, hit the spacebar after a few seconds to pause rosbag playback. You should now see something similiar to the screenshot below.

![](images/exercise2/01_ExpectedRVizView.png)

---

## Adjust the RViz view (TopDownOrth and ThirdPersonFollower)
5. Click on the RViz icon to bring the GUI to the front, and then adjust RViz view (TopDownOrth): 
- Clicking and holding the left mouse button then moving the mouse rotates the view in the same plane
- Clicking and holding the right mouse button then moving the mouse zooms in/out
- Holding the shift key and moving the mouse pans the view

6. Adjust RViz viewpoint to ThirdPersonFollower to change from a top-down 2D view to a 3D view
- In the Views panel on the left side of the window, click the Type dropdown box and select "ThirdPersonFollower"
- Double-click the Target Frame value and select "base_link"
- Click the “Zero” button

![](images/exercise4/views_properties.png)

7. Adjust RViz view (ThirdPersonFollower):
- In ThirdPersonFollower view, clicking and holding the left mouse button then moving the mouse rotates the view in all directions
- Other functions (holding the right mouse button, holding shift) behave the same as for TopDownOrth

8. Click the [Zero] button in the Views panel to move the displayed view to the origin of the base_link (the center of the vehicle's rear axle)

---

## Resume rosbag playback and toggle display options
9. Click in the second terminal, then hit the spacebar to resume rosbag playback

10. Toggling display options
- In the `Displays` panel, click the triangle icons next to `Sensing` and then the one next `LiDAR`
- Toggle “ConcatenatePointCloud” off and on by clicking the checkbox.
- Toggle “NoGroundPointCloud” off and on by clicking the checkbox.

11. Once the rosbag playback has completed, click on the first terminal and press Ctrl + C to end the running roslaunch command, then close the Terminator window.


| Next |
| ---- |
| [Exercise 3: Localization using NDT Scan Matching](exercise3.md) |
