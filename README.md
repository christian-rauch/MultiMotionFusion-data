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
