# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Load Data: Read the dataset using Pandas and explore it with .head() and .info() to understand the structure.
2. Find Optimal Clusters (Elbow Method): Use the Elbow method by fitting KMeans for k values from 1 to 10 and plot the Within-Cluster Sum of Squares (WCSS) to find the optimal number of clusters.
3. Train KMeans Model: Initialize and fit the KMeans model using the chosen number of clusters (e.g., 5) on the selected features (Annual Income and Spending Score).
4. Predict Clusters: Use the trained model to predict cluster labels and add them as a new column to the dataset.
5. Segment Data: Split the data into separate DataFrames based on predicted cluster labels for visualization.
6. Visualize Clusters: Plot the clusters using different colors to visualize how customers are grouped based on income and spending score.
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Shivaram M.
RegisterNumber:  212223040195
    import pandas as p
    import matplotlib.pyplot as py
    data=p.read_csv("Mall Customers.csv")
    data.head()
    data.info()
    
    
    from sklearn.cluster import KMeans
    wcss=[]
    for i in range(1,11):
      kmeans=KMeans(n_clusters=i,init="k-means++")
      kmeans.fit(data.iloc[:,3:])
      wcss.append(kmeans.inertia_)
    
    
    py.plot(range(1,11),wcss)
    py.xlabel("No.of cluster")
    py.ylabel("wcss")
    py.title("Elbow method")
    py.show()
    
    
    km=KMeans(n_clusters=5)
    km.fit(data.iloc[:,3:])
    y_pred=km.predict(data.iloc[:,3:])
    y_pred
    
    
    data["clusters"]=y_pred
    df0=data[data["clusters"]==0]
    df1=data[data["clusters"]==1]
    df2=data[data["clusters"]==2]
    df3=data[data["clusters"]==3]
    df4=data[data["clusters"]==4]
    
    
    py.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],color="gold")
    py.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],color="pink")
    py.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],color="green")
    py.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],color="blue")
    py.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],color="red")
*/
```

## Output:

<img width="1680" alt="Screenshot 2025-05-22 at 8 21 14 PM" src="https://github.com/user-attachments/assets/be634c09-383b-437e-a34d-bf4bf355631e" />
<img width="1680" alt="Screenshot 2025-05-22 at 8 21 20 PM" src="https://github.com/user-attachments/assets/f509aaeb-7a78-4dec-8888-c99373acbb1e" />
<img width="1680" alt="Screenshot 2025-05-22 at 8 21 27 PM" src="https://github.com/user-attachments/assets/3902a892-1c89-4c5f-b7fa-aaf5fb9ceea4" />
<img width="1680" alt="Screenshot 2025-05-22 at 8 21 32 PM" src="https://github.com/user-attachments/assets/3e56cb8f-a01a-48e5-82b7-61e193e012b5" />


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
