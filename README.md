# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
```
1. Collect and preprocess data (tokenize, remove stopwords, convert to numerical format using TF-IDF or Bag of Words).
2. 2.Split the dataset into training and testing sets (e.g., 80/20).
3. 3.Train the SVM model using a linear kernel and optimize hyperparameters.
4. 4.Test the model and evaluate performance metrics (accuracy, precision, recall, F1-score). 5.Deploy the model and periodically retrain with updated data.
```
## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by:Eesha Ranka
RegisterNumber:24900107 
*/
```
```
import chardet
file='spam.csv'
with open(file,'rb') as rawdata:
    result=chardet.detect(rawdata.read(100000))
print(result)
import pandas as pd
data=pd.read_csv("spam.csv",encoding='Windows-1252')
data.head()
data.info()
data.isnull().sum()
x=data["v1"].values
y=data["v2"].values
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)
from sklearn.feature_extraction.test import CountVectorizer
cv=CountVectorizer()
x_train=cv.fit_transform(x_train)
x_test=cv.transform(x_test)
from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train,y_train)
y_pred=svc.predict(x_test)
print(y_pred)
from sklearn import metrics
accuracy=metric.accuracy_score(y_test,y_pred)
print(accuracy)
```

## Output:
```
{'encoding': 'Windows-1252', 'confidence': 0.7272080023536335, 'language': ''}
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 5572 entries, 0 to 5571
Data columns (total 5 columns):
 #   Column      Non-Null Count  Dtype 
---  ------      --------------  ----- 
 0   v1          5572 non-null   object
 1   v2          5572 non-null   object
 2   Unnamed: 2  50 non-null     object
 3   Unnamed: 3  12 non-null     object
 4   Unnamed: 4  6 non-null      object
dtypes: object(5)
memory usage: 217.8+ KB
0.003587443946188341
```
## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
