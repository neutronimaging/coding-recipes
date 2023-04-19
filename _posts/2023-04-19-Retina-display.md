---
title: "Improve matplotlib sharpness on Apple Retina screens"
date: 2023-04-19 10:50
author:
- Anders Kaestner
---

Add the line 
```%config InlineBackend.figure_format = 'retina'```

In a notebook cell to improve the plot sharpness on screens with retina 
display. Other screens ignore the option.

