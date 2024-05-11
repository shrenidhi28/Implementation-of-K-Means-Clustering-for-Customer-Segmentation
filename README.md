# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages using import statement.
2. Read the given csv file using read_csv() method and print the number of
contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print the outputs and end the program. 

## Program:
```

Program to implement the K Means Clustering for Customer Segmentation.
Developed by: C.SHRENIDHI
RegisterNumber:  212223040196
```
```
import pandas as pd

import matplotlib.pyplot as plt

data=pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans

wcss=[]

for i in range(1,11):

kmeans=KMeans(n_clusters=i,init="k-means++")

kmeans.fit(data.iloc[:,3:])

wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)

plt.xlabel("No_of_Clusters")

plt.ylabel("wcss")

plt.title("Elbow Method")

km=KMeans(n_clusters=5)

km.fit(data.iloc[:,3:])

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

plt.title("Customer Segment")

```

## Output:
# Dataset:
![image](https://github.com/shrenidhi28/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/155261096/1d440847-cbfa-40f1-acc7-a276608634a0)

# Dataset information:
![image](https://github.com/shrenidhi28/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/155261096/078324ab-3ac4-49c0-86fd-34dff70ed0d5)

# Elbow method graph (wcss vs each iteration):
![image](https://github.com/shrenidhi28/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/155261096/a474db49-b74a-4628-9952-e3b3b70b7ad7)

# Cluster represnting customer segments-graph:
![image](https://github.com/shrenidhi28/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/155261096/cbbd96c7-4097-422f-8546-c999faa4e8d5)





## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
