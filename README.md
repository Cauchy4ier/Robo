Trajectory planning for UR3 robotic arm
========================================
Author: Junqi Ren (Karl)    
  This package works on trajectory planning in Rviz and Gazebo for the 6 dof UR3 robotic arm. We can move the end effector to any specific point with the script "movetopoint.py" where the path from the initial point to the destination is a straight line. However, we could move the end effector of UR3 not only in lines but also in curves or splines with computing Cartesian path. Running "circle.py" could let the end effector move in a full circle and other splines or polynomials could also work in the same way.  
  The package works in Ubuntu 14.04 ROS Indigo. I also try to load the universal robot model and run the package in Ubuntu 16.04 ROS Kinetic but I met consecutive problems when I try to catkin make the original UR package and my own package. These problems are very common and a lof of engineers have also met these problems when compiling. I spent weeks but just only solved some of them. At last, I turned to Indigo and this time everything went smoothly. Thanks god.    
  I will elaborate how to solve the problems that I met in the following Troubleshooting part.  
## Dependencies:
  Go and check https://github.com/ros-industrial/universal_robot to get urdf,xacro,yaml and all the files you want. Please follow the instructions in http://wiki.ros.org/action/show/universal_robots?action=show&redirect=universal_robot and install all the dependencies. Wiki.ros.org has a comprehensive introduction of how is everything working in the UR package and you would find the solution to your problem after a careful reading(for the most of time).  
  However, no matter you are using Indigo or Kinetic,after you installing the universal robot package, you are very likely to encounter a problem when compiling,called *Action client not connected: PositionJointInterface_trajectory_controller/follow_joint_trajectory* Any edition in controller.yaml does not help. Actually you are lack of the gazebo-ros-control package. So just run `sudo apt-get install ros-$$$-gazebo-ros-pkgs ros-$$$-gazebo-ros-control` and $$$ is either indigo or kinetic.  
## Roll up our sleeves
