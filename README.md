# Retina-Vision
Hybrid object detection algorithm that integrates RetinaNet and Google Vision

Object Detection with RetinaNet and Google Vision API
This repository contains code for enhancing object detection performance by integrating the RetinaNet model with the Google Vision API. The system detects objects using RetinaNet, saves low-confidence detections as individual images, and re-evaluates these images using Google Vision for improved accuracy.

Setup

Usage
Running the Script
Ensure your dataset JSON file and images are in the correct directories.
Modify the paths to your dataset and images in the script:
  json_path = r"path_to_your_dataset/Dataset.json"
  images_directory = r"path_to_your_images_directory/"
You won't have to extract the COCO images from the Json Dataset as they are already saved in the image folder

Run the script:
  python main.py
  
Script Overview
The script performs the following tasks:
  Loads the COCO dataset and initializes the RetinaNet model.
  Processes each image in the dataset to detect objects using RetinaNet.
  Saves low-confidence detections as individual images.
  Uses Google Vision API to re-evaluate low-confidence detections.
  Compares the detection results with ground truth annotations.
  Calculates and prints the detection accuracy.
  Plots the bounding boxes for visualization.
  Modifiable Variables
  
You can adjust the following variables in the script to tune the performance:

  score_threshold: Confidence level threshold for considering a detected object valid.
  score_threshold = 0.4  # Default: 0.4

  low_score_threshold: Confidence level threshold below which detected objects are re-evaluated using Google Vision.
  low_score_threshold = 0.6  # Default: 0.6 (if < 0,05 Google Vision won't be used)
  
  iou_threshold: Intersection over Union (IoU) threshold for determining correct detections.
  iou_threshold = 0.7  # Default: 0.7
  
Output
The script will output detection accuracy for each image and overall statistics, including:
  Percentage of detected ground truths
  Total percentage of correctly labeled bounding boxes
        
Contributing
Feel free to submit issues or pull requests if you find any bugs or have suggestions for improvements.
