---
title: "Adding error bands to a scatter plot"
date: 2022-05-28 09:36
author:
- Anders Kaestner
---

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/neutronimaging/coding-recipes/blob/main/python/ErrorBands.ipynb) <a href="[https://github.com/ImagingLectures/Quantitative-Big-Imaging-2022/blob/main/Lectures/Lecture-02/02-Datasets.ipynb](https://github.com/neutronimaging/coding-recipes/blob/main/python/ErrorBands.ipynb)"><img src="https://upload.wikimedia.org/wikipedia/commons/3/38/Jupyter_logo.svg" height="30px"/></a>

Error bands is often easier to interpret than a cluttered scatter plot. Here is an example how to create the error bands using ```numpy.convolve()``` for the moving average and standard devivation which are needed to display the bands. The error bands are plotted using ```matplotlib.pyplot.fillbetween()```.

In the example we start with a plot looking like this. 

![noisydata](https://user-images.githubusercontent.com/11174364/170815792-8fb6e086-6d93-4b22-93f2-56d9ae58fee4.png)

And end with this result. 

![errorbands](https://user-images.githubusercontent.com/11174364/170815793-82a2d55e-dc7e-4e1c-839a-8340fff51d0b.png)



