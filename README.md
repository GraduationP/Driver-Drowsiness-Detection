# Driver Drowsiness Detection

Driver Drowsiness Detection is a Python project that utilizes computer vision and machine learning techniques to monitor a driver's eye status and detect drowsiness or blinking. It can be integrated into in-vehicle systems or used as a standalone application to enhance road safety.

## Features

- Real-time detection of driver blinks and drowsiness.
- Calculation of the eye aspect ratio for assessing eye openness.
- Alerts and warnings to prevent potential accidents.
- Easy integration with existing vehicle systems.

## Prerequisites

Before you get started, ensure that you have the following prerequisites in place:

- Python 3.x
- OpenCV
- dlib
- Your specific dependencies

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

