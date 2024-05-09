# distance_tracker_service package

## Overview
The `distance_tracker_service` is a ROS node designed to track the cumulative distance traveled by a robot. It subscribes to odometry data provided by `nav_msgs/Odometry` and maintains a tally of the distance, which can be accessed on-demand. A service server implemented with `std_srvs/Trigger.h` responds to requests with the total distance traveled. This functionality is crucial for robotic projects involving navigation, mapping, or any scenario where tracking movement metrics is necessary.

Originally developed by Roberto Zegers and hosted by [TheConstruct](https://bitbucket.org/theconstructcore/advanced_cpp_auxiliary_pkgs), this package is licensed under the BSD-3-Clause license. It has been adapted in this repository to enhance compatibility and extend functionality with other robotic systems, including integration with the `robot_gui` project. For a comprehensive robotic control and monitoring solution, visit [robot_gui on GitHub](https://github.com/MarkBilginer/robot_gui).

## Usage
To use the `distance_tracker_service` in your ROS workspace:

1. Clone the repository:
```
cd ~/catkin_ws/src
git clone https://github.com/MarkBilginer/distance_tracker_service.git
```

2. Compile the workspace:
```
cd ~/catkin_ws
catkin_make
source devel/setup.bash
```

3. Ensure a robot simulation or a real robot setup publishing odometry data is running.

4. Launch the service:
```
rosrun distance_tracker_service distance_tracker_service
```

## Manual Testing
To manually test the service and confirm its functionality:
```
rosservice call /get_distance "{}"
```

The output should be similar to the following:  
```
success: True
message: "7.52"
```

This test will demonstrate the service's ability to accurately report the distance traveled based on the odometry data it receives.

## License
This project is maintained under the BSD-3-Clause License, which allows for modification and redistribution under the same terms.

## Dependencies
- ROS Noetic

