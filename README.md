# Vehicle Detection
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)


The Project
---

The goals / steps of this project are the following:

* Perform a Histogram of Oriented Gradients (HOG) feature extraction on a labeled training set of images and train a classifier Linear SVM classifier
* Optionally, you can also apply a color transform and append binned color features, as well as histograms of color, to your HOG feature vector. 
* Note: for those first two steps don't forget to normalize your features and randomize a selection for training and testing.
* Implement a sliding-window technique and use your trained classifier to search for vehicles in images.
* Run your pipeline on a video stream (start with the test_video.mp4 and later implement on full project_video.mp4) and create a heat map of recurring detections frame by frame to reject outliers and follow detected vehicles.
* Estimate a bounding box for vehicles detected.


### HOG Feature Implementation

The HOG feature implementation is done in the HelperFunctions.py file. The function is called get_hog_features.

For the implementation of the HOG features the following parameters were used:
#### orient = 8  
#### pix_per_cell = 8 
#### cell_per_block = 2 


### Implementation of the Classifier

The classifier was trainined in the In [4] - In In [8] in the jupyter notebook.

1. Got the car and noncar images from the data provided
2. Extracted the features of car and non cars
3. Splitted the taining data and testing data 80-20
4. Trained the data using sklearn.svm.SVC and fir funstion.


### Sliding Window

The sliding window implementation is performed in the the HelperFunctions.py.

1. draw_bounding_boxes was used to implement slider in differnet sizes
2. Heat map applied on the selection for the purpose of removing the false positives
3. Threshold is applied to combine the heatmaps.
4. Final dexted regions were drawn using the draw__label_boxes.

## VideoPipeline

The video pipeline was implement in the the IN[11] of the jupyter notebook.

Based on the heatmap and detecting how many features are prenesnt helped in reducing the false positives. The putput video is
(https://github.com/mohsinkar/Vehicle-Detection/blob/master/project_video_output.mp4) project_video_output.mp4
