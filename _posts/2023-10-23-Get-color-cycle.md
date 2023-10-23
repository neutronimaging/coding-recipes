---
title: "Get current color cycle"
date: 2023-10-23
author:
- Anders Kaestner
---

In many plotting situations, it is needed to use the same color repeatedly for several plotting elements. This can be achieved by reading the ```plt.rcParams``` field of matplotlib.

## Example
```python
import numpy as np
import matplotlib.pyplot as plt

cycle = plt.rcParams['axes.prop_cycle'].by_key()['color']

x=np.linspace(0,2*np.pi,300)

for idx,i in enumerate([1,2,4,8]) :
    y=np.sin(i*x)
    plt.plot(x,y,color=cycle[idx])
    plt.fill_between(x,y1=0,y2=y,color=cycle[idx],alpha=0.1)
```

