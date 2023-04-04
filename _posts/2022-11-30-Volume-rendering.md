---
title: "Volume rendering using PyVista"
date: 2022-11-30 20:19
author:
- Anders Kaestner
---
The package [PyVista](https://docs.pyvista.org) offers many possibilties to visualize volume data.
You can for example produce movies like this using different file formats:
![OrthoMovie](https://github.com/neutronimaging/coding-recipes/blob/main/python/orbit.gif)

You need to install the following packages before starting.
```bash 
conda install -c conda-forge pyvista
conda install -c conda-forge imageio-ffmpeg
```

The detailed example is provided in this jupyter notebook 

<a href="https://github.com/neutronimaging/coding-recipes/blob/main/python/PyVistaDemos.ipynb"><img src="https://upload.wikimedia.org/wikipedia/commons/3/38/Jupyter_logo.svg" height="30px"/></a>


You need to download the data set [_legorecon.tif_](https://github.com/neutronimaging/coding-recipes/blob/main/python/legorecon.tif) to use the notebook.

