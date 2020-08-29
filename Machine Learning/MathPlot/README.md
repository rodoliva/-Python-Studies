# Matplotlib

From <a href="https://matplotlib.org/" target="_blank">Matplotlib</a>

---

**Simple graph**
```python
import matplotlib.pyplot as plt
import numpy as np
fig, ax = plt.subplots()  # Create a figure containing a single axes.
ax.plot([1, 2, 3, 4], [1, 4, 2, 3])  # Plot some data on the axes.
```
![Graph1](https://raw.githubusercontent.com/rodoliva/Python-Studies/master/Machine%20Learning/MathPlot/graph1.png)

The same graph in short version:
```python
import matplotlib.pyplot as plt
plt.plot([1, 2, 3, 4], [1, 4, 2, 3])  # Matplotlib plot.
```

**Parts of a Figure**
![Graph2](https://github.com/rodoliva/Python-Studies/blob/master/Machine%20Learning/MathPlot/graph2.png?raw=true)

Axes: This is what you think of as 'a plot', it is the region of the image with the data space. A given figure can contain many Axes, but a given Axes object can only be in one Figure. The Axes contains two (or three in the case of 3D) Axis objects (be aware of the difference between Axes and Axis) which take care of the data limits (the data limits can also be controlled via the axes.Axes.set_xlim() and axes.Axes.set_ylim() methods). Each Axes has a title (set via set_title()), an x-label (set via set_xlabel()), and a y-label set via set_ylabel()).
The Axes class and its member functions are the primary entry point to working with the OO interface.

Axis: These are the number-line-like objects. 

Artist: Basically everything you can see on the figure is an artist (even the Figure, Axes, and Axis objects)

```python
fig = plt.figure()  # an empty figure with no Axes
fig, ax = plt.subplots()  # a figure with a single Axes
fig, axs = plt.subplots(2, 2)  # a figure with a 2x2 grid of Axes
```
![Graph3](https://github.com/rodoliva/Python-Studies/blob/master/Machine%20Learning/MathPlot/graph3.png?raw=true)
![Graph4](https://github.com/rodoliva/Python-Studies/blob/master/Machine%20Learning/MathPlot/graph4.png?raw=true)
