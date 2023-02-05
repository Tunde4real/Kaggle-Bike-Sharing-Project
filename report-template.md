# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Ibrahim Aderinto

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
First of all, I had to use .predict method as opposed to the .evaluate method thought in the lesson. This outputed a pandas series object which acted like a list of values. So I had to add this list of values to my submission dataframe as it's new count column. I then converted the submission dataframe to a csv file, then uploaded to kaggle (I had problems with running kaggle in the notebook initially). 

### What was the top ranked model that performed?
WeightedEnsemble_L3

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
EDA showed the distribution of values, which helped me determine that some columns are of purely categorical data, and some were of no importance like the minute and second column I created.
Having converted the datetime column to a pandas datetime column type, I created year. month, day, hour, minute, and second column off the datetime column for both train and test datasets.

### How much better did your model preform after adding additional features and why do you think that is?
Very much! It massively improved my kaggle score from 2.07388 to 0.63169.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
I tried tuning twice and at first, I got an improvement of about 0.07. I tried again and only got about 0.03 improvement.

### If you were given more time with this dataset, where do you think you would spend more time?
Fine tuning the model

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|time_limit|num_stack_levels|keep_only_best|score|
|--|--|--|--|--|
|initial|120|None|False|2.07388|
|add_features|120|None|False|0.63169|
|hpo|300|3|True|0.53208|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](model_test_score.png)

## Summary
The project started off with setups on kaggle and sagemaker, followed up with breif visualizing the data and training of the models.
