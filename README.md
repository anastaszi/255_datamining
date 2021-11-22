# Assignments
## HW1
[notebook](https://github.com/anastaszi/255_datamining/blob/main/HW1_AnastasiaZimina.ipynb)

The dataset used for this assigment is Hotel Booking Demand from [Kaggle](https://www.kaggle.com/jessemostipak/hotel-booking-demand/version/1)

### Data exploration findings: 

According to Kaggle discussion forum for this dataset about booking made in Portugal.\
The data consisted of 119390 records with 32 features recorded per each record. \
To get more insights about the data I checked types of data in the columns as well as the number of unique values. 

After the analysis of missing values I dropped 2 columns with most missing values and also dropped 'Country' columns

## HW2

[notebook](https://github.com/anastaszi/255_datamining/blob/main/HW2_Dimensionality_Reduction_Technics.ipynb)

2 datasets used: 
- Breast cancer wisconsin (diagnostic) dataset (Scikit-learn)
- MNIST digits dataset (openml)

### Tabular dataset

PCA and SVD: to explain 95% of variability 10 components are needed

![num-components](https://github.com/anastaszi/255_datamining/blob/main/img/num-components.png)

![elbow](https://github.com/anastaszi/255_datamining/blob/main/img/elbow.png)

2 components comparison
![psa](https://github.com/anastaszi/255_datamining/blob/main/img/pca.png)
![svd](https://github.com/anastaszi/255_datamining/blob/main/img/svd.png)
![tsne](https://github.com/anastaszi/255_datamining/blob/main/img/tsne.png)
![umap](https://github.com/anastaszi/255_datamining/blob/main/img/umap.png)
![lle](https://github.com/anastaszi/255_datamining/blob/main/img/lle.png)
![isomap](https://github.com/anastaszi/255_datamining/blob/main/img/isomap.png)


### Image dataset

PCA and SVD were used for dimensionality reduction and image compession. Both processes demonstrated almost identical results.
Number of features was reduced from 256  to 35 \
Original vs PCA-compressed vs SVD-compressed
![PCA](https://github.com/anastaszi/255_datamining/blob/main/img/img-pca.png)

Visual comparison of LLE, t-SNE, ISOMAP and UMAP

UMAP and t-SNE demostrates better results compared to ISOMAP and LLE

![tsne](https://github.com/anastaszi/255_datamining/blob/main/img/img-tsne.png)

![umap](https://github.com/anastaszi/255_datamining/blob/main/img/img-umap.png)

![lle](https://github.com/anastaszi/255_datamining/blob/main/img/img-lle.png)

![isomap](https://github.com/anastaszi/255_datamining/blob/main/img/img-isomap.png)

## HW3

[notebook]()

Comparison of custom and original sklearn Kmeans model: 

![kmeans](https://github.com/anastaszi/255_datamining/blob/main/img/hw3_kmeans.png)

Different clustering models were used to reduce number of colors for a given image 

Here is an original image and a new one created based on the centroid colors resulted from appling custom Kmeans model to the image.

![kmeans_image](https://github.com/anastaszi/255_datamining/blob/main/img/hw3_pic2.png)

The problem of the hierarchical clustering (Agglomerative) is that it is doesn't work on large data sets.
And our current reshaped image has more than 1bln rows. \
In order to proceed I took another image (smaller one) and used only unique color values.

![agglomerative](https://github.com/anastaszi/255_datamining/blob/main/img/hw3_pic1.png)

Results of GMM for color compression: 

![gmm](https://github.com/anastaszi/255_datamining/blob/main/img/hw3_pic3.png)

To work with PyCaret and DBSCAN I used another dataset: built-in dataset from Pycaret of reactions on different facebook posts.

Bellow are visualizations of 3d clustering results for DBSCAN (resulted in 22 clusters), KMeans (with preset 6 cluster), KMeans (with preset of 22 clusters):

![dbscan](https://github.com/anastaszi/255_datamining/blob/main/img/hw3_tsne_dbscan_pycaret.png)

![kmeans6](https://github.com/anastaszi/255_datamining/blob/main/img/hw3_tsne_kmeans_pycaret.png)

![kmeans22](https://github.com/anastaszi/255_datamining/blob/main/img/hw3_tsne_kmeans22_pycaret.png)