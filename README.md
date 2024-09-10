# lego-loam_ndt
**we add map save service in [LeGO-LOAM](https://github.com/RobustFieldAutonomyLab/LeGO-LOAM), ndt_localizer is used to complete localization work based on normal distribution voxel map.**

** **

## 0. Features
[LeGO-LOAM](https://github.com/RobustFieldAutonomyLab/LeGO-LOAM) is a 3D Lidar SLAM with loop detection function, which can be used for large-scale scene mapping. The ndt_localizer can achieve general scene representation using Gaussian distribution voxels and perform real-time localization.

## 1. Prerequisites
### 1.1 **Ubuntu** and **ROS**
**Ubuntu >= 18.04**

ROS    >= Melodic. [ROS Installation](http://wiki.ros.org/ROS/Installation)

### 1.2. **PCL && Eigen**
PCL    >= 1.8,   Follow [PCL Installation](http://www.pointclouds.org/downloads/linux.html).

Eigen  >= 3.3.3, Follow [Eigen Installation](http://eigen.tuxfamily.org/index.php?title=Main_Page).

### 1.3. **livox_ros_driver**
Follow [livox_ros_driver Installation](https://github.com/Livox-SDK/livox_ros_driver).

## 2. Build

Clone the repository and catkin_make:

```
    cd ~/$A_ROS_DIR$/src
    git clone https://github.com/Hero941215/fast-lio2_swba
    cd fast-lio2_swba
    git submodule update --init
    cd ../..
    catkin_make
    source devel/setup.bash
```
- Remember to source the livox_ros_driver before build (follow 1.3 **livox_ros_driver**)

## 3. Run
### 3.1. **run with hilti dataset**

roslaunch robotrun tight_slam_ouster_indoor.launch (hilti-2021)

roslaunch robotrun tight_slam_pandar_indoor.launch (hilti-2022)

### 3.2. **run with UrbanNav dataset**

roslaunch robotrun tight_slam_velodyne_outdoor.launch

### 3.3. **run with livox mid-360**

roslaunch robotrun tight_slam_mid360_indoor.launch

## 4. Acknowledgments

Thanks for LOAM(J. Zhang and S. Singh. LOAM: Lidar Odometry and Mapping in Real-time), [FAST-LIO2](https://github.com/hku-mars/FAST_LIO), [BALM2](https://github.com/hku-mars/BALM).
