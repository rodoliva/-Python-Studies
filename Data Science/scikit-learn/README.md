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
y = b0 + b1*x # formula b0: interceptor b1: slope
lm.intercept_ # return interceptor
lm.coef_ # return slope
```

**Multiple Linear Regression**
```python
z = df[['x1','x2','x3','x4']] # pandas data frame with the columns names eg: x1="age"
lm.fot(z, y)
yhta=lm.predinct(x) # arrays prediction
y = b0 + b1*x1 + b2*x2 + b3*x3 + b4*x3 # formula b0: interceptor b1: slope
lm.intercept_ # return interceptor array([b1,b2,b3,b4])
lm.coef_ # return slope
```

**Evaluation: Mean Squared Error (MSE)**
```python
from sklearn.metrics import mean_squared_error
mean_squared_error(df["target"], "prediction") # actual value of target variable and the predicted value of target variable
```

**Testing**
```python
from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test = train_test_split(x_data, y_data, test_size=0.3, random_state=0) # x independent variable, y target, random is a number generator used for random sampling
```

**Cross Validation**
```python
from sklearn.model_selection import cross_val_score
scores = cross_val_score(lr, x_data, y_data, cv=3) # lr model type object (lineal regression), cv partitions
np.mean(scores) # average r square for each sample

from sklearn.model_selection import cross_val_predict
yhat = cross_val_predict(lr2e, x_data, y_data, cv=3) # yhat prediction
```
