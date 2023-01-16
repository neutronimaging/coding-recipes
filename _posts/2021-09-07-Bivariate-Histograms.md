---
title: Bivariate histograms
author: Anders Kaestner
date: 2021-09-07 15:20
tags: matplotlib python plotting histograms
---
Histograms are a great way to get an overview of the information distribution of an image. This notebook shows how to create bivariate histogram with and without logarithmic scaling.

What you need to produce this histogram is
![bivariate png](https://user-images.githubusercontent.com/11174364/212683994-408bbd30-80c3-418d-88b0-35f0b40c3e6d.png)

Two images (_n_ and _x_) and 
- the numpy functions ```histogram``` and ```histogram2d```:
```python
H, xedges, nedges = np.histogram2d(x.ravel(), n.ravel(), bins=nBins)
nH,nax = np.histogram(n.ravel(),bins=nedges)
xH,xax = np.histogram(x.ravel(),bins=xedges)
```
- the matplotlib function ```plot_surface``` imported using ```from mpl_toolkits.mplot3d import Axes3D```:
```python
X, Y = np.meshgrid(xedges[:-1], nedges[:-1])
fig = plt.figure(figsize=(12,10))
ax = fig.gca(projection = '3d')
hScale = 0.05
ax.plot(nedges[:-1], hScale*xH, zs=xedges.min(), zdir='x', lw = 2., color = 'coral')
ax.plot(xedges[:-1], hScale*nH, zs=nedges.max(), zdir='y', lw = 2., color = 'cornflowerblue')
cax=ax.plot_surface(X, Y, H, cmap='viridis')
fig.colorbar(cax,shrink=0.5)
ax.set_ylabel('X-rays');
ax.set_xlabel('Neutrons');
plt.show()
```

[<img src="https://upload.wikimedia.org/wikipedia/commons/3/38/Jupyter_logo.svg" height="50px"/>](https://nbviewer.jupyter.org/github/neutronimaging/coding-recipes/blob/main/python/HistgramRecipes.ipynb)
