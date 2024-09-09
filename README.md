from sklearn.datasets import make_classification

X, y = make_classification(
    n_features=4,
    n_classes=.....,
    n_samples=35,
    n_informative=2, # الصفين المفيده
    random_state=1, # يثبت التقسيمه لو اشتغل مع احد يصير الي عندي فالترين كمان هو عندها
    n_clusters_per_class=1,
)

from sklearn.model_selection import train_test_split #    استخدم القيم الي بقيت  من التست  لتقسيم  للترينق ولازم يكون اكثرمن التست

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=....., random_state=.....
)

from sklearn.naive_bayes import GaussianNB #بعد ما اعطيه القيمه الي يختبرها في اكس اخليه يخمن قيمه الواي

# Build a Gaussian Classifier
model = GaussianNB()

# Model training
model.fit(X_train, y_train)

# Predict Output
predicted = model.predict([X_test[3......]])# اعطيته يخمن قيمه وحده

print("Actual Value:", y_test[3......])
print("Predicted Value:", predicted[0])

from sklearn.metrics import (
    accuracy_score,
    confusion_matrix,
    ConfusionMatrixDisplay,
    f1_score,
)

y_pred = model.predict(X_test)
accuray = accuracy_score(y_pred, y_test)
f1 = f1_score(y_pred, y_test, average="weighted")

print("Accuracy:", accuray)
print("F1 Score:", f1)

import pandas as pd


df = pd.read_csv('breast+cancer+wisconsin+diagnostic.zip')
df.head()

df.info() # توريني ايش الكولوم الموجوده
# نتيجه تقيم المودا كل ماقربت للواحد يعني المودل كويس  اهم شي ماتوصل 1
