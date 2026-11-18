# clone-funny-lidar-without-rtk-from-commit


# Livox Ros2 driver2 install on ros2 humble

    mkdir livox_ws
    cd livox_ws
    mdkir src
    cd src
    
## clone Livox SDK2

    git clone https://github.com/Livox-SDK/Livox-SDK2.git
    cd ./Livox-SDK2/
     mkdir build
     cd build
     cmake .. && make -j
     sudo make install

## clone Livox ros deiver2

    cd ~/livox_ws/src
    git clone https://github.com/Livox-SDK/livox_ros_driver2.git

## after cloning 

    cd ~/livox_ws/src/livox_ros_driver2
    source /opt/ros/humble/setup.bash
    ./build.sh humble



Clone and checkout a specific commit
====================================

Repository:
 
    https://gitee.com/qingdao-qingcheng-digital/qc_lidar_slam.git

Target commit:
  dd6c5e49695c475be350a8bf7c1ea98cdc641ee9

Important:
  git clone -b <commit-hash> does NOT work.
  -b only accepts branch names or tag names.
  Use: clone -> fetch -> checkout <commit-hash>


Commands
--------

# 1. Clone the repository

    git clone https://gitee.com/qingdao-qingcheng-digital/qc_lidar_slam.git

# 2. Enter the repository

    cd qc_lidar_slam

# 3. Fetch all remote refs

    git fetch origin

# 4. Checkout the exact commit

    git checkout dd6c5e49695c475be350a8bf7c1ea98cdc641ee9

# 5. Verify

    git log -1 --oneline
    
# Expected output starts with:
# dd6c5e4 fix:rename mid360 file


If cloning inside a ROS 2 workspace
-----------------------------------

    cd ~/funny_lidar_slam_ws0/src
    git clone https://gitee.com/qingdao-qingcheng-digital/qc_lidar_slam.git
    cd qc_lidar_slam
    git fetch origin
    git checkout dd6c5e49695c475be350a8bf7c1ea98cdc641ee9
    git log -1 --oneline


Notes
-----

- After checkout, Git enters "detached HEAD" state. This is normal.
- To return to a branch later:
    git checkout ros2_humble
- Do not use "git clone --depth 1" if you need an older commit.
- To verify the commit exists remotely:
    git ls-remote https://gitee.com/qingdao-qingcheng-digital/qc_lidar_slam.git | grep dd6c5e4
