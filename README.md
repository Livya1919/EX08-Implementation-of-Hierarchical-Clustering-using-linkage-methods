# EX8-Implementation of Hierarchical Clustering using linkage methods
## DATE:
## AIM:
To implement Hierarchical Clustering using single and complete linkage method

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Compute the distance between every pair of data points,resulting in a distance matrix.
2.Assign each data point to its own individual cluster. 
3.Using a linkage criterion,find the two closest cluster and merge them.
4.Visualize the hierarchical clustering as a dendrogram.

## Program:
```
/*
Program to implement Hierarchical Clustering using single and complete linkage method
Developed by: Livya Dharshini G
RegisterNumber: 2305001013
*/
 import pandas as pd
 import numpy as np
 import matplotlib.pyplot as plt
 from scipy.cluster.hierarchy import dendrogram, linkage, fcluster # Changed 'dendog
 from sklearn.preprocessing import StandardScaler
 df=pd.read_csv('/content/Hclus_EX8.csv')
 df.head()
 X=df[['StudentID','Marks']].values
 X
 #Perform hierarchical clustering (agglomerative)
 Z=linkage(X, method='complete')
 #Plot dendogram
 plt.figure(figsize=(5,2))
 plt.title("Dendogram for Student Segmentation")
 labels=range(1,len(df)+1)
 dendrogram(Z,labels=labels)
 plt.xlabel("Student ID")
 plt.ylabel("Marks")
 plt.show()
 #Cut the dendrogram to form clusters(let's say we want 5 clusters)
 max_clusters=2
 clusters=fcluster(Z,max_clusters,criterion='maxclust')
 clusters
 #Scatter plot with different colors for each cluster
 plt.figure(figsize=(5,2))
 plt.scatter(X[:,0],X[:,1],c=clusters,cmap='rainbow',s=100)
 plt.title("Student segmented (Hierarchical Clustering)")
 plt.xlabel("Student ID")
 plt.ylabel("Marks")
 plt.show()
 Z=linkage(X, method='single')
 #Plot dendogram
 plt.figure(figsize=(5,2))
 plt.title("Dendogram for Student Segmentation")
 labels=range(1,len(df)+1)
 dendrogram(Z,labels=labels)
 plt.xlabel("Student ID")
 plt.ylabel("Marks")
 plt.show()
 #Cut the dendrogram to form clusters(let's say we want 5 clusters)
 max_clusters=2
 clusters=fcluster(Z,max_clusters,criterion='maxclust')
 clusters
 #Scatter plot with different colors for each cluster
 plt.figure(figsize=(5,2))
 plt.scatter(X[:,0],X[:,1],c=clusters,cmap='rainbow',s=100)
 plt.title("Student segmented (Hierarchical Clustering)")
 plt.xlabel("Student ID")
 plt.ylabel("Marks")
 plt.show()
```

## Output:![image](https://github.com/user-attachments/assets/4af0e301-736d-4706-9b7d-70316c5aa32b)
![image](https://github.com/user-attachments/assets/09cb3c4a-7783-45ff-b578-6e4f11ce94bb)
![image](https://github.com/user-attachments/assets/3eee0c8b-3668-473a-b74d-3cd32ce68be4)
![image](https://github.com/user-attachments/assets/8b86a867-8e72-4c0f-8414-d44667843a56)
![image](https://github.com/user-attachments/assets/6e52d50d-ebe5-437f-b541-54ff01359128)
![image](https://github.com/user-attachments/assets/46bee14d-e41c-4d7a-9e20-233bca8b4706)









## Result:
Thus the implementation of Hierarchical Clustering using single and complete linkage method in python programming and verified successfully.
