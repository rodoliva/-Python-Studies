# NumPy

---
**Importing Data**

```python
import numpy as np
```

**Functions & Methods**

```python
a=np.array([1,2,3,4,5]) # Array
a[0] # index 0 (ex:1)
type(a) # type
a.dtype # data type
a.size # elements in the array
a.ndim # number of array dimension
a.shape # size of the array in each dimension
d=a[1:4] " slicing array from 1 to 4 (from the index 0,1,2,3,4,5 the slice=1,2,3)
ones = np.ones((1,2)) # Result in an array with one dimension with 1 as a value array([[1.,1.]])
Zeros = np.zeros((1,2)) # Result in an array with one dimension with 0 as a value array([[0.,0.]])
range_array = np.arange(0,10,2) # start at 0 end at 10, step 2, resulting array([0, 2, 4, 6, 8])
random_array = np.random.randint(0, 10, size=(3,5)) # lowest 0, highest 10, size 3x5 (3 rows, 5 colummns), resulting array([[4, 7, 8, 6, 8],[8, 2, 9, 3, 1],[5, 6, 3, 3, 2]])
np.random.random((5,3)) # random array between 0 to 1 with a 5,3 size
np.random.seed(seed=5) # every time that a random function run, the result will be the same, it will choose the seed 5
np.unique(random_array) # show unique elements

```

**Operations**

```python
# vector operations zip
u = [1,0]
v = [0,1]
z = []
from n, m in zip(u,v):
  z.append(n+m)
  
# vector operations np array
u = np.array([1,0])
v = np.array([0,1])
z = u+v # z: np.array

# vector scalar
u = np.array([1,0])
c = 2*u

# product
u = np.array([1,0])
v = np.array([0,1])
z=u*v

# dot product (mult first part vector + mult second part vector)
u = np.array([1,2])
v = np.array([3,1])
z=np.dot(u,v)= 1*3 + 2*1 = 5

# broadcasting
u = np.array([1,2,3,-1])
z = u + 1 = array([1+1, 2+1, 3+1, -1+1]) = array([2,3,4,0])

# universal functions
a = np.array([1,-1,1,-1])
b = a.mean() = 0
c = a.max() = 1
d = np.pi
e = np.sin(x)
f = np.std() # standard deviation

# mathematical plotting
np.linsspace(-2,2,num=5) = np.array([-2,-1,0,1,2]) #-2 start, 2 end, 5 number of samples

```

**2D Arrays**

```python
a = [[11,12,13],[21,22,23],[31,32,33]]
a.ndim #dimension (2)
a.shape # array size and nest size (3,3)
a.size # normal size of the array (9)
a[x][y] = a[x,y] # select x row and y column
a[0,0:2] # slicing ([11,12])
+ - * / # matrix operation
2 * a # multipli every item by 2

# matrix multiplication x columns must be equal to y rows
x = [[11,12,13],[21,22,23]]
y = [[45,46],[55,56],[65,66]]
z = [[11*45+12*55+13*65,11*46+12*56+13*66],[21*45+22*55+23*65,21*46+22*56+23*66]]

x_new=np.array(x)
y_new=np.array(y)
z_new=np.dot(x_new,y_new)



```
