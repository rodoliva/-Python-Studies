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

