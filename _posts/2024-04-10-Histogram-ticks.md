---
title: Centered histogram ticks
author: Anders Kaestner
date: 2024-04-10 08:00:00
---

When plotting a histogram, the ticks on the x-axis are usually placed at the left edge of the histogram bars. This can be changed by using the `align` argument in the `plt.bar` function.

The `align="center"` argument centers the histogram ticks on the x-axis. 

```python
import numpy as np
import matplotlib.pyplot as plt

data = np.random.normal(0, 1, 1000)
hb,ha = np.histogram(data,bins=np.arange(-5,5))

plt.bar(ha[:-1],hb ,align="center")
plt.xlabel('Number of connected edges')
plt.ylabel('Number of nodes')
```

