# Implementation-of-Linear-Regression-Using-Gradient-Descent

## AIM:
To write a program to predict the profit of a city using the linear regression model with gradient descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Start the program
 
2.Import numpy , pandas and matplotlib

3.Read the file which store the data

4.Declare x as Hours and y as scores of the dataset

5.Using loop predict the data and find the MSE,dm,dc,y intercept,slope using the formulae

6.Find the best fit using the straight line formula

7.Display the data in graph using matplotlib libraries

8.Stop the program

## Program:
```
/*
Program to implement the linear regression using gradient descent.
Developed by: PREETHA.S
RegisterNumber: 212222230110 
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd

data = pd.read_csv('dataset/ex1.txt', header = None)

plt.scatter(data[0], data[1])
plt.xticks(np.arange(5, 30, step = 5))
plt.yticks(np.arange(-5, 30, step = 5))
plt.xlabel("Population of City (10,000s)")
plt.ylabel("Profit ($10,000)")
plt.title("Profit Prediction")

def computeCost(x, y, theta):
    """
    Test in a numpy array x, y theta and generate the cost function
    in a linear regression model
    """
    m = len(y) # length of the training data
    h = X.dot(theta) # hypothesis
    square_err = (h - y) ** 2
    
    return 1/(2*m) * np.sum(square_err) #returning
    
data_n = data.values
m = data_n[:, 0].size
X = np.append(np.ones((m, 1)), data_n[:, 0].reshape(m, 1), axis = 1)
y = data_n[:, 1].reshape(m, 1)
theta = np.zeros((2, 1))

computeCost(X, y, theta) # Call the function

def gradientDescent(x, y, theta, alpha, num_iters):
    """
    Take in numpy array X, y and theta and update theta by taking num_oters gradient steps
    with learning rate of alpha
    
    return theta and the list of the cost of theta during each iteration
    """
    
    m = len(y)
    J_history = []
    
    for i in range(num_iters):
        predictions = X.dot(theta)
        error = np.dot(X.transpose(), (predictions - y))
        descent = alpha * 1/m * error
        theta -= descent
        J_history.append(computeCost(X, y, theta))
        
    return theta, J_history
    
theta, J_history = gradientDescent(X, y, theta, 0.01, 1500)
print("h(x) ="+str(round(theta[0, 0], 2))+" + "+str(round(theta[1, 0], 2))+"x1")

plt.plot(J_history)
plt.xlabel("Iteration")
plt.ylabel("$J(\Theta)$")
plt.title("Cost function using Gradient Descent")

plt.scatter(data[0], data[1])
x_value = [x for x in range(25)]
y_value = [y*theta[1]+theta[0] for y in x_value]
plt.plot(x_value, y_value, color = "r")
plt.xticks(np.arange(5, 30, step = 5))
plt.yticks(np.arange(-5, 30, step = 5))
plt.xlabel("Population of City (10,000s)")
plt.ylabel("Profit ($10,000)")
plt.title("Profit Prediction")

def predict(x, theta):
    """
    Takes in numpy array of x and theta and return the predicted value of y based on theta
    """
    
    predictions = np.dot(theta.transpose(), x)
    
    return predictions[0]
    
predict1 = predict(np.array([1, 3.5]), theta)*10000
print("For population = 35,000, we predict a profit of $"+str(round(predict1, 0)))

predict2 = predict(np.array([1, 7]), theta)*10000
print("For population = 70,000, we predict a profit of $"+str(round(predict2, 0)))

```

## Output:

### Profit prediction

![image](https://github.com/Preetha-Senthamilan/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119390282/265f3e06-cabe-4713-9f3c-6d956135d26f)

### Function output

![Screenshot 2023-10-05 103829](https://github.com/Preetha-Senthamilan/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119390282/7c2fd5e4-0fe3-4dce-b304-4919868814e4)

### Gradient descent

![image](https://github.com/Preetha-Senthamilan/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119390282/45433492-ceeb-48b6-8a6d-48addee5e315)

### Cost function using gradient descent:

![image](https://github.com/Preetha-Senthamilan/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119390282/6818f89e-c67b-4ac5-95fa-23837b4d0e6b)

### Profit Prediction:

![image](https://github.com/Preetha-Senthamilan/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119390282/307dd9b3-480d-4578-95a1-23e420e691b1)


### Profit prediction for a population of 35,000:

![image](https://github.com/Preetha-Senthamilan/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119390282/fd827473-b904-47f9-afe0-c6d60d89effc)

### Profit prediction for a population of 70,000:

![image](https://github.com/Preetha-Senthamilan/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119390282/b85b74d0-a0cc-4ffb-ab65-bf4d58bccfcb)








## Result:
Thus the program to implement the linear regression using gradient descent is written and verified using python programming.
