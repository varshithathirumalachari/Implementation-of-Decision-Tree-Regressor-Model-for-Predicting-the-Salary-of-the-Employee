# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import pandas as pd and import the required dataset.

2.Calculate the null values in the dataset.

3.Import the LabelEncoder from sklearn.preprocessing

4.Convert the string values to numeric values.

5.Import train_test_split from sklearn.model_selection.

6.Assign the train and test dataset.

7.Import DecisionTreeRegressor from sklearn.tree.

8.Import metrics from sklearn.metrics.

9.Calculate the MeanSquareError.

10.Apply the metrics to the dataset.

11.Predict the output for the required values.
## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: VARSHITHA A T
RegisterNumber: 212221040176 
*/
import pandas as pd
data = pd.read_csv("/content/Salary.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
data["Position"]= le.fit_transform(data["Position"])
data.head()  
x= data[["Position","Level"]]
y= data["Salary"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2,random_state=2)
from sklearn.tree import DecisionTreeRegressor
dt = DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
from sklearn import metrics
mse = metrics.mean_squared_error(y_test,y_pred)
mse
r2=metrics.r2_score(y_test,y_pred)
r2
dt.predict([[5,6]])
```
## Output:
## HEAD
![image](https://github.com/varshithathirumalachari/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/131793193/23bbd405-dda3-403b-be42-6694c102a41f)
## INFO
![image](https://github.com/varshithathirumalachari/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/131793193/c96cd9cf-547b-4181-a661-9d5948b92802)
## ISNULL
![image](https://github.com/varshithathirumalachari/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/131793193/32e6687d-671b-4788-b6a2-c0bddeb51168)
## LABELENCODER
![image](https://github.com/varshithathirumalachari/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/131793193/988f9f4e-c6cc-4d07-a85e-544c1a418eef)
## MSE
![image](https://github.com/varshithathirumalachari/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/131793193/0770a1a8-db06-4f35-b014-32ffa6e1c4c6)
## R2
![image](https://github.com/varshithathirumalachari/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/131793193/66022a8d-660f-4dfc-bf82-3469ff17614f)
## PREDICT
![image](https://github.com/varshithathirumalachari/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/131793193/36cba012-4e77-4e5f-8cbe-1b4a898f3fed)

## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
