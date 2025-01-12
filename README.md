# Implementation-of-Linear-Regression-Using-Gradient-Descent

## AIM:
To write a program to predict the profit of a city using the linear regression model with gradient descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. reprocess Data: Normalize the input data X (cities' data points).
2.Initialize Variables: Set initial values for m (slope) and b (intercept). 
3. Set Learning Rate: Define the learning rate for gradient descent (e.g., 0.01).
4. Gradient Descent Loop: Update m and b iteratively by adjusting them using the gradient descent algorithm over 1000 iterations.
5.redict Profit: Once the gradient descent converges, use the optimized values of m and b to predict the profit for the city.
## Program:
```
/*
Program to implement the linear regression using gradient descent.
Developed by: Naneshvaran
RegisterNumber: 24900972/212224110038 
*/
import numpy as np
import pandas as pd
from sklearn.preprocessing import StandardScaler
def linear_regression(X1,y,learning_rate=0.01,num_iters=1000):
    X=np.c_[np.ones(len(X1)),X1]
    theta=np.zeros(X.shape[1]).reshape(-1,1)
    for _ in range(num_iters):
        predictions=(X).dot(theta).reshape(-1,1)
        errors=(predictions-y).reshape(-1,1)
        theta=learning_rate*(1/len(X1))*X.T.dot(errors)
    return theta
data=pd.read_csv(r'C:\Users\admin\Downloads\50_Startups.csv',header=None)
X=(data.iloc[1:,:-2].values)
X1=X.astype(float)
scaler=StandardScaler()
y=(data.iloc[1:,-1].values).reshape(-1,1)
X1_Scaled=scaler.fit_transform(X1)
Y1_Scaled=scaler.fit_transform(y)
theta=linear_regression(X1_Scaled,Y1_Scaled)
new_data=np.array([165349.2,136897.8,471784.1]).reshape(-1,1)
new_Scaled=scaler.fit_transform(new_data)
prediction=np.dot(np.append(1,new_Scaled),theta)
prediction=prediction.reshape(-1,1)
pre=scaler.inverse_transform(prediction)
print(data)
print(f"predicted value: {pre}")
```

## Output:
![linear regression using gradient descent](sam.png)
![output(ML)03 i](https://github.com/user-attachments/assets/c245d927-4311-428c-8648-3470ebf48c2a)
![output(ML)03 ii](https://github.com/user-attachments/assets/81f96c28-33d1-47ff-a935-8cea782590bf)



## Result:
Thus the program to implement the linear regression using gradient descent is written and verified using python programming.
