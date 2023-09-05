---
title: "Select ROIs in a matplotlib figure"
date: 2023-09-05
author:
- Anders Kaestner
---

It is often good to be able to select a ROI in a figure for using in the next calculations. Matplotlib offers this ability in the widgets section. 
<img width="398" alt="Screenshot 2023-09-05 at 11 23 59" src="https://github.com/neutronimaging/coding-recipes/assets/11174364/a47e864f-2099-4fac-bccb-738688c26b78">

You need to 
- import the selector
- implement a callback function for the mouse actions
- connect the selector with the plot axis you want to use

It is also important to set the matplotlib output to notebook.
```
%matplotlib notebook
```
the interaction will not work otherwise.

The following notebook is inspired by the [matplotlib documentation example](https://matplotlib.org/stable/gallery/widgets/rectangle_selector.html)

<a href="https://github.com/neutronimaging/coding-recipes/blob/main/python/ROISelection.ipynb"><img src="https://upload.wikimedia.org/wikipedia/commons/3/38/Jupyter_logo.svg" height="30px"/></a>




