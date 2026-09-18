# Rice Variety Classification

I made this project for the B104 Artificial Intelligence & Machine Learning class at Gisma University.

# Project overview

Basically, I was just trying to see if a rice processor can actually tell the difference between Cammeo and Osmancik rice grains just by looking at seven numbers about their shape and size. The whole point is to help sort them out before packing so there aren’t mix-ups, I guess.

It’s just a binary classification. I tried to keep the notebook in some order.

1. Data Exploration
2. Data Pre-processing
3. Feature Engineering
4. Model Training
5. Model Evaluation
6. Final Thoughts

# Dataset

The dataset contains 3,810 rice grains and the following seven predictor features:

* Area
* Perimeter
* Major Axis Length
* Minor Axis Length
* Eccentricity
* Convex Area
* Extent

So the main thing we’re trying to predict is if the rice is Cammeo or Osmancik. I split the data, like 80% for training and 20% for testing, before doing anything else.

# Sources:

* Rice Cammeo and Osmancik on Kaggle
* Rice dataset in the UCI Machine Learning Repository

# Methods

I tried out a few things, like just picking the most common class, then logistic regression and K-nearest neighbours. I did the standardisation inside the pipeline and used five-fold cross-validation and grid search to pick the best settings with macro-F1. After that, I checked how the model did on the test set.

Results

In the end, logistic regression with C=100 worked best after standardising everything.

* Validation macro-F1: 0.9297
* Test accuracy: 92.91%
* Test macro-F1: 0.9286
* Test ROC-AUC: 0.9823
* Test errors: 54 out of 762 grains

The results look good for a pilot, but the problem is that it's not sure if it’ll work with rice from other suppliers or different harvests or if someone uses different equipment. Probably should test with new data before actually using it for real.

# Repository contents

* ML_Project.ipynb — complete analysis, code and saved outputs
* ML_Project.html — rendered notebook for viewing and submission
* data/Rice_data_type.csv — dataset used by the notebook

# Running the notebook

1. Download or clone the complete repository.
2. Open ML_Project.ipynb from the project folder.
3. Use a Python 3 environment with pandas, numpy, matplotlib, scikit-learn and IPython installed.
4. Restart the kernel and run all cells from top to bottom.

The relative dataset path is data/Rice_data_type.csv, so keep the folder structure unchanged.