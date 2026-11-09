# clone-funny-lidar-without-rtk-from-commit


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
