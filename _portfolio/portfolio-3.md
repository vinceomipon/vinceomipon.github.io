---
title: "Electroluminescence Script"
excerpt: "A Python script that determines the healthiness of a solar panel through electroluminescence<br/><img src='/images/elm.png'>"
collection: portfolio
---

![Segmentations and Original Image](http://localhost:4000/images/elm.png)

The ELM script is an image-processing pipeline that measures the electroluminescence (ELM) coverage on the CubeSat solar panels. This is determined by calculating the ratio of the panel area that lights up (healthy) when a voltage is applied across the panel, and the total panel area. The percentage calculated although approximate, is a good indicator of how healthy a solar panel is. This ratio can determine whether or not the solar panel should be integrated into the final prototype to launch into space.

## Workflow Overview

1. Photograph of an active solar panel in a dark room
2. Convert the image from .heic to .png for OpenCV processing
3. Segment the illuminated cells of the solar panel using 2 K means clustering in the BGR space.
4. Segment the total solar panel using value segmentation and morphological operations in the HSV space.
5. Calculate the effective coverage ratio using the formula:

$$
    \text{Effective Coverage (\%)} = \left( \frac{\Sigma \text{Illuminated Pixels}}{\Sigma \text{Panel Pixels}}\right) \cdot 100
$$

The K-Means algorithm is common among many image processing applications. The algorithm helps with segmenting the panel into illuminated and not, clearly differentiating between the two to create a binary mask. However, the algorithm was unhelpful when attempting to segment the solar panel as shown below.

<img src="http://localhost:4000/images/3k_means.png" alt="Segmentations and Original Image" width="300" style="display: block; margin-left: auto; margin-right: auto;"/>

One possible reason for this issue is that when performing kmeans in the value space of an hsv image, some pixels will exhibit colours away from the mean color of the panel and thus not be included. This is shown in the hsv histogram below.

<img src="http://localhost:4000/images/hsv_hist_IMG_6609.png" alt="HSV Histogram plot" style="display: block; margin-left: auto; margin-right: auto;"/>

As shown in the value histogram above, the pixels in the panel exhibit colors around the range of [0,25] and [200,255]. Therefore, k means would not help and thus color thresholding along with morphological operations was instead used to segment the panel.

## Conclusion
Overall this project helped expand my knowledge of python programming using many different libraries and packages such as `OpenCV`, `NumPy`, `Matplotlib`, and `Pathlib`. This project was developed on `Visual Studio Code` with `git` version control.

Here is a video link to the [demo](https://youtu.be/1Gy6AkZf6DE)