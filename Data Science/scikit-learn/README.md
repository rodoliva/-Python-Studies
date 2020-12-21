# scikit-learn

From <a href="https://scikit-learn.org/stable/" target="_blank">scikit-lear</a>

---
**Importing Data**
```python
import sklearn.linear_model
```

**Linear Regression**
```python
from sklearn.linear_model import LinearRegression
lm = LinearRegression() # Constructor
x = def['indep'] # pandas data frame with independant variable or predictor
y = def['dep'] # pandas data frame with dependant variable or target
lm.fit(x,y) # fit the model to fine parameters
yhta=lm.predinct(x) # arrays prediction
y = b0 + b1 * x # formula b0: interceptor b1: slope
lm.intercept_ # return interceptor
lm.coef_ # return slope
```
