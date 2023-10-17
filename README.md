# Driver Drowsiness Detection

## Overview

Driver Drowsiness Detection is a computer vision project that uses machine learning to detect and count the blinks of a car driver. It also provides warnings if the driver appears to be falling asleep or has fainted while driving. This project aims to enhance road safety by preventing accidents caused by drowsy or inattentive drivers.

## Features

- Real-time detection of driver blinks using computer vision techniques.
- Monitoring of the driver's eye movements and alerting if drowsiness is detected.
- Warning notifications to prevent potential accidents.

## Technologies Used

Before you get started with this project, make sure you have the following prerequisites:

- Python 3.x
- OpenCV
- dlib
- numpy
- scipy
- playsound

## How It Works

The project consists of the following key functions:

### Blink Counter Function

The `Blink Counter Function` is responsible for detecting the number of blinks in a minute to determine if the driver is getting drowsy. It operates as follows:

1. Calculates the vertical length by measuring the distance between the `leftUp` and `leftDown` points on the driver's face.
2. Calculates the horizontal length by measuring the distance between the `leftLeft` and `leftRight` points on the driver's face.
3. Computes the ratio of the vertical length to the horizontal length.
4. If the ratio changes (indicating a blink), it increases the blink count.

### Eye Aspect Ratio Function

The `eye_aspect_ratio` function calculates the aspect ratio of an eye based on the distances between the pupil center and the corneal reflection point. It takes an `eye` structure as input and returns the aspect ratio as output.

### Get Landmarks Function

The `getLandmarks` function detects faces in an image and extracts facial landmarks, which are essential for eye status assessment.

### Check Eye Status Function

The `checkEyeStatus` function checks the eye status based on the extracted landmarks. It follows these steps:

1. Creates a binary mask to define the region of interest around the eyes.
2. Computes the aspect ratio of both eyes using the `eye_aspect_ratio` function.
3. Determines the eye status based on an aspect ratio threshold.

Here is the code explanation formatted for a README file:

# Blink Detection and Drowsiness Alert System

This program uses computer vision and face detection to monitor a user's blink rate and alert them if signs of drowsiness are detected.

## How it Works

The main steps are:

### 1. Video Capture
A VideoCapture object is used to continuously capture frames from a camera source. 

### 2. Pre-processing
Each frame is resized for faster processing. Histogram equalization enhances the image for face detection.

### 3. Face and Eye Detection
getLandmarks() detects facial landmarks using a pre-trained model. The eye regions are indexed.

### 4. Blink Analysis  
checkEyeStatus() analyzes eye closure. checkBlinkStatus() checks for signs of drowsiness over consecutive frames.

### 5. Alerts
If drowsy, an alert message is drawn. Otherwise the blink count is displayed.

### 6. Output  
The processed frames are displayed, saved to an output video file.

### 7. Controls
'r' resets the alert. Esc exits. Exceptions are printed for debugging.

## Implementation
The main logic runs in a loop continuously capturing, processing and displaying frames in real-time. Computer vision and drowsiness detection algorithms are used to monitor the user.

## Usage
Run the Python file and the program will start monitoring via your webcam. It will alert if signs of drowsiness are detected to ensure user safety.

This provides a basic overview of how the blink detection and drowsiness alerting system works for documentation or README purposes. Let me know if any part needs more explanation!
