# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## DATE:

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:

1. Import the required libraries.

2. Read the data frame using pandas.
3. Get the information regarding the null values present in the dataframe.
4. Apply label encoder to the non-numerical column inoreder to convert into numerical values.
5. Determine training and test data set.
6. Apply decision tree regression on to the dataframe.
7. Get the values of Mean square error, r2 and data prediction.

## Program:
```python
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: VARSHITHA A T
RegisterNumber:  21221040176
*/

import pandas as pd
data=pd.read_csv("Salary.csv")
print("\nThe first five data of the Salary.csv:")
print(data.head())
print("\nThe DataFrame:")
print(data.info())
print("\nCount the number of NaN values:")
print(data.isnull().sum())

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
print("\nThe first five data for Position:")
print(data.head())

x=data[["Position","Level"]]
y=data["Salary"]

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)

from sklearn import metrics
mse=metrics.mean_squared_error(y_test,y_pred)
print("\nThe Mean Squared Error:")
print(mse)

r2=metrics.r2_score(y_test,y_pred)
print("\nCoefficient of Determination:")
print(r2)

print("\nPrediction Value:")
print(dt.predict([[5,6]]))

```

## Output:

### The first five data of the Salary.csv:

![image](https://github.com/varshithathirumalachari/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/131793193/8a91e113-609a-4069-80f6-1f73119f05a0)


### The DataFrame:

![image](https://github.com/varshithathirumalachari/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/131793193/5f7f778f-f57f-4328-9c0e-fb1abe17c281)


### Count the number of NaN values:

![image](https://github.com/varshithathirumalachari/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/131793193/7fd597ef-e741-47b7-a482-3f987239e850)


### The first five data for Position:

![image](https://github.com/varshithathirumalachari/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/131793193/6b4e0c4b-79c3-45d4-857e-9dfda29ec948)


### The Mean Squared Error:
![image](https://github.com/varshithathirumalachari/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/131793193/34f47898-71c7-4388-a767-e3b53e7b29fc)


### Coefficient of Determination:

![image](https://github.com/varshithathirumalachari/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/131793193/fc7b4c76-3c11-443c-a010-e339d9bb20a0)


### Prediction Value:

![image](https://github.com/varshithathirumalachari/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/131793193/d03be8f5-fe32-4aaa-8ae7-0e9d317b0840)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
