# Writeup: Track 3D-Objects Over Time

Please use this starter template to answer the following questions:  
In this project, we used the [Waymo Open Dataset](https://waymo.com/open/terms)'s real-world data with 3d point cloud library for lidar based object detection.  
- In the Waymo Open dataset, lidar data is stored as a range image. Therefore, this task is about extracting two of the data channels within the range image, which are "range" and "intensity", and convert the floating-point data to an 8-bit integer value range then display the range /intensity image (ID_S1_EX1) use the OpenCV library to stack the range and intensity image vertically and visualize it.
- Use the Open3D library to display the lidar point-cloud in a 3d viewer then identify 10 images from point cloud find vehicle features that appear stable in most of the inspected examples and describe them (ID_S1_EX2). 

### 1. Write a short recap of the four tracking steps and what you implemented there (filter, track management, association, camera fusion). Which results did you achieve? Which part of the project was most difficult for you to complete, and why?


### 2. Do you see any benefits in camera-lidar fusion compared to lidar-only tracking (in theory and in your concrete results)? 


### 3. Which challenges will a sensor fusion system face in real-life scenarios? Did you see any of these challenges in the project?


### 4. Can you think of ways to improve your tracking results in the future?

