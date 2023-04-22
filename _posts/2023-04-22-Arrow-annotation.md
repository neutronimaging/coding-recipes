---
title: "Annotate plots with arrow labels"
date: 2023-04-22
author:
- Anders Kaestner
---

<img width="446" alt="Screenshot 2023-04-22 at 10 13 50" src="https://user-images.githubusercontent.com/11174364/233771992-39393dec-bcaa-4fdd-b17e-c41e50eb0eb9.png">

```
bbox_props = dict(boxstyle="larrow", fc=(0.8, 0.9, 0.9), ec="b", lw=2)
```
__boxstyle__ Describes the shape of the box. Can be boxes or arrows.  
__fc__ Face color.  
__ec__ Edge color.  
__lw__ Edge line width.  

```
t = axs[1].text(60, 10, "Text", ha="left", va="center", rotation=0,
            size=15,
            bbox=bbox_props)
```

