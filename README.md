# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. 
2. 
3. 
4. 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by:somalarajurohini 
RegisterNumber:24000337  
*/
```


import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
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
y_pred
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"], df0["Spending Score (1-100)"], c="red", label="Cluster 0")
plt.scatter(df1["Annual Income (k$)"], df1["Spending Score (1-100)"], c="black", label="Cluster 1")
plt.scatter(df2["Annual Income (k$)"], df2["Spending Score (1-100)"], c="blue", label="Cluster 2")
plt.scatter(df3["Annual Income (k$)"], df3["Spending Score (1-100)"], c="green", label="Cluster 3")
plt.scatter(df4["Annual Income (k$)"], df4["Spending Score (1-100)"], c="magenta", label="Cluster 4")
plt.legend()
plt.title("Customer Segments")
 
## Output:

![Screenshot 2024-12-18 203555](https://github.com/user-attachments/assets/9c051ed2-9e6a-47cd-b247-6e9f91aab0ba)


![Screenshot 2024-12-18 203602](https://github.com/user-attachments/assets/33ceae9d-6c99-4dc7-958f-64beb7df41cd)


![Screenshot 2024-12-18 203620](https://github.com/user-attachments/assets/a9c6bc54-4700-433c-986a-8892c5d8393a)






![Screenshot 2024-12-18 203627](https://github.com/user-attachments/assets/309481ed-c489-4750-8ed7-2db1b6b325a2)







![Screenshot 2024-12-18 203633](https://github.com/user-attachments/assets/9f3e3de6-374a-44e4-aae2-5c21a8d78386)




## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
