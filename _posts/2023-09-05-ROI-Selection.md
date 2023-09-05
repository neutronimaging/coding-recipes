---
title: "Select ROIs in a matplotlib figure"
date: 2023-09-05
author:
- Anders Kaestner
---

It is often good to be able to select a ROI in a figure for using in the next calculations. Matplotlib offers this ability in the widgets section. 

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






