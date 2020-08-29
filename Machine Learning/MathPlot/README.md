# Matplotlib

From <a href="https://matplotlib.org/tutorials/index.html#introductory" target="_blank">Matplotlib</a>

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

or plot style:
```python
x = np.linspace(0, 2, 100)

plt.plot(x, x, label='linear')  # Plot some data on the (implicit) axes.
plt.plot(x, x**2, label='quadratic')  # etc.
plt.plot(x, x**3, label='cubic')
plt.xlabel('x label')
plt.ylabel('y label')
plt.title("Simple Plot")
plt.legend()
```

***Better aproach***

Make a function to do all of this to all the graph that you need:

```python
def my_plotter(ax, data1, data2, param_dict):
    """
    A helper function to make a graph

    Parameters
    ----------
    ax : Axes
        The axes to draw to

    data1 : array
       The x data

    data2 : array
       The y data

    param_dict : dict
       Dictionary of kwargs to pass to ax.plot

    Returns
    -------
    out : list
        list of artists added
    """
    out = ax.plot(data1, data2, **param_dict)
    return out
```

Example:
```python
data1, data2, data3, data4 = np.random.randn(4, 100)
fig, ax = plt.subplots(1, 1)
my_plotter(ax, data1, data2, {'marker': 'x'})
```
![Graph6](https://github.com/rodoliva/Python-Studies/blob/master/Machine%20Learning/MathPlot/graph6.png?raw=true)

 sub-plots:
 
 ```python
fig, (ax1, ax2) = plt.subplots(1, 2)
my_plotter(ax1, data1, data2, {'marker': 'x'})
my_plotter(ax2, data3, data4, {'marker': 'o'})
```
![Graph7](https://github.com/rodoliva/Python-Studies/blob/master/Machine%20Learning/MathPlot/graph7.png?raw=true)

***Interactive view***

This will show immediately the figure:
 ```python
import matplotlib.pyplot as plt
plt.ion()
plt.plot([1.6, 2.7])
plt.title("interactive test")
plt.xlabel("index")
```
![Graph8](https://github.com/rodoliva/Python-Studies/blob/master/Machine%20Learning/MathPlot/graph8.png?raw=true)

***Non-Interactive view***

Every time you use the show method, the figure will appear:
 ```python
import numpy as np
import matplotlib.pyplot as plt

plt.ioff()
for i in range(3):
    plt.plot(np.random.rand(10))
    plt.show()
```
![Graph9](https://github.com/rodoliva/Python-Studies/blob/master/Machine%20Learning/MathPlot/graph9.png?raw=true)
![Graph10](https://github.com/rodoliva/Python-Studies/blob/master/Machine%20Learning/MathPlot/graph10.png?raw=true)
![Graph11](https://github.com/rodoliva/Python-Studies/blob/master/Machine%20Learning/MathPlot/graph11.png?raw=true)


***Samples***

 ```python
import numpy as np
import matplotlib.pyplot as plt

plt.plot([1, 2, 3, 4], [1, 4, 9, 16])
plt.plot([1, 2, 3, 4], [1, 4, 9, 16], 'ro')
plt.axis([0, 6, 0, 20])
```
![Graph12](https://github.com/rodoliva/Python-Studies/blob/master/Machine%20Learning/MathPlot/graph12.png?raw=true)

 ```python
import numpy as np

# evenly sampled time at 200ms intervals
t = np.arange(0., 5., 0.2)

# red dashes, blue squares and green triangles
plt.plot(t, t, 'r--', t, t**2, 'bs', t, t**3, 'g^')
plt.show()
```
![Graph13](https://github.com/rodoliva/Python-Studies/blob/master/Machine%20Learning/MathPlot/graph13.png?raw=true)

 ```python
data = {'a': np.arange(50),
        'c': np.random.randint(0, 50, 50),
        'd': np.random.randn(50)}
data['b'] = data['a'] + 10 * np.random.randn(50)
data['d'] = np.abs(data['d']) * 100

plt.scatter('a', 'b', c='c', s='d', data=data)
plt.xlabel('entry a')
plt.ylabel('entry b')
plt.show()
```
![Graph14](https://github.com/rodoliva/Python-Studies/blob/master/Machine%20Learning/MathPlot/graph14.png?raw=true)

 ```python
names = ['group_a', 'group_b', 'group_c']
values = [1, 10, 100]

plt.figure(figsize=(9, 3))

plt.subplot(131)
plt.bar(names, values)
plt.subplot(132)
plt.scatter(names, values)
plt.subplot(133)
plt.plot(names, values)
plt.suptitle('Categorical Plotting')
plt.show()
```
![Graph15](https://github.com/rodoliva/Python-Studies/blob/master/Machine%20Learning/MathPlot/graph15.png?raw=true)


 ```python
def f(t):
    return np.exp(-t) * np.cos(2*np.pi*t)

t1 = np.arange(0.0, 5.0, 0.1)
t2 = np.arange(0.0, 5.0, 0.02)

plt.figure()
plt.subplot(211)
plt.plot(t1, f(t1), 'bo', t2, f(t2), 'k')

plt.subplot(212)
plt.plot(t2, np.cos(2*np.pi*t2), 'r--')
plt.show()
```
![Graph16](https://github.com/rodoliva/Python-Studies/blob/master/Machine%20Learning/MathPlot/graph16.png?raw=true)


 ```python
mu, sigma = 100, 15
x = mu + sigma * np.random.randn(10000)

# the histogram of the data
n, bins, patches = plt.hist(x, 50, density=1, facecolor='g', alpha=0.75)


plt.xlabel('Smarts')
plt.ylabel('Probability')
plt.title('Histogram of IQ')
plt.text(60, .025, r'$\mu=100,\ \sigma=15$')
plt.axis([40, 160, 0, 0.03])
plt.grid(True)
plt.show()
```
![Graph17](https://github.com/rodoliva/Python-Studies/blob/master/Machine%20Learning/MathPlot/graph17.png?raw=true)


 ```python
ax = plt.subplot(111)

t = np.arange(0.0, 5.0, 0.01)
s = np.cos(2*np.pi*t)
line, = plt.plot(t, s, lw=2)

plt.annotate('local max', xy=(2, 1), xytext=(3, 1.5),
             arrowprops=dict(facecolor='black', shrink=0.05),
             )

plt.ylim(-2, 2)
plt.show()
```
![Graph18](https://github.com/rodoliva/Python-Studies/blob/master/Machine%20Learning/MathPlot/graph18.png?raw=true)


 ```python
# Fixing random state for reproducibility
np.random.seed(19680801)

# make up some data in the open interval (0, 1)
y = np.random.normal(loc=0.5, scale=0.4, size=1000)
y = y[(y > 0) & (y < 1)]
y.sort()
x = np.arange(len(y))

# plot with various axes scales
plt.figure()

# linear
plt.subplot(221)
plt.plot(x, y)
plt.yscale('linear')
plt.title('linear')
plt.grid(True)

# log
plt.subplot(222)
plt.plot(x, y)
plt.yscale('log')
plt.title('log')
plt.grid(True)

# symmetric log
plt.subplot(223)
plt.plot(x, y - y.mean())
plt.yscale('symlog', linthresh=0.01)
plt.title('symlog')
plt.grid(True)

# logit
plt.subplot(224)
plt.plot(x, y)
plt.yscale('logit')
plt.title('logit')
plt.grid(True)
# Adjust the subplot layout, because the logit one may take more space
# than usual, due to y-tick labels like "1 - 10^{-3}"
plt.subplots_adjust(top=0.92, bottom=0.08, left=0.10, right=0.95, hspace=0.25,
                    wspace=0.35)

plt.show()
```
![Graph19](https://github.com/rodoliva/Python-Studies/blob/master/Machine%20Learning/MathPlot/graph19.png?raw=true)


## Other Samples

From <a href="https://matplotlib.org/tutorials/introductory/sample_plots.html#sphx-glr-tutorials-introductory-sample-plots-py" target="_blank">Samples</a>

## Images Tutorial

From <a href="https://matplotlib.org/tutorials/introductory/images.html#sphx-glr-tutorials-introductory-images-py" target="_blank">Images</a>

## The Lifecycle of a Plot

From <a href="https://matplotlib.org/tutorials/introductory/lifecycle.html#sphx-glr-tutorials-introductory-lifecycle-py" target="_blank">Cycles</a>
