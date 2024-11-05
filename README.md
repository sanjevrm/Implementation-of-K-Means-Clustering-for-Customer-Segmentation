# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages using import statement.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data and Predict the cluster and plot data graphs.
4. Print the outputs and end the program

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: SANJEV R M
RegisterNumber:  212223040186


import pandas as pd 
import matplotlib.pyplot as plt
d=pd.read_csv("Mall_Customers.csv")
```
# DATA SET:
```
d.head()
```
![image](https://github.com/user-attachments/assets/675251df-59d0-4028-ade4-5c61f756df1c)
# DATA INFO:
```
d.info()
```
![image](https://github.com/user-attachments/assets/be535a0a-2977-42e4-bacd-8b8030c82873)
```
d.isnull().sum()
```
![image](https://github.com/user-attachments/assets/d7918bf7-5721-4666-a228-2eb83a2ed48a)
# Elbow method graph (wcss vs each iteration):
```
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    Kmeans=KMeans (n_clusters = i, init ="k-means++")
    Kmeans.fit(d.iloc[:,3:])
    wcss.append(Kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("no of cluster")
plt.ylabel("wcss")
plt.title("Elbow Metthod")
km=KMeans(n_clusters=5)
km.fit(d.iloc[:,3:])
y_pred = km.predict(d.iloc[:,3:])
y_pred
```
![image](https://github.com/user-attachments/assets/8393afca-931b-4256-bd22-193ddf679faf)
# Cluster represnting customer segments-graph:
```
d["clusters"]=y_pred
df0=d[d["clusters"]==0]
df1=d[d["clusters"]==1]
df2=d[d["clusters"]==2]
df3=d[d["clusters"]==3]
df4=d[d["clusters"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="clusters0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="pink",label="clusters1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="green",label="clusters2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="blue",label="clusters3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="black",label="clusters4")
plt.legend()
plt.title("Customer Segments")
```
![image](https://github.com/user-attachments/assets/fb99ffd3-39ac-4af4-bd15-fabe249660bc)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
