# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
## Algorithm

1.Import libraries and load data.

2.Select features for clustering.

3.Fit KMeans model with chosen clusters (e.g., k=5).

4.Predict clusters and plot results.

5.Print cluster centers and finish.


## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: karthikeyan k
RegisterNumber:  212223230101
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv(r"C:\Users\admin\Downloads\Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans =KMeans (n_clusters = i, init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range (1,11), wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5) 
km.fit(data.iloc[:,3:])
KMeans (n_clusters=5)
y_pred = km.predict(data.iloc[:,3:]) 
y_pred
data["cluster"] = y_pred
df0= data[data["cluster"]==0]
df1= data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"], df0["Spending Score (1-100)"],c="red", label="cluster0")
plt.scatter(df1["Annual Income (k$)"], df1["Spending Score (1-100)"],c="black", label="cluster1")
plt.scatter(df2["Annual Income (k$)"], df2 ["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter (df3["Annual Income (k$)"], df3 ["Spending Score (1-100)"],c="green", label="cluster3")
plt.scatter (df4["Annual Income (k$)"], df4["Spending Score (1-100)"],c="magenta", label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
## Output:

![Screenshot 2025-05-13 102405](https://github.com/user-attachments/assets/f4698aaf-8e55-41fd-a5fd-75174d1373c6)

![Screenshot 2025-05-13 102418](https://github.com/user-attachments/assets/33cc59b7-913f-43b5-bbe6-5f27580bc944)

![Screenshot 2025-05-13 102428](https://github.com/user-attachments/assets/83b96b52-743c-43f2-ac6a-3e53be1e628f)

![Screenshot 2025-05-13 102443](https://github.com/user-attachments/assets/7a98542d-fca7-4fd2-a526-3f7904c616f2)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
