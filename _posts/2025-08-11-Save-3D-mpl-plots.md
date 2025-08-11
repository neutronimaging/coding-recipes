---
title: Save vector figures made with 3D view
author: Anders Kaestner
date: 2025-08-11 02:00:00
---

The 3D plotting engine for matplotlib can not save figures in vector format. A workaround is to generate a tikz figure for latex and compile the latex wrapper.

```python
import matplotlib
matplotlib.use("pgf")
matplotlib.rcParams.update({
    "pgf.texsystem": "pdflatex",
    "pgf.preamble": r"\usepackage{amsmath}",
})

import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D

fig = plt.figure()
ax = fig.add_subplot(111, projection="3d")

# Plot a helix along the x-axis
theta_max = 8 * np.pi
theta = np.linspace(0, theta_max, n)
x = theta
z = np.sin(theta)
y = np.cos(theta)
ax.plot(x, y, z, "b", lw=2)

# Remove axis planes, ticks and labels
ax.set_axis_off()

plt.savefig("plot.pgf")
```

The generated '.pgf'-file is then imported in a latex file like.

```latex
\documentclass[border=1pt]{standalone}
\usepackage{pgf}
\usepackage{amsmath}
\begin{document}
\input{plot.pgf}
\end{document}
```
Here, saved as 'wrapper.tex

Run pdflatex 
```bash
pdflatex trapper.tex
```

This should produce a _wrapper.pdf_ file with the plot.
