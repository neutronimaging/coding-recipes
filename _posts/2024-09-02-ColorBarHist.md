---
title: Plot a histogram in the color bar
author: Anders Kaestner
date: 2024-09-02 08:00:00
---

It can help to understand the color map distribution in an image if there is a histogram integrated in the colorbar.


```python
import matplotlib.pyplot as plt
import numpy as np

# Generate some data
np.random.seed(0)
data = np.random.randn(100, 100)
data[20:70,30:80]=data[20:70,30:80]+10

# Create the plot
fig, ax = plt.subplots(figsize=(5,6))
cax = ax.imshow(data, cmap='viridis')

# Add a color bar underneath the image
cbar = fig.colorbar(cax, ax=ax, orientation='horizontal', pad=0.08, aspect=10)  # Adjust aspect for width

# Calculate the histogram and its cumulative sum (integral histogram)
hist, bins = np.histogram(data, bins=30, density=True)
cumulative_hist = np.cumsum(hist * np.diff(bins))

# Plot the integral histogram along the color bar
cbar.ax.plot(bins[:-1], hist, color='red')
cbar.ax.set_xlabel('Distribution')

# Show the plot
plt.show()
```



