---
title: "Define and use a soil and water colormap"
date: 2023-03-29 07:50
author:
- Anders Kaestner
---


Define the colormap generating function
```python
def soilwater(N=100) :
    clst=np.zeros([N,3])
    clst[:,0]=np.linspace(1,0,N) # red
    clst[:,2]=np.linspace(0,1,N) # blue
    clst[:,1]=0.5*(clst[:,0]+clst[:,2]) # green
    cmap = colors.ListedColormap(clst)

    return cmap
```
