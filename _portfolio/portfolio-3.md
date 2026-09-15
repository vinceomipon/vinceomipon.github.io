---
title: "Electroluminescence Script"
excerpt: "A Python script that determines the healthiness of a solar panel through electroluminescence<br/><img src='/images/elm.png'>"
collection: portfolio
---

![Segmentations and Original Image](http://localhost:4000/images/elm.png)

The ELM script is an image-processing pipeline that measures the electroluminescence (ELM) coverage on the CubeSat solar panels. This is determined by calculating the ratio of the panel area that lights up (healthy) when a voltage is applied across the panel, and the total panel area. The percentage calculated although approximate, is a good indicator of how healthy a solar panel is. This ratio can determine whether or not the solar panel should be integrated into the final prototype to launch into space.

The gist of the workflow:

1. Photograph of an active solar panel in a dark room
2. Segment the illuminated cells of the solar panel using 2 K means clustering
3. Segment the total solar panel using value segmentation and morphological operations
4. Calculate the ratio using the following formula
    $$
        f(x) = \int_{-\infty}^{\infty} e^{-x^2} dx
    $$