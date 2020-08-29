# Matplotlib

From <a href="https://matplotlib.org/" target="_blank">Matplotlib</a>

---

**Simple graph**
```python
import matplotlib.pyplot as plt
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

- Axes: This is what you think of as 'a plot', it is the region of the image with the data space. A given figure can contain many Axes. The Axes contains two (or three in the case of 3D) Axis objects.

- Axis: These are the number-line-like objects. 

- Artist: Basically everything you can see on the figure is an artist (even the Figure, Axes, and Axis objects)

```python
fig = plt.figure()  # an empty figure with no Axes
fig, ax = plt.subplots()  # a figure with a single Axes
fig, axs = plt.subplots(2, 2)  # a figure with a 2x2 grid of Axes
```
![Graph3](https://github.com/rodoliva/Python-Studies/blob/master/Machine%20Learning/MathPlot/graph3.png?raw=true)
![Graph4](https://github.com/rodoliva/Python-Studies/blob/master/Machine%20Learning/MathPlot/graph4.png?raw=true)


**Types of inputs to plotting functions***
All of plotting functions expect numpy.array or numpy.ma.masked_array as input. Classes that are 'array-like' such as pandas data objects and numpy.matrix may or may not work as intended. It is best to convert these to numpy.array objects prior to plotting.

Convert to pandas:
```python
import pandas
import numpy as np
a = pandas.DataFrame(np.random.rand(4, 5), columns = list('abcde'))
a_asarray = a.values
```

Convert to numpy:
```python
b = np.matrix([[1, 2], [3, 4]])
b_asarray = np.asarray(b)
```

***The object-oriented interface and the pyplot interface***
As noted above, there are essentially two ways to use Matplotlib:

Explicitly create figures and axes, and call methods on them (the "object-oriented (OO) style").
Rely on pyplot to automatically create and manage the figures and axes, and use pyplot functions for plotting.
So one can do (OO-style)

```python
x = np.linspace(0, 2, 100)

# Note that even in the OO-style, we use `.pyplot.figure` to create the figure.
fig, ax = plt.subplots()  # Create a figure and an axes.
ax.plot(x, x, label='linear')  # Plot some data on the axes.
ax.plot(x, x**2, label='quadratic')  # Plot more data on the axes...
ax.plot(x, x**3, label='cubic')  # ... and some more.
ax.set_xlabel('x label')  # Add an x-label to the axes.
ax.set_ylabel('y label')  # Add a y-label to the axes.
ax.set_title("Simple Plot")  # Add a title to the axes.
ax.legend()  # Add a legend.
```
![Graph5](https://github.com/rodoliva/Python-Studies/blob/master/Machine%20Learning/MathPlot/graph5.png?raw=true)
