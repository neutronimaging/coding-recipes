---
title: Logarithmic colormaps
author: Anders Kaestner
date: 2021-09-07 15:42
tags: matplotlib python imshow logarithmic
---

In some cases it makes sense to use logarithic color coding to visualize your data. This can be done by just computing the logartihm of the image. The problem with this approach is that you have to rescale the color bar and its ticks as well.

The scaling problems can easily be avoided by using the norn argument in ```imshow()``` with the ```LogNorm()``` function from the matplotlib.colors module.
```python
import numpy as np
import matplotlib.pyplot as
from matplotlib.colors import LogNorm

img = <some image>

plt.imgshow(img,norm=LogNorm())
plt.colorbar()
```
