# Implementation-of-Linear-Regression-Using-Gradient-Descent

## AIM:
To write a program to predict the profit of a city using the linear regression model with gradient descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
```
STEP 1. Start the program.

STEP 2. Import the required library and read the dataframe.

STEP 3. Write a function computeCost to generate the cost function.

STEP 4. Perform iterations og gradient steps with learning rate.

STEP 5. Plot the Cost function using Gradient Descent and generate the required graph.

STEP 6.End the Program.
```

## Program:
```
Program to implement the linear regression using gradient descent.
Developed by: PRAVEENA N
RegisterNumber: 212222040122
```
```
import numpy as np
import pandas as pd
from sklearn.preprocessing import StandardScaler
def linear_regression(X1,y,learning_rate=0.1,num_iters=1000):
    X=np.c_[np.ones(len(X1)),X1]
    theta=np.zeros(X.shape[1]).reshape(-1,1)
    for _ in range(num_iters):
        predictions=(X).dot(theta).reshape(-1,1)
        errors=(predictions-y).reshape(-1,1)
        theta-=learning_rate*(1/len(X1))*X.T.dot(errors)
    return theta
```
```
data=pd.read_csv("C:/Users/SEC/Documents/50_Startups.csv",header=None)
data.head()
```
```
X=(data.iloc[1:,:-2].values)
X1=X.astype(float)
```
```
scaler=StandardScaler()
y=(data.iloc[1:,-1].values).reshape(-1,1)
X1_Scaled=scaler.fit_transform(X1)
Y1_Scaled=scaler.fit_transform(y)
print(X)
print(X1_Scaled)
```
```
theta=linear_regression(X1_Scaled,Y1_Scaled)
new_data=np.array([165349.2,136897.8,471784.1]).reshape(-1,1)
new_Scaled=scaler.fit_transform(new_data)
prediction=np.dot(np.append(1,new_Scaled),theta)
prediction=prediction.reshape(-1,1)
pre=scaler.inverse_transform(prediction)
print(prediction)
print(f"Predicted value: {pre}")
```

## Output:
![image](https://github.com/Praveenanagaraji22/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119393514/24a49de2-07c5-4a3b-b1d7-21c83d451c18)

## Result:
Thus the program to implement the linear regression using gradient descent is written and verified using python programming.
