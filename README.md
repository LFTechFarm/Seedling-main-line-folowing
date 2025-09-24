# Seedling Main Line Following

This project was developed for the **FIRA 25 Hackathon** by the **Farmagedon team**. It provides a vision-based solution to help a robot navigate accurately within crop rows by detecting the main (central) line and guiding fine steering adjustments.

---

## Overview

The goal of this code is to assist a robot in **making precise corrections while moving along crop rows**, ensuring it stays centered and follows the row smoothly. The approach aims to align the image central line with the detected line. 

---

## Main Steps

1. **Preprocess the Image:** Crop the image and convert it to a suitable color space to enhance relevant features.  
2. **Generate a Mask:** Highlight the line or path regions based on visual characteristics such as color or intensity.  
3. **Compute a 1D Projection:** Reduce the mask to a horizontal profile by summing along the vertical axis, optionally weighting lower rows more to prioritize nearby corrections.  
4. **Detect the Line Position:** Identify the most prominent peak in the projection to determine the line’s current position relative to the robot.  
5. **Output for Control: To_Do** Use the detected position to compute fine steering adjustments to keep the robot centered in the row, optionally visualizing the line for debugging.

---
## Example Results

Below is an example of the pipeline detecting the line for fine navigation within a crop row:

<img width="1989" height="390" alt="row_detection" src="https://github.com/user-attachments/assets/bd5fc0ad-5d5b-42b4-b618-e4ffbbd0ae95" />


---

## Features

- Adjustable **crop ratio** to focus on the most relevant part of the image near the robot.  
- Optional **row weighting** to emphasize features closer to the robot.  
- Multiple **peak detection strategies**: `highest`, `prominent`, or `central`.  
- **Buffer accumulation** to smooth projections over multiple frames, reducing noise.  
- Visualization pipeline for debugging: original image, mask, projection, and detected line.

---

## Requirements

- Python 3.x  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  
- SciPy  





