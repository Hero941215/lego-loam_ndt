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

### 1.3. **Gtsam**

```
  wget -O ~/Downloads/gtsam.zip https://github.com/borglab/gtsam/archive/4.0.0-alpha2.zip
  cd ~/Downloads/ && unzip gtsam.zip -d ~/Downloads/
  cd ~/Downloads/gtsam-4.0.0-alpha2/
  mkdir build && cd build
  cmake ..
  sudo make install
```

## 2. Build

Clone the repository and catkin_make:

```
    cd ~/$A_ROS_DIR$/src
    git clone https://github.com/Hero941215/lego-loam_ndt
    cd lego-loam_ndt
    git submodule update --init
    cd ../..
    catkin_make
    source devel/setup.bash
```

## 3. Run
### 3.1. **run lego-loam**

roslaunch lego_loam run.launch

### 3.2. **run ndt_localizer**

roslaunch ndt_localizer ndt_localizer.launch

#### Config map loader
Move your map pcd file (.pcd) to the map folder inside this project (`ndt_localizer/map`), change the pcd_path in `map_loader.launch` to you pcd path, for example:

```xml
<arg name="pcd_path"  default="$(find ndt_localizer)/map/kaist02.pcd"/>
```

## 4. Acknowledgments

Thanks for [LeGo-LOAM](https://github.com/RobustFieldAutonomyLab/LeGO-LOAM), [ndt_localizer](https://github.com/AbangLZU/ndt_localizer).
