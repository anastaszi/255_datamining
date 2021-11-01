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

2 datasets used: 
- Breast cancer wisconsin (diagnostic) dataset (Scikit-learn)
- MNIST digits dataset (openml)

### Tabular dataset

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

