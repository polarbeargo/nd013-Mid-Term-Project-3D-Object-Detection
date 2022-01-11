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
[image11]: ./img/show_pcl.png
[image12]: ./img/ID_S1_EX2.png
[image13]: ./img/Open3D3.png
[image14]: ./img/Open3D1.png
[image15]: ./img/Open3D4.png
[image16]: ./img/bevFromPCL.png
[image17]: ./img/ID_S2_EX1.png
[image18]: ./img/bev_from_pcl.png
[image19]: ./img/height.png
[image20]: ./img/intensity.png
[image21]: ./img/intensityBEV.png
[image22]: ./img/heightBEV.png
[image23]: ./img/ID_S3Settings.png
[image24]: ./img/labelsVSDetected.png
[image25]: ./img/labelsVSDetected2.png

Please use this starter template to answer the following questions:  
In this project, we used the [Waymo Open Dataset](https://waymo.com/open/terms)'s real-world data with 3d point cloud library for lidar based object detection.  
- In the Waymo Open dataset, lidar data is stored as a range image. Therefore, this task is about extracting two of the data channels within the range image, which are "range" and "intensity", and convert the floating-point data to an 8-bit integer value range then display the range /intensity image (ID_S1_EX1) use the OpenCV library to stack the range and intensity image vertically and visualize it.
- Use the Open3D library to display the lidar point-cloud in a 3d viewer then identify 10 images from point cloud find vehicle features that appear stable in most of the inspected examples and describe them (ID_S1_EX2).  
- Create Birds-Eye View (BEV) from Lidar PCL based on the (x,y)-coordinates in sensor space, compute the respective coordinates within the BEV coordinate space in subsequent tasks and map lidar intensity values to BEV,normalize the heatmap of each BEV. Plotting intensity values from the BEV map (ID_S2_EX1,ID_S2_EX2,ID_S2_EX3).  
- Clone the repo [Super Fast and Accurate 3D Object Detection based on 3D LiDAR Point Clouds](https://github.com/maudzung/SFA3D), Extract the relevant parameters from SFA3D->test.py->parse_test_configs() and add them to the configs structure in load_configs_model and Instantiate the model for fpn_resnet (ID_S3_EX1)
- Performing BEV coordinates into pixel coordinates and convert model output to bounding box format such that all detections have the format [1, x, y, z, h, w, l, yaw], where 1 denotes the class id for the object type vehicle  (ID_S3_EX2).
- Compute the geometrical overlap between the bounding boxes of labels and detected objects and determine the percentage of this overlap in relation to the area of the bounding boxes which call intersection over union (IOU). (ID_S4_EX1)
- Determine the number of false positives, false negatives for the current frame. After processing all the frames of a sequence, we measure precision and recall to evaluate the performance of the object detection algorithm (ID_S4_EX2,ID_S4_EX3).  
### How to run this project:  

```
python loop_over_dataset.py
```   
### Project Instructions Step 1: Compute Lidar Point-Cloud from Range Image

* Extracting "range" and "intensity" two data channels within the range image.   
* Convert the floating-point data to an 8-bit integer value range.  
* Display the range /intensity image (ID_S1_EX1) use the OpenCV library to stack the range and intensity image vertically and visualize it.   
#### The changes in the settings are:
![][image1]
![][image2]

The function show_range_image located in the file `student/objdet_pcl.py`.
![][image3]  
* The result range images:  
![][image4]
![][image6]
![][image7]  
In this part, we use the Open3D library to display the lidar point-cloud in a 3d viewer
![][image12]
![][image5]
![][image11]
* Point cloud images:  
![][image15]
![][image14]
![][image13]  
### Project Instructions Step 2 : Create Birds-Eye View from Lidar PCL  
* Create Birds-Eye View (BEV) from Lidar PCL based on the (x,y)-coordinates in sensor space.
* Compute the respective coordinates within the BEV coordinate space in subsequent tasks and map lidar intensity values to BEV.
* Normalize the heatmap of each BEV. Plotting intensity values from the BEV map  
#### The changes in the settings are:  
![][image17] 
![][image10] 
The function bev_from_pcl located in the file `student/objdet_pcl.py`. 
![][image16] 
* BEV
![][image18]

![][image20]
![][image22]  

| height map | intensity map |
| ------------- | ------------- |
| ![][image19]  | ![][image21] |   
### Project Instructions Step3 : Model-based Object Detection in BEV Image  
* Clone the repo [Super Fast and Accurate 3D Object Detection based on 3D LiDAR Point Clouds](https://github.com/maudzung/SFA3D).  
* Extract the relevant parameters from SFA3D->test.py->parse_test_configs() and add them to the configs structure in load_configs_model and Instantiate the model for fpn_resnet.  
* Performing BEV coordinates into pixel coordinates and convert model output to bounding box format such that all detections have the format [1, x, y, z, h, w, l, yaw], where 1 denotes the class id for the object type vehicle.  
#### The changes in the settings are:  
![][image23]
![][image9]  

| labels VS Detected 1 | labels VS Detected 2 |
| ------------- | ------------- |
| ![][image24]  | ![][image25] |   

### Project Instructions Step 4 : Performance Evaluation for Object Detection  
* Compute the geometrical overlap between the bounding boxes of labels and detected objects and determine the percentage of this overlap in relation to the area of the bounding boxes which call intersection over union (IOU). 
* Determine the number of false positives, false negatives for the current frame.  
* After processing all the frames of a sequence, we measure precision and recall to evaluate the performance of the object detection algorithm.  
#### The changes in the settings are:   
![][image8] 
 The function bev from PCL located in the file `student/objdet_eval.py`. 


### 1. Write a short recap of the four tracking steps and what you implemented there (filter, track management, association, camera fusion). Which results did you achieve? Which part of the project was most difficult for you to complete, and why?


### 2. Do you see any benefits in camera-lidar fusion compared to lidar-only tracking (in theory and in your concrete results)? 


### 3. Which challenges will a sensor fusion system face in real-life scenarios? Did you see any of these challenges in the project?


### 4. Can you think of ways to improve your tracking results in the future?

