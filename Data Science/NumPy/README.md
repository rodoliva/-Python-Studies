# NumPy

---
**Importing Data**
```python
import numpy as np

```
**Functions & Methods**

```python
a=np.arrat([1,2,3,4,5]) # Array
a[0] # index 0 (ex:1)
type(a) # type
a.dtype # data type
a.size # elements in the array
a.ndim # number of array dimension
a.shape # size of the array in each dimension
d=a[1:4] " slicing array from 1 to 4 (from the index 0,1,2,3,4,5 the slice=1,2,3)
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
z=np.dor(u,v)= 1*3 + 2*1 = 5

# broadcasting
u = np.array([1,2,3,-1])
z = u + 1 = array([1+1, 2+1, 3+1, -1+1]) = array([2,3,4,0])

# universal functions
a = np.array([1,-1,1,-1])
b = a.mean() = 0
c = a.max() = 1
d = np.pi
e = np.sin(x)

# mathematical plotting
np.linsspace(-2,2,num=5) = np.array([-2,-1,0,1,2]) #-2 start, 2 end, 5 number of samples

```
