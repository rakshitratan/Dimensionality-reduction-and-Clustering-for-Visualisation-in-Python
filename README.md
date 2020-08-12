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

<h3>Splitting the Data</h3>

As in our dataset the very first column is considered as the label, we are dropping this column from the features and keeping it just in the labels. <br>

<h3>Normalization</h3>

Normalization of the values is done so that all the columns can have data in same range. In this process the variance is kept as 1 and mean is set as 0. This is done so that models do not concentrate on only one attribute and can get trained on all the attributes.<br>

<h3>Finding number of clusters using Elbow plot method</h3>

Elbow plot allows us to guess the number of clusters in a dataset. This can be done by plotting cluster numbers against the inertia. Inertia can be considered as the squared and summed value of distances of every single data point in the cluster from the cluster center. It is also known as WCSS which stands for within cluster sum of squared error.
Elbow point in any cluster is the point after which the drop is not so significant and this can be noticed by observing the sloe between two points. In this section the elbow point can lie near 2 to 3 as the slop in the starting segment is more.
Here we have kept the range between 1 to 25 as it is already known that total cluster value for this data is 24.
