# Sparse-Dense Motion Modelling and Tracking for Manipulation without Prior Object Models

This repo contains the RGB-D sequences used for the paper ["Sparse-Dense Motion Modelling and Tracking for Manipulation without Prior Object Models"](https://doi.org/10.1109/LRA.2022.3200177) in the ROS 1 bag format.

The bag files contain the colour images with intrinsics, the depth images registered to the colour frame and ground truth camera poses:
```
/depth_to_rgb/camera_info                    : sensor_msgs/CameraInfo
/depth_to_rgb/image_raw/compressed           : sensor_msgs/CompressedImage
/depth_to_rgb/image_raw/filtered/compressed  : sensor_msgs/CompressedImage
/diagnostics                                 : diagnostic_msgs/DiagnosticArray
/rgb/camera_info                             : sensor_msgs/CameraInfo
/rgb/image_raw/compressed                    : sensor_msgs/CompressedImage
/tf                                          : tf2_msgs/TFMessage
/tf_static                                   : tf2_msgs/TFMessage
/vicon/kinect/kinect                         : geometry_msgs/TransformStamped
/vicon/markers                               : vicon_bridge/Markers
```

If you use this data, please cite:
```bibtex
@ARTICLE{Rauch2022,
  author={Rauch, Christian and Long, Ran and Ivan, Vladimir and Vijayakumar, Sethu},
  journal={IEEE Robotics and Automation Letters},
  title={Sparse-Dense Motion Modelling and Tracking for Manipulation Without Prior Object Models},
  year={2022},
  volume={7},
  number={4},
  pages={11394-11401},
  doi={10.1109/LRA.2022.3200177}
}
```

Mirrors:
- https://conferences.inf.ed.ac.uk/MultiMotionFusion
- https://github.com/christian-rauch/MultiMotionFusion-data
- https://gitlab.com/christian-rauch/MultiMotionFusion-data

## Usage

### Download

Install Git LFS via https://git-lfs.com or the Debian package:
```sh
sudo apt install git-lfs
git lfs install
```
and then download the repo via `git clone`.

### ROS 1

Use the ROS 1 `rosbag` command-line tool to publish the topics from the bag files:
```sh
rosbag play estimation/nx_estim1_manipulation.bag
```

### ROS 2

Install [`rosbags`](https://gitlab.com/ternaris/rosbags):
```sh
pip3 install rosbags
```
and convert the bag files from ROS 1 to ROS 2:
```sh
find . -type f -name *.bag -exec sh -c 'rosbags-convert --src $0 --dst ${0%.bag}' '{}' \;
```

Then you can use the ROS 2 command-line tool to publish the topics:
```sh
ros2 bag play estimation/nx_estim1_manipulation
```
