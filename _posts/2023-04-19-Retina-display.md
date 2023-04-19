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

## Before
<img width="498" alt="Default render backend" src="https://user-images.githubusercontent.com/11174364/233040453-0ff2918b-f024-4a61-8b25-963264ce98cc.png" style="width:500px"/>

## After
<img width="497" alt="Retina render backend" src="https://user-images.githubusercontent.com/11174364/233041322-167a292a-45f3-475f-9401-a5cb025e6c95.png" style="width:500px"/>
