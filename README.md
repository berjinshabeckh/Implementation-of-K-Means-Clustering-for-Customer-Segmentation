# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages using import statement.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print the output and end the program.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: R Guruprasad
RegisterNumber:  212222240033
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers (1).csv")
data

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
  kmeans = KMeans(n_clusters = i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No . of clusters")
plt.ylabel("wcss")
plt.title("Elbow method")

km=KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
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
plt.title("Customer Segments   ")
```

## Output:

![image](https://github.com/R-Guruprasad/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119390308/e4bd5502-9833-4383-b321-3dd63cfdb1c2)
## data.head()
![image](https://github.com/R-Guruprasad/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119390308/fa001769-8786-49d4-9460-c50bbac0d718)
## data.info()
![image](https://github.com/R-Guruprasad/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119390308/0a5b3766-be12-4ff5-928e-1d207bf441a2)
## data.isnull().sum()
![image](https://github.com/R-Guruprasad/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119390308/15d00075-1f5d-4e99-bc08-166113270dde)
![image](https://github.com/R-Guruprasad/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119390308/8daf7417-f4e9-4124-9a33-be720e091579)
## Elbow method graph
![image](https://github.com/R-Guruprasad/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119390308/940e717e-5f03-4aad-9135-37d4fd3b2e5d)
## Kmeans cluster
![image](https://github.com/R-Guruprasad/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119390308/cfd8e56d-6cdb-44e0-94b9-5202ab6ba90e)
## y_pred
![image](https://github.com/R-Guruprasad/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119390308/7c6758c6-b8ad-4091-bbf6-c7145c0e1c46)
## Customers Segments Graph
![image](https://github.com/R-Guruprasad/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119390308/0539d171-b50b-4601-8071-b914e9c271ad)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
