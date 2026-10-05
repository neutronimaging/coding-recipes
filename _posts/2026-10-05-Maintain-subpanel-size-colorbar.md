---
title: Maintain the subplot size when colorbar is shown
author: Anders Kaestner
date: 2026-10-05 02:00:00
---

It is important to add colorbar to your figures to show the duynamic range of the image colormap. 
```python
import numpy as np
import matplotlib.pyplot as plt

fig, axes = plt.subplots(1, 3,figsize=(12,4))
vmin = -2
vmax = 2

for ax in axes:
    im=np.random.normal(size=[100,100])
    a=ax.imshow(im, vmin=vmin, vmax=vmax, cmap='Blues')

cbar = fig.colorbar(a, ax=axes[-1], ticks=np.linspace(vmin,vmax,5))
```

<img width="982" height="341" alt="Unknown" src="https://github.com/user-attachments/assets/08d2363c-a2a5-4196-99a9-3ba8d300f7fa" />

This issue is fixed when you use the ```inset_locator```
```python
import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.axes_grid1 import inset_locator

fig, axes = plt.subplots(1, 3,figsize=(12,4))
vmin = -2
vmax = 2

for ax in axes:
    im=np.random.normal(size=[100,100])
    a=ax.imshow(im, vmin=vmin, vmax=vmax, cmap='Blues')

axins = inset_locator.inset_axes(
    axes[-1],
    width="7.5%",   # width: 7.5% of parent_bbox width
    height="100%",  # height: 100%
    loc="lower left",
    bbox_to_anchor=(1.05, 0., 1, 1),
    bbox_transform=axes[-1].transAxes,
    borderpad=0,
)
cbar = fig.colorbar(a, cax=axins, ticks=np.linspace(vmin,vmax,5))
cbar.ax.tick_params(labelsize=8)
```

<img width="1037" height="321" alt="Unknown-1" src="https://github.com/user-attachments/assets/79d31055-afe9-46b7-b907-c5202888b4df" />
