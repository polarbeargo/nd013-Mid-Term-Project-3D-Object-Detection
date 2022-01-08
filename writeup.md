# Writeup: Track 3D-Objects Over Time
[image1]: ./img/ID_S1_EX1.png
[image2]: ./img/S1_EX1Settings.png
[image3]: ./img/code1.png
[image4]: ./img/S1_EX1s.png
[image5]: ./img/ID_S1_EX2setting.png
[image6]: ./img/S1_EX1s2.png
[image7]: ./img/S1_EX1s3.png
[image8]: ./img/ID_s4Settings.png
[image9]: ./img/ID_S3Setting.png
[image10]: ./img/ID_S2setting.png


Please use this starter template to answer the following questions:  
In this project, we used the [Waymo Open Dataset](https://waymo.com/open/terms)'s real-world data with 3d point cloud library for lidar based object detection.  
- In the Waymo Open dataset, lidar data is stored as a range image. Therefore, this task is about extracting two of the data channels within the range image, which are "range" and "intensity", and convert the floating-point data to an 8-bit integer value range then display the range /intensity image (ID_S1_EX1) use the OpenCV library to stack the range and intensity image vertically and visualize it.
- Use the Open3D library to display the lidar point-cloud in a 3d viewer then identify 10 images from point cloud find vehicle features that appear stable in most of the inspected examples and describe them (ID_S1_EX2).  
- Create Birds-Eye View (BEV) from Lidar PCL based on the (x,y)-coordinates in sensor space, compute the respective coordinates within the BEV coordinate space in subsequent tasks and map lidar intensity values to BEV,normalize the heightmap of each BEV. Plotting intensity values from the BEV map (ID_S2_EX1,ID_S2_EX2,ID_S2_EX3).  
- Clone the repo [Super Fast and Accurate 3D Object Detection based on 3D LiDAR Point Clouds](https://github.com/maudzung/SFA3D), Extract the relevant parameters from SFA3D->test.py->parse_test_configs() and add them to the configs structure in load_configs_model and Instantiate the model for fpn_resnet (ID_S3_EX1)
- Performing BEV coordinates into pixel coordinates and convert model output to bounding box format such that all detections have the format [1, x, y, z, h, w, l, yaw], where 1 denotes the class id for the object type vehicle  (ID_S3_EX2).
- Compute the geometrical overlap between the bounding boxes of labels and detected objects and determine the percentage of this overlap in relation to the area of the bounding boxes which call intersection over union (IOU). (ID_S4_EX1)
- Determine the number of false positives, false negatives for the current frame. After processing all the frames of a sequence, we measure precision and recall to evaluate the performance of the object detection algorithm (ID_S4_EX2,ID_S4_EX3).  
### How to run this project:  

```
python loop_over_dataset.py
```
![][image1]
![][image2]

The function show_range_image located in the file `student/objdet_pcl.py`.
![][image3]  
The result range images:  
![][image4]
![][image6]
![][image7] 
![][image5] 
![][image8] 
![][image9] 
![][image10] 
### 1. Write a short recap of the four tracking steps and what you implemented there (filter, track management, association, camera fusion). Which results did you achieve? Which part of the project was most difficult for you to complete, and why?


### 2. Do you see any benefits in camera-lidar fusion compared to lidar-only tracking (in theory and in your concrete results)? 


### 3. Which challenges will a sensor fusion system face in real-life scenarios? Did you see any of these challenges in the project?


### 4. Can you think of ways to improve your tracking results in the future?

