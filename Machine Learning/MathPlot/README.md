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

```python
fig = plt.figure()  # an empty figure with no Axes
fig, ax = plt.subplots()  # a figure with a single Axes
fig, axs = plt.subplots(2, 2)  # a figure with a 2x2 grid of Axes
```
![Graph3](https://github.com/rodoliva/Python-Studies/blob/master/Machine%20Learning/MathPlot/graph3.png?raw=true)
![Graph4](https://github.com/rodoliva/Python-Studies/blob/master/Machine%20Learning/MathPlot/graph4.png?raw=true)
