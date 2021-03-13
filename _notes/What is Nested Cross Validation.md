---
title: What is Nested Cross Validation
tree_state: 🌱
---

Suppose we are given a dataset, a bunch of possible learners and hyperparameters, and we want to know what the best learner and hyperparameters are as well as an estimate for how well the best model (with best hyperparameters) will perform. The most common approach is to divide data into 3 sets: a training set, a validation set, and a testing set. We train all our models with their possible hyperparameters on the training set, select the model and hyperparameters that has the lowest error when predicting the outcomes on the validation set, and then estimate the performance of this model on the testing set. This approach works well. However, what if we don't have a good way to split the data into these 3 sets without making a certain set biased or we have only a small amount of data that we don't want to segment further into 3 separate classes. Another possible approach is to use nested cross validation.

## Steps for Nested Cross Validation
1. Divide the dataset into $K$ cross-validation folds at random.
2. Do the following for each fold $k=1,2, \ldots, K$ (this is the outer loop used for the evaluation of the model with selected hyperparameter)
	1. Set the testing set to be fold $k$
	2. Set all the data except those in fold $k$ to be a set we will call **trainval** (composes both the training and validation sets)
	3. Randomly split **trainval** into $L$ folds
	4. For each fold $l=1,2, \ldots, L$ (this is the inner loop used for hyperparameter tuning)
		1. Let the validation set be fold $l$
		2. Let training set be all the data except those in testing or validation
		3. Train with each hyperparameter on the training set, and evaluate it on the validation set. Keep track of the performance metrics.
	5. For each hyperparameter setting, calculate the average metrics score over the $L$ folds, and choose the best hyperparameter setting.
	6. Train a model with the best hyperparameter on **trainval**. Evaluate its performance on the testing data and save the score for fold $k$.
3. Calculate the mean score over all $K$ folds, and report it as the generalization error.