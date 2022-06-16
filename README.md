# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the required packages.

2.Import the dataset to work on.

3.From sklearn module import kmeans.

4.Define number of clusters to be made.

5.Assign the cluster values.

6.Plot the cluster using matplotlib.pyplot

7.End the program.


## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: M.GUNASEKHAR
RegisterNumber:  212221240014
*/

import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers.csv")

data.head()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []#within-cluster sum of square.it is the squared distance between each point and the centroid is the cluster

for i in range(1,11):
  kmeans = KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
  
  plt.plot(range(1,11),wcss)
plt.xlabel("No.of clusters")
plt.ylabel("wcss")
plt.title("Elbow method")
km=KMeans(n_clusters=5)
km.fit (data.iloc[:,3:])
y_pred=km.predict(data.iloc[:,3:])
y_pred

data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")

```

## Output:
![output](https://github.com/gunasekhar159/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/blob/main/31.png?raw=true)

![output](https://github.com/gunasekhar159/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/blob/main/32.png?raw=true)

![output](https://github.com/gunasekhar159/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/blob/main/33.png?raw=true)

![output](https://github.com/gunasekhar159/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/blob/main/34.png?raw=true)

![output](https://github.com/gunasekhar159/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/blob/main/35.png?raw=true)




## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
