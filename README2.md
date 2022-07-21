# voting classifier
 voting classifier

 # use this code
 ```py

!pip install scikit-learn
import numpy as np
import pandas as pd
import sklearn as sklearn
from sklearn.tree import DecisionTreeClassifier
from sklearn.datasets import load_iris
iris_data = load_iris()
iris_data
iris_data['data'], iris_data['target']
iris_data.keys()
iris_data['filename']
iris_data['data_module']
iris_data.items()
iris_data.values()
features = iris_data['data']
labels = iris_data['target']
from sklearn.model_selection import train_test_split
X_train, X_test, Y_train, Y_test = train_test_split(
    features,
    labels,
    test_size=0.2
)
len(features)
len(labels)
len(features)/150
dt = DecisionTreeClassifier()
dt.fit(X_train, Y_train)
Y_pred = dt.predict(X_test)
Y_pred
from sklearn.metrics import accuracy_score
accuracy_score(Y_pred, Y_test)
from sklearn.ensemble import RandomForestClassifier
from sklearn.ensemble import VotingClassifier
from sklearn.linear_model import LogisticRegression
from sklearn.svm import SVC
from sklearn.tree import DecisionTreeClassifier
from sklearn.datasets import load_iris
from sklearn.metrics import accuracy_score
from sklearn.model_selection import train_test_split
  rf = RandomForestClassifier()
  rf.fit(X_train, Y_train)
  Y_pred_rf = rf.predict(X_test)
Y_pred_rf
accuracy_score(Y_pred_rf, Y_test)
from sklearn.ensemble import VotingClassifier
dt = DecisionTreeClassifier()
rf = RandomForestClassifier()
lr = LogisticRegression()
ewc = VotingClassifier(estimators=[('lr', lr), ('dt', dt), ('rf', rf)], voting = 'hard')
ewc
ewc.fit(X_train, Y_train)
ewc.score(X_test, Y_test)
ewc = VotingClassifier(estimators=[('lr', lr), ('dt', dt), ('rf', rf)], voting = 'soft')
ewc
ewc.fit(X_train, Y_train)
ewc.score(X_test, Y_test)

 ```