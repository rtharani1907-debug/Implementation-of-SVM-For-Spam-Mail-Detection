# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
```
1.Import the required libraries and load the spam mail dataset.
2.Preprocess the text data using CountVectorizer or TF-IDF Vectorizer.
3.Split the dataset into training and testing datasets.
4.Train the SVM classifier model and evaluate its accuracy
```
## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: THARANI RAMESHBABU
RegisterNumber: 212225240170
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.svm import SVC
from sklearn.metrics import accuracy_score, classification_report
data = pd.read_csv("spam.csv", encoding='latin-1')
print(data.head())
data = data[['v1', 'v2']]
data.columns = ['label', 'message']
data['label'] = data['label'].map({'ham': 0, 'spam': 1})
X = data['message']
y = data['label']
vectorizer = TfidfVectorizer(stop_words='english')
X = vectorizer.fit_transform(X)
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)
model = SVC(kernel='linear')
model.fit(X_train, y_train)
y_pred = model.predict(X_test)
accuracy = accuracy_score(y_test, y_pred)
print("Accuracy :", accuracy)
print("\nClassification Report:\n")
print(classification_report(y_test, y_pred)) 
*/
```

## Output:
<img width="1588" height="660" alt="Screenshot_23-5-2026_19733_localhost" src="https://github.com/user-attachments/assets/ee28499e-061c-401b-8e36-668881122b05" />

## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
