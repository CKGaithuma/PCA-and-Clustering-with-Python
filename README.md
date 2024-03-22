<h1 style="text-align:center;">PCA-and-Clustering-with-Python</h1>
<div style="text-align:center;">
  <img src="images/pcaSteps.jpeg" alt="PCA Steps">
</div>

<h1 style="text-align:center;">PART I: PRINCIPAL COMPONENT ANALYSIS (PCA)</h1>
The essence of PCA is to find the directions of maximum variance in high dimensional data, and project it into
a smaller dimensional space while still retaining most of the information.

<h1 style="text-align:center;">STEPS TO IMPLEMENT PCA</h1>
- Standardize the data
- Center the data; subtract from mean.
- Calculate covariance matrix and eigenvectors.
- Project the Principal Components in the direction of the eigenvectors


<h1 style="text-align:center;">DATA UNDERSTANDING</h1>
The mpg/mtcars dataset shall be used to demonstrate PCA. The dataset originates from Seaborn, a Python library, which comes with a number of built-in datasets. The mpg dataset contains 398 entries with 9 columns. These columns contain various attributes and characteristics of different vehicle models, such as their fuel efficiency, engine specifications, weight, acceleration, manufacturing year, origin, and model name. 

Here is a breakdown of the columns:

1. mpg: Miles per gallon (fuel efficiency of the vehicle). It represents the number of miles the vehicle can travel per gallon of fuel.

2. cylinders: Number of cylinders in the engine. It indicates the number of internal combustion chambers where the air-fuel mixture is burned.

3. displacement: Engine displacement in cubic inches (cu in). It measures the total volume of all the cylinders in the engine.

4. horsepower: Engine horsepower. It represents the power output of the engine.

5. weight: Vehicle weight in pounds (lbs). It indicates the mass of the vehicle.

6. acceleration: Acceleration of the vehicle in seconds from 0 to 60 miles per hour (mph). It measures how quickly the vehicle can increase its speed.

7. model_year: Model year of the vehicle. It represents the year when the vehicle model was manufactured.

8. origin: Origin of the vehicle. It represents the manufacturing region or country of the vehicle.

9. name: Name of the vehicle model. It specifies the model or brand name of the vehicle.

<h1 style="text-align:center;">Exploratory Data Analysis</h1>

- Data Visualization: Visualizations are useful to be able to understand the distribution and relationships between different variables in the mpg dataset .

<div style="text-align:center;">
  <img src="images/Country of Origin.png" alt="Country of Origin" width="500" height="400">
</div>

- As we can see from the graph,majority of the vehicles in the dataset are from the USA region.
 

<div style="text-align:center;">
  <img src="Images/Power Vs Weight.png" alt="Power Vs Weight">
</div>
From the scatter plot with horsepower on the y-axis and weight on the x-axis, with different origins represented by different colors we can see:

* American vehicles, being heavier and more powerful, tend to cluster towards the upper right corner of the plot.
* European vehicles, though lighter and less powerful on average, still show a decent range of horsepower and weight.
* Japanese vehicles, typically lighter and with moderate horsepower, cluster towards the lower portion of the plot, exhibiting a more efficient balance between weight and power

* This plot provides a visual confirmation of these trends, with a few outliers and a general trend showing as weight of vehicle increases the horsepower also increases.

<div style="text-align:center;">
  <img src="Images/Acceleration Vs mpg.png" alt="Acceleration Vs mpg">
</div>
From the above visualization we can see Japanese vehicles generally have more economical fuel consumption i.e higher miles per gallon("mpg"). American vehicles have lower mpg rates indicating the lowest economical fuel consumption.

Acceleration performance is generally almost equal for vehicle classes from all the 3 regions. However, the American vehicles tend to have the lowest Acceleration performance. 

<h1 style="text-align:center;">Performing Principal Component Analysis</h1>

After running the exercise using the full dataset ('mpg' dataset) with 392 samples, the visual output were a mess. Instead, there is a smaller version of
the dataset ('mtcars' dataset) included to ensure we achieve the learning goals of today's work.

The mtcars dataset contains 32 entries of car models with columns representing the same features as the 'mpg' dataset.

Principal Component Analysis (PCA) is a dimensionality reduction technique used to reduce the number of features in a dataset while preserving most of the information. Here are the steps used to carry out PCA on the mtcars dataset:

1. Feature Standardization:

Standardize the features to have a mean of 0 and a standard deviation of 1. This step is essential for PCA as it ensures that features with larger scales do not dominate the principal components.
2. PCA Model Creation:

Create an instance of the PCA class from a suitable library such as scikit-learn.
3. Fit PCA Model:

Fit the PCA model to the standardized dataset. This step calculates the principal components and the explained variance ratio for each component.
4. Transform Data:

Transform the original data into the new feature space spanned by the principal components.
5. Explained Variance Ratio:

Analyze the explained variance ratio to determine the amount of variance explained by each principal component. This step helps in deciding how many principal components to retain.
6. Select Number of Components:

Determine the number of principal components to retain based on the cumulative explained variance. A common approach is to choose the number of components that explain a significant portion of the total variance (e.g., 90% or 95%). In the mtcars dataset we chose the first 2 components as they explained a significant portion of the variance and we wanted to visualize the 2 components.
7. Dimensionality Reduction:

Project the original data onto the selected principal components to obtain a reduced-dimensional representation of the dataset.
8. Analysis and Interpretation:
The PCA analysis produced a total of 11 principal components. The variance explained by each of these components is provided as a percentage. Here's the breakdown of the variance explained by each component:

PC1 explains approximately 60.08% of the variance in the data.
PC2 explains approximately 24.09% (84.17% - 60.08%) of the remaining variance after PC1.
PC3 to PC11 explains the remaining 15.83% of the variance.

Below is a visualization of the results. The visualization generates a biplot showing the first two principal components and their relationships with the original features.

div style="text-align:center;">
  <img src="images/biplot.png" alt="PCA Biplot>
</div>

The red arrows represent the loadings of each original feature on the principal components. This visualization helps in understanding which features contribute most to the variance captured by each principal component and how the data points are distributed in the reduced-dimensional space.



<h1 style="text-align:center;"> PART II: CLUSTERING TECHNIQUES</h1>

 Hierarchical clustering is a method of cluster analysis that builds a hierarchy of clusters. It starts by treating each data point as a singleton cluster and then successively merges pairs of clusters until all clusters have been merged into a single cluster that contains all the data points. In the context of the mtcars dataset, hierarchical clustering can be used to group similar cars based on their features.The Euclidean distance metric is used in this case to measure the distance or dissimilarity between data points. 

 - Average Linkage Method: In average linkage clustering, the distance between two clusters is defined as the maximum distance between any two points in the two clusters. This method tends to produce compact clusters.
<div style="text-align:center;">
  <img src="images/Average Linkage Cluster.png" alt="Average Linkage Cluster">
</div>
This dendrogram showing the hierarchical clustering result using average linkage. Each leaf in the dendrogram represents a car model, and the vertical height indicates the distance or dissimilarity between clusters. The height at which branches merge indicates the distance or dissimilarity at which clusters are combined.The average linkage method calculates the average distance between all pairs of points in two clusters, resulting in clusters that are relatively evenly distributed and not heavily biased towards outliers, as in single linkage method, nor heavily biased towards compactness, as in complete linkage method.

<h1 style="text-align:center;">CONCLUSION</h1>

Considering the characteristics of the mtcars dataset, which includes various numerical attributes representing car characteristics, the average linkage method may be the most suitable choice. This method would consider the overall similarity between clusters while avoiding the chaining effects of single linkage and the compactness bias of complete linkage.

Interpreting the dendrogram resulting from the average linkage clustering provides insights into the hierarchical structure and potential groupings within the dataset. For example, distinct clusters of car models with similar characteristics emerge, indicating different classes or categories of vehicles based on their attributes such as miles per gallon, horsepower, etc. The height at which branches merge in the dendrogram can also indicate the level of similarity between clusters, with lower heights representing higher similarities.

## Repository Guide

The datasets used can be found [here](<mtcars.csv>)

The notebook can be found [here](<core.ipynb>)
