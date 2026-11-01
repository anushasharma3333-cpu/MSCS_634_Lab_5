# MSCS_634_Lab_5: Hierarchical and DBSCAN Clustering


**Objective**
1. Investigate agglomerative hierarchical clustering and DBSCAN using scikit-learn Wine dataset (178 samples and 13 numerical features).
2. Standardize features, experiment with different parameters, visualize clustering using PCA, and analyze silhouette, homogeneity, and completeness scores.
   
**Methods**

1. Hierarchical clustering uses Ward linkage, n_clusters ranges from 2 to 6 and truncated dendrogram is plotted.
2.  DBSCAN has various eps values from 1.5 to 4.5 and min_samples values of 3, 5, and 8. Black crosses indicate noise points.
3. All models are fitted on the complete standardized feature matrix while PCA is used for visualization purposes only.
   
**Key findings and insights**

1. Hierarchical Clustering Performance: Hierarchical Clustering with 3 clusters had a Silhouette Score of 0.277, a Homogeneity Score of 0.790, and Completeness Score of 0.783. It was the highest silhouette score obtained from any of the hierarchical clustering models used.

2. DBSCAN Clustering Performance: DBSCAN with eps=2.2 and min_samples=5 generated 2 clusters with 55 noise points and Silhouette Score of approximately 0.348. With eps=1.5, all 178 observations were noise points while with eps=4.5 all 178 observations formed one cluster.

3. Comparison of Silhouette Scores: In calculating the Silhouette Score, DBSCAN ignores noise points while for hierarchical clustering, all 178 observations are included in the Silhouette Score calculation. Consequently, the scores cannot be used in making a comparison of the performance of the two algorithms.

4. Effects of Parameters Used: From the results, it is evident that selection of parameters plays an important role in clustering outcomes. For instance, in Hierarchical Clustering the number of clusters has an effect on clustering, while in DBSCAN eps and min_samples affect number of clusters and noise points respectively.
5. 5. Effectiveness of Hierarchical Clustering: Hierarchical Clustering offers an organized way to find commonalities between wine samples. Dendrogram assists in understanding relations between observations and how small clusters form larger clusters.

6. Noisy Observations Identification in DBSCAN: DBSCAN helps in detecting noise and outliers. While hierarchical clustering clusters every observation in a data set into a cluster, DBSCAN is able to label observations as noise, hence, it can be used with datasets having abnormal observations.

7. Significance of Data Standardization: Standardization of all 13 features of the Wine dataset prevents the effect of different units of measurements on clustering outcomes. This is because both algorithms use distance measures for clustering.


**Challenges and decisions**

1. Scaling was required for the Wine attributes due to their different numeric scales.
2. DBSCAN was sensitive to parameter choices in 13-dimensional space. Certain combinations resulted in less than two clusters that were not noise, so silhouette score was left undefined.
3. True Wine classes were only used for the purpose of evaluation and not during model training.
4.  2D PCA plot is only a visual representation and does not necessarily retain all relationships from the original 13-dimensional space.
