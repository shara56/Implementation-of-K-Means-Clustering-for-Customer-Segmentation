# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas and matplot libraries.
2. import Kmeans algorithm to solve customer segmentation.
3. Using the for loop cluster the given data
4. Predict the output and plot data graphs.
5. Display the outputs

## Program:
```

Program to implement the K Means Clustering for Customer Segmentation.
Developed by: SHARANGINI T K
RegisterNumber:  212222230143


import pandas as pd

import matplotlib.pyplot as plt

data=pd.read_csv("/content/Mall_Customers (1) (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
WCSS=[]

for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  WCSS.append(kmeans.inertia_)

  plt.plot(range(1,11), WCSS)
plt.xlabel("No. of clusters")
plt.ylabel("WCSS")
plt.title("Elbow Method")

km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"]==0]

df1 = data[data["cluster"]==1]

df2 = data[data["cluster"]==2]

df3 = data[data["cluster"]==3]

df4 = data[data["cluster"]==4]

plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")

plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")

plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")

plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")

plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")

plt.legend()
plt.title("Customer segments")
```

## Output:

data.head() function

![51](https://github.com/hariprasath5106/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/111515488/a80dbcda-cb89-4a5d-9e21-d0ad0baf8a3e)

data.info

![52](https://github.com/hariprasath5106/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/111515488/f9551193-8ad0-4d10-8170-f5e94c2ac634)

data.isnull().sum() function

![54](https://github.com/hariprasath5106/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/111515488/b764e2fb-1fcf-41c1-b499-c6b3433aac97)

### Elbow Method Graph
![55](https://github.com/hariprasath5106/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/111515488/488cc513-f21e-4abe-9a31-3e00e332532d)

### KMeans clusters
![56](https://github.com/hariprasath5106/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/111515488/55cf7be8-300b-40da-8ffe-cb258f8600b5)

### array()
![57](https://github.com/hariprasath5106/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/111515488/e790374a-18d1-4fbd-a12f-ad90c51dfa4f)

### Customers segments Graph
![58](https://github.com/hariprasath5106/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/111515488/b4f21a1f-1ff4-4c1a-aef0-9bf0a79859ec)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
