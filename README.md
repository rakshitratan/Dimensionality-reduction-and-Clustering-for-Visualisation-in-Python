# Dimensionality-reduction and Visualisation in Python
 
Aim of this project: Dimensionality reduction and Clustering

DataSet: Our dataset for this question consisted of pixel details for American Sign Language images that represented 24 English Alphabets. This dataset did not contain any information for the letter J and Z.

<h3> Process:</h3>
Our process is consisting of many steps as mentioned below:<br>
1. Loading libraries and understanding basic data structure.<br>
2. Splitting the Data<br>
3. Normalization<br>
4. Finding number of clusters using Elbow plot method<br>
5. K-Means clustering and PCA<br>
6. Applying U-MAP<br>
7. Applying T-SNE<br>

<h3>2. Splitting the Data</h3>

As in our dataset the very first column is considered as the label, we are dropping this column from the features and keeping it just in the labels. <br>

<h3>3. Normalization</h3>

Normalization of the values is done so that all the columns can have data in same range. In this process the variance is kept as 1 and mean is set as 0. This is done so that models do not concentrate on only one attribute and can get trained on all the attributes.<br>

<h3>4. Finding number of clusters using Elbow plot method</h3>

Elbow plot allows us to guess the number of clusters in a dataset. This can be done by plotting cluster numbers against the inertia. Inertia can be considered as the squared and summed value of distances of every single data point in the cluster from the cluster center. It is also known as WCSS which stands for within cluster sum of squared error.
Elbow point in any cluster is the point after which the drop is not so significant and this can be noticed by observing the sloe between two points. In this section the elbow point can lie near 2 to 3 as the slop in the starting segment is more.
Here we have kept the range between 1 to 25 as it is already known that total cluster value for this data is 24.

<h3>5. K-Means clustering and PCA</h3>
For reference we are using PCA to plot the data points and notice the crowding issues faced due to it. The primary components here are just 2. We also have taken 24 clusters due to the dataset as it is having 24 alphabets.
The graph generated clearly shows that all the data points are overlapping and creating crowding issues. To resolve this issue we are using T-SNE and UMAP.<br>

<h3>6. Applying U-MAP</h3>

Now we have created a 2D image to better understand the clusters present in our dataset. Here we have considered taking certain parameters. Firstly, we have taken n_neighbors as 12. This parameter governs how UMAP manages the data locally versus globally. This achieves so by limiting the size of UMAP's local neighborhood while trying to explain the data's diverse structure. This implies that small n neighbors values will cause UMAP to dwell on very local structure causing the detriment of bigger image. Whereas high values drive UMAP to look at larger communities at each point when estimating the data's multiple structure, sacrificing the detailed image for the sake of making the data broader. Multiple combination of the values were tried to come up with the optimal solution as 12.
Later on, we have selected min_dist value as 0.5. The min dist parameter regulates how tightly UMAP allows points to be packed together. It signifies the minimum distance apart that points can be in the representation of the lower dimensions. Low values result in clumps. Larger values help in preventing the packing structure. Here after trying with multiple values of min_dist, we came up with optimal value of 0.5 for our dataset.
While trying to tune the values for all the parameters we tried to provide min_dist greater than 1 and received an error saying the min_dist should be less than or equal to the spread. As the variance size is 1, the value of min_dist cannot exceed it so we choose to keep it below 1.<br>


<h3>7. Applying T-SNE</h3>

The same process mentioned above has been repeated for 3D-UMAP, where the n_neighbors are considered as 10 and min_dist as 0.007. These values are changed to observe how the decrement of both values will affect the classification of cluster.
We have taken random_state value as 42. It is a random number generator. Here we can pass values accordingly, such as p-value for Minkowski distance.
We have also considered taking n_components value as 3. This is used for the dimensional type of our representation. Here we are drawing our presentation on 3 dimensions, so we have considered taking the value as 3. <br>



