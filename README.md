# MAE-275-Vineyard-UAS
Dual Camera-Based Control of a Quadcopter for Autonomous Crop Spraying Applications  
Members: Andrew Arends - Dinesh Kumar -  George Martin  - Prawin Sankar  
University of California, Davis - Spring 2022

This project attempts to design a surveying and path-planning algorithm for a quadcopter to fly over rows of trees, maintaining constant relative altitude to the top of the treeline.

Software Requirements: Ubuntu 20.04 and ROS 1 (Noetic) previously installed.

1. Install ROS Noetic
    a. Enable Repositories
        https://linuxconfig.org/how-to-enable-disable-universe-multiverse-and-restricted-repository-on-ubuntu-20-04-lts-focal-fossa
    b. Install ROS
      http://wiki.ros.org/noetic/Installation/Ubuntu
2. Install PX4 with MAVSDK  
    a. Install PX4 Environment  
      https://docs.px4.io/master/en/dev_setup/dev_env_linux_ubuntu.html  
    b. Install MAVSDK with QGroundControl  
      https://mavsdk.mavlink.io/main/en/cpp/quickstart.html  
3. Install Kinect Model Files > ~/.gazebo/models  
    https://github.com/osrf/gazebo_tutorials/tree/master/ros_depth_camera/files  
4. Download MAE 275 Package  
    a. Download Package Files (this Github)  
    b. Setup World  
      i. Move Orchard.world File > PX4-Autopilot/Tools/sitl_gazebo/worlds/  
    c. Setup Drone Environment  
      i. Follow Gazebo World Setup Instructions from Andrew  
     ii. Move ‘mae275drone’ Folder > PX4-Autopilot/Tools/sitl_gazebo/models  
    iii. Move ‘mae275drone.world’ > PX4-Autopilot/Tools/sitl_gazebo/worlds  
     iv. Move ‘2750_mae275drone’ file > PX4-Autopilot/ROMFS/px4fmu_common/init.d-posix/airframes  
      v. Type ‘mae275drone’ > PX4-Autopilot/platforms/posix/cmake/sitl_target.cmake in the command set(models           …  *HINT*Line 144  
     vi. Move ‘mae275_posix_sitl.launch’ > PX4-Autopilot/launch  
  5. Test Run   
    a. New terminal -     cd PX4-Autopilot  
    b. ‘make px4_sitl gazebo_MAE275Drone__Orchard’  
      i. If it does not launch, may have to copy step iv. Into tmp folder, follow error path  
  6. Copy mae275drone_sim.sh to home  
    a. ‘bash mae275drone_sim.sh’ to run automated roslaunch with PX4


NOTE: setup.bashrc should have the following lines appended:  
source /opt/ros/noetic/setup.bash  
source ~/catkin_ws/devel/setup.bash  
source ~/PX4-Autopilot/Tools/setup_gazebo.bash \~/PX4-Autopilot \~/PX4-Autopilot/build/px4_sitl_default  
export ROS_PACKAGE_PATH=/home/george/catkin_ws/src:/opt/ros/noetic/share:~/PX4-Autopilot:~/PX4-Autopilot/Tools/sitl_gazebo





