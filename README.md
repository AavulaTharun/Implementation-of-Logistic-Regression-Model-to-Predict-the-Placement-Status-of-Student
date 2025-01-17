# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. start the program. 
2. import pandas.
3. Read the csv file .
4. print the program.
5. Display the proram.
6. Stop the program.

## Program:
```
/*
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by:Aavula Tharun 
RegisterNumber: 212221240003 
*/
import pandas as pd
data = pd.read_csv("Placement_Data.csv")
print(data.head())
data1 = data.copy()
data1= data1.drop(["sl_no","salary"],axis=1)
print(data1.head())
data1.isnull().sum()
data1.duplicated().sum()
from sklearn.preprocessing import LabelEncoder
lc = LabelEncoder()
data1["gender"] = lc.fit_transform(data1["gender"])
data1["ssc_b"] = lc.fit_transform(data1["ssc_b"])
data1["hsc_b"] = lc.fit_transform(data1["hsc_b"])
data1["hsc_s"] = lc.fit_transform(data1["hsc_s"])
data1["degree_t"]=lc.fit_transform(data["degree_t"])
data1["workex"] = lc.fit_transform(data1["workex"])
data1["specialisation"] = lc.fit_transform(data1["specialisation"])
data1["status"]=lc.fit_transform(data1["status"])
print(data1)
x = data1.iloc[:,:-1]
print(x)
y = data1["status"]
from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test = train_test_split(x,y,test_size=0.2,random_state=0)
from sklearn.linear_model import LogisticRegression
lr = LogisticRegression(solver="liblinear")
print(lr.fit(x_train,y_train))
y_pred = lr.predict(x_test)
print(y_pred)
from sklearn.metrics import accuracy_score
accuracy = accuracy_score(y_test,y_pred)
print(accuracy)
from sklearn.metrics import confusion_matrix
confusion = confusion_matrix(y_test,y_pred)
print(confusion)
from sklearn.metrics import classification_report
classification_report1 = classification_report(y_test,y_pred)
print(classification_report1)
print(lr.predict([[1,80,1,90,1,1,90,1,0,85,1,85]]))
```

## Output:
![output](https://github.com/AavulaTharun/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/blob/main/1.png?raw=true)


![output](https://github.com/AavulaTharun/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/blob/main/2.png?raw=true)


![output](https://github.com/AavulaTharun/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/blob/main/3.png?raw=true)


![output](https://github.com/AavulaTharun/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/blob/main/4.png?raw=true)


![5](https://user-images.githubusercontent.com/93427201/162418254-da423b8f-54f2-48a5-b99d-da54160e54ab.png)


![6](https://user-images.githubusercontent.com/93427201/162418289-caf035e9-c05b-4e78-8e05-b46bbd48de4f.png)


![7](https://user-images.githubusercontent.com/93427201/162418332-0521c324-b18d-4eb7-a7f2-e3863dabbbdd.png)


![8](https://user-images.githubusercontent.com/93427201/162418367-3d87a11e-b153-4d71-a74c-82705f5c046c.png)





## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
