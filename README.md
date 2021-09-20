# Song Recommendation System - Readme
## About The Project

This was a group project in which we attempted to build a Song Recommendation System using the Million Songs Dataset Subset. The Million Songs Dataset Subset consists of 10,000 songs with observations containing a User, Song, and Listen Count. The goal of this project was to develop a recommendation system leveraging implicit data. Two approaches were taken:

  * Alternating Least Squares Matrix Factorization
  * Neural Network with Bayesian Personalized Ranking

The models were both evaluated on metrics including hit ratio, mean average precision, and mean average recall. This iteration of the project did not address the cold-start problem, although it will be addressed in future iterations. The models were both trained and evaluated on a subset of the training and test data that consisted of users who had at least 5 observations for the ALS model and at least 3 observations in the BPR model. The future iterations of this project will attempt to use the full Million Songs Dataset to obtain better and more accurate performance in the models. Additionally, future iterations will also include other approaches for recommendations such as Neural Collaborative Filtering.

### Built With

* [Jupyter Notebooks](https://jupyter.org/)
* [Python 3.7.4](https://www.python.org/)
* [Implicit Package](https://implicit.readthedocs.io/en/latest/#)
* [Keras](https://keras.io/)
* [Google Colab](https://colab.research.google.com)


### Prerequisites

Raw Data:
* [Song Data](http://millionsongdataset.com/)
* [User Data](http://millionsongdataset.com/tasteprofile/)
* [Map Song and User Data](https://www.kaggle.com/c/msdchallenge/data?select=taste_profile_song_to_tracks.txt.zip)


## Getting Started

The final ALS model can be run on new data and evaluated using the ALS_Evaluation notebook. The ALS_Evaluation notebook only evaluates on data where at least 5 observations exist per user. The evaluation consists of a comparison of recommending the top 10 most popular songs vs the top 10 model recommended songs. A stratified 5 fold cross validation is performed and the results are compared on the metrics. A paired t-test is also conducted to check for statistical significance in the results. To evaluate the model on new data, line 5 in the notebook must be changed to import the new data into the standardized_df.

The BPR model requires loading the notebook bpr04.ipynb on Google Colab. In Google Colab, a GPU must be used by selecting Runtime  ->Change Runtime Type -> Hardware Accelerator -> GPU. Once the GPU is selected, the dataset to evaluate the model on can be imported into the Jupyter notebook by changing the directory on line 26 and indicating the filename on line 27. The model is evaluated based on the training and testing loss observed and the hold out hits which is the hit ratio on the test set.


## Usage

### To run entire project

1. Obtain the raw data and save on local drive
2. Open loading_trial01.ipynb, change directory paths for importing and exporting, and run notebook.
3. Using the exported files from step 2, open preprocessing_sprint.ipynb, change directory paths for importing and exporting, and run notebook.
4. Using the files obtained from step 3, open Matrix Factorization Model.ipynb and bpr04.ipynb. Change directories to point to files from step 3 and alter model parameters to tune. The notebook bpr04.ipynb should be run in Google Colab with a GPU. In Google Colab, a GPU can be used by selecting Runtime -> Change Runtime Type -> Hardware Accelerator -> GPU. Select a final model based on performance.
5. Change directory paths and use final model parameters in ALS_Evaluation.ipynb. Run notebook and observe results to see model performance relative to recommending the top 10 most popular songs.

### To run on new data

1. In order to use the ALS model on new data, the directory paths can be changed in ALS_Evaluation.ipynb and run. The model can then be evaluated based on the paired t-test and compared against recommending the top 10 most popular songs.

2. In this iteration of the project, the BPR model training and evaluation are performed on the same dataset. In order to use the BPR model on new data, the directory paths can be changed in the bpr04.ipynb and the notebook can be run in Google Colab with a GPU. In Google Colab, a GPU must be used by selecting Runtime -> Change Runtime Type -> Hardware Accelerator -> GPU. The model will be trained on the new data and the hold out hits(i.e. hit ratio) can be evaluated for model comparison.


## Team Members

* Jason Miller


