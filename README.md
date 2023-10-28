# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import pandas and matplotlib.pyplot.
2. Read the dataset and transform it.
3. Import KMeans and fit the data in the model.
4. Plot the Cluster graph.

## Program:
```py
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: ARSHATHA P
RegisterNumber: 212222230012
```
```py
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers.csv")

data.head()
data.info()
data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
  kmeans = KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
data["cluster"] = y_pred

df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]

plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="olive",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="orange",label="cluster4")
```
## Output:
data.head() function.

![8 1](https://github.com/arshatha-palanivel/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118682484/c76d439d-39ec-47b7-a097-24268892073d)

data.info().

![8 2](https://github.com/arshatha-palanivel/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118682484/7b29f223-e32b-4af2-9543-93469a69cb64)

data.isnull().sum() function.

![8 3](https://github.com/arshatha-palanivel/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118682484/b653b060-d0b5-4e5c-b697-7fcbb1fc7914)

Elbow method Graph.

![8 4](https://github.com/arshatha-palanivel/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118682484/3f3dbff1-2f6c-4f9d-9017-f833887aeccf)

KMeans clusters.

![8 5](https://github.com/arshatha-palanivel/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118682484/a7fd7b54-d1b6-4a68-b912-5c7257349b4f)

![8 6](https://github.com/arshatha-palanivel/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118682484/a46e6b46-6e2c-4af8-8399-6b49742f9dc3)

Customer segments Graph.

![8 7](https://github.com/arshatha-palanivel/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118682484/c2c91dd6-506d-4fc5-b75e-92e37828fc61)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
