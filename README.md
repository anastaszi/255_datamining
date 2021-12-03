# Story:
[Medium Link](https://medium.com/@nastyazimina/fashion-meets-computer-vision-df8fe61f6cd8)

# Assignments
[Homework1](#hw1) \
[Homework2](#hw2) \
[Homework3](#hw3) \
[Homework4](#hw4)

***
# HW1
[notebook](https://github.com/anastaszi/255_datamining/blob/main/HW1_AnastasiaZimina.ipynb)

The dataset used for this assigment is Hotel Booking Demand from [Kaggle](https://www.kaggle.com/jessemostipak/hotel-booking-demand/version/1)

### Data exploration findings: 

According to Kaggle discussion forum for this dataset about booking made in Portugal.\
The data consisted of 119390 records with 32 features recorded per each record. \
To get more insights about the data I checked types of data in the columns as well as the number of unique values. 

After the analysis of missing values I dropped 2 columns with most missing values and also dropped 'Country' columns

***
# HW2

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

***
# HW3

[notebook](https://github.com/anastaszi/255_datamining/blob/main/HW3_Anastasia_Zimina.ipynb)

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

![gmm](https://github.com/anastaszi/255_datamining/blob/main/img/hw3_pic3.jpg)

To work with PyCaret and DBSCAN I used another dataset: built-in dataset from Pycaret of reactions on different facebook posts.

Bellow are visualizations of 3d clustering results for DBSCAN (resulted in 22 clusters), KMeans (with preset 6 cluster), KMeans (with preset of 22 clusters):

![dbscan](https://github.com/anastaszi/255_datamining/blob/main/img/hw3_tsne_dbscan_pycaret.png)

![kmeans6](https://github.com/anastaszi/255_datamining/blob/main/img/hw3_tsne_kmeans_pycaret.png)

![kmeans22](https://github.com/anastaszi/255_datamining/blob/main/img/hw3_tsne_kmeans22_pycaret.png)

***
# HW4

[notebook](https://github.com/anastaszi/255_datamining/blob/main/HW4_Anastasia_Zimina.ipynb)

## LSH

Library: **MinHashLSHForest** from [datasketch](http://ekzhu.com/datasketch/lshforest.html) \
Dataset: [Indian Food Receipts](https://www.kaggle.com/nehaprabhavalkar/indian-food-101) \
Task: Recommendation Engine of Similar Dishes based on ingredients

```
Query for ingredients = 'sugar, milk'
```

```
It took 0.008231878280639648 seconds to query forest.

 Top Recommendation(s) is(are) 
               name                  ingredients
8         Kalakand  Milk, cottage cheese, sugar
11           Lassi    Yogurt, milk, nuts, sugar
43  Kakinada khaja           Wheat flour, sugar
21   Chhena kheeri          Chhena, sugar, milk
56         Basundi            Sugar, milk, nuts
```

## Exhaustive search

Library: **faiss** by [Facebook](https://github.com/facebookresearch/faiss) [IndexFlatL2] \
Dataset: [News Headlines Dataset For Sarcasm Detection](https://www.kaggle.com/rmisra/news-headlines-dataset-for-sarcasm-detection?select=Sarcasm_Headlines_Dataset_v2.json) \
Task: Find Similar Articles' Headlines

```
The most similar movies to banksy returns to new york city with one of his trademark rats are:
* banksy returns to new york city with one of his trademark rats
* new documentary makes the case for supervised heroin injection sites in new york
* tony hale reveals the new york inspiration for buster bluth's personality
* giuliani spotted sleeping on new york city subway
* russell simmons leads 'i am a muslim too' rally in new york
* find lead paint violations in new york city neighborhoods
* watch live: bernin up nyc dance party in brooklyn, new york
* congressman says new york city gunman got 'raw deal'
* george and amal cloney are a vision in nyc
* kasich hastily paints name on side of skyscraper in attempt to woo new york voters
```

## Product Quantization

Library: **faiss** by [Facebook](https://github.com/facebookresearch/faiss) [IndexFlatL2, IndexIVFPQ] \
Dataset: [Medium articles dataset for 2020](https://www.kaggle.com/shlokramteke/sdfadgdadfda) \
Task: Find Similar Meduim Articles

```
Similar Meduim articles for Android’s ImageView scale type cheatsheet
['Android Gradle Build Configuration',
 'How to Deploy Your Qt Cross-Platform Applications to\xa0Android',
 'Generating DeepLinks at compile time\xa0Android',
 'Android Notifications#1: Creating Basic Notifications',
 'Getting Started With Android\xa0Testing',
 'Modern Android Development',
 'Creating a Kotlin Android rotary\xa0knob',
 'Build A Simple Calculator Application For Android Using Kotlin And Android\xa0Studio',
 'How to Create a Stopwatch in\xa0Android?',
 'Android’s ImageView scale type cheatsheet']
```


## Trees and Graphs

Library: **annoy** by [Spotify](https://github.com/spotify/annoy) and it's implementation in gensim \
Dataset: [Corpus of English Sayings and Phrases](https://www.kaggle.com/bryanb/phrases-and-sayings) \
Task: Find Similar English Sayings and Phrases

```
Approximate Neighbors for the phrase: Act the giddy goat

Magical realism
Fits and starts
Faint-hearted
Has the cat got your tongue?
Ace in the hole
Knock off
Bite the dust
Game is afoot - The 
Johnny on the spot
Charm offensive
House divided against itself cannot stand - A 
```

## Hierarchical Navigable Small World Graphs

Library: [**nmslib**](https://github.com/nmslib/nmslib) \
Dataset: [Movielens](https://www.kaggle.com/grouplens/movielens-20m-dataset?select=movie.csv) \
Task: Recommendation Engine of Similar Movies based on tags

```
Similar movies for Dangerous Minds (1995)
['Cry, the Beloved Country (1995)',
 'Is Anybody There? (2008)',
 'Little Lord Fauntleroy (1936)',
 "Matthew's Days (1968)",
 'The End of the Tour (2015)',
 'The Old Maid (1939)',
 'Babylon XX (1979)',
 'The Sea Vultures (1915)',
 'The Monastery of Sendomir (1920)',
 'Night Editor (1946)']
```

# HW5