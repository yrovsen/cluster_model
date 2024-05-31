# Applying Cluster methods 
Clustering algorithms are fundamental tools in data analysis and prediction, allowing us to uncover hidden patterns and structures within datasets. This project delves into the application of diverse clustering techniques to solve real-world problems and enhance decision-making processes.

## Introduction

Data clustering plays a pivotal role in organizing unlabelled data into meaningful groups, enabling insights that drive business strategies, scientific research, and societal advancements. By grouping data points based on similarity metrics, clustering algorithms facilitate exploratory data analysis, anomaly detection, and segmentation tasks across various domains.

## Objectives

- **Exploration of Algorithms**: This project aims to explore a spectrum of clustering algorithms, each tailored to different data characteristics and objectives. By understanding the strengths and limitations of algorithms like KMeans, hierarchical clustering, and others, we can select the most suitable method for specific datasets and analytical goals.

- **Predictive Capabilities**: Beyond descriptive analysis, clustering models in this project are leveraged for predictive tasks. By identifying clusters with distinct characteristics, we can extrapolate trends, forecast trends, and make informed decisions based on data-driven insights.

- **Scalability and Deployment**: Emphasizing practicality, the project addresses scalability concerns and deployment strategies. Optimizing algorithms for large-scale datasets and integrating them into scalable frameworks ensures robust performance in real-time applications.

---

## Contents

1. **Data Import**
   - Details the process of importing data and any considerations. Data has been analyzed deeply, and observed statistically to get better understanding. More information about features were given in the second sheet of dataset file.

2. **Preprocessing Steps**
   - **Filling Null Values**: Missing values have been replaced by mean (if it is numeric column) or mode of categoric columns.

3. **KMeans Cluster Method**
   - To find best k value for clustering, wcss and silhouette scores were found respectively and elbow curve plotted for observation. WCSS (Within-Cluster Sum of Squares) measures the sum of squared distances between each data point and its assigned centroid within a cluster, aiming to minimize this value to achieve tighter clusters and better separation between clusters. Silhouette scores assess clustering quality by measuring how similar each data point is to its own cluster compared to others, with higher scores indicating well-defined clusters.
![image](https://github.com/yrovsen/cluster_model/assets/137065696/04d7b05d-2b1c-4726-9d11-ebbb1f749b55)

Based on this graph, k = 3 was chosen best option for this model, and silhouette score for this k value is 0.4653.

4. **Hierarchical Method**
   - First of all, data was scaled using normalize method, and then dendrograms were plotted to choose optimal value for clustering:

![image](https://github.com/yrovsen/cluster_model/assets/137065696/8c2d3887-3d8c-468c-943c-debafe38c953)

Based on this plot, the number of cluster was chosen as 3, and using Agglomerative Clustering the cluster column has been created accordingly. Here is more information about Agglomerative Clustering. It is a hierarchical clustering method that starts with each data point as its own cluster and progressively merges clusters based on similarity until all points belong to a single cluster. It uses linkage criteria such as Ward, complete, or average linkage to determine how clusters are merged at each step. This method is effective for exploring hierarchical relationships within data and visualizing them using dendrograms.
Finally, silhouette score will be 0.285.

5. **Modelling**
   - After clustering applied, it can be checked using building the SVM model for multinomial classifiaction. Here One Versus One classifier is used to determine average gini score. The One-Versus-One (OvO) Classifier is a strategy used in machine learning for handling multi-class classification tasks. In OvO, a binary classifier is trained for every pair of classes in the dataset. During prediction, each classifier predicts which of the two classes is more likely for a given input. The final class prediction is determined by aggregating the votes from all pairwise classifiers, often using a voting scheme (e.g., majority voting). OvO is useful for algorithms that natively support binary classification (e.g., Support Vector Machines) and can effectively handle complex class relationships and imbalanced datasets.

Here is the results: Gini score for model is 0.995, since target column has been created using other features. Therefore, it results in a high value.
---
