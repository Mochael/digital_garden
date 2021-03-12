---
marp: true
title: data science overview
tree_state: 🌱
---

# Data Science Overview

Walk you through the steps of what the data science process looks like from start to finish.

---

## Accessing and Determining Relevant Data
- Everyone's data is different and many companies use different methods of storing their data, even if they have extremely similar underlying data.
- To solve their problems, we most likely want a subset of the data that they have available, which is stored all over the place

---


## Extract, Transform, Load (ETL) Process: Data Engineer
- Spark
- SQL
- Data lake vs data warehouse
- AWS (S3, Glue, Redshift)
  - Glue to piece together your various data from S3. Redshift can be used if you have structured data stories that you want to be able to quickly query from. Can also use glue to write to Redshift datawarehouse

---

## Time for Exploratory data analysis (EDA): Data Analyst
- Python/R
- Jupyter Notebook/Databricks
- Tableau/Excel
- Communication with ETL throughout rest of stages to talk about new features needed, errors, etc.

---

## Statistics Fundamentals

$Y_i = f(X_i) + \epsilon_i$
- Frequentists vs Bayesian approach (Bayes rule and posterior distribution)
- Bias-Variance trade off
- Curse of dimensionality
- Deep learning
  - Pytorch/Tensorflow
- Hypothesis testing

Most important thing to be aware of: what assumptions am I making?

---

## Modeling: Data Scientist
- Train/Validation/Test Split
  - train on train, select model/hyperparameters on val, evaluate on test (should be holdout)
- Supervised/Unsupervised
  - Supervised: regression/classification
  - Unsupervised: clustering, generative modeling
- Prediction/Inference
- Regression/Classification
  - Regression: MSE
  - Classification: Accuracy, ROC Curve

---

## More on Modeling
Types of Problems:
- Computer Vision
- NLP
- Time series forecasting

Services for Heavy Computation
- AWS EC2
- Databricks

---

## Integration and Implementation: Machine Learning Engineer
Tools for Testing and Integration
- Writing tests and mocking servers
- Git:
  - GitHub actions and workflows
- CI/CD (Continuous Integration and Deployment)

Services to Train/Host Model
- AWS Sagemaker (preconfigured environments) or AWS EC2 (compute power, so you need to set up your own environment)

---

## Deployment

Infrustructure Stuff
- Terraform
- Docker
  - AWS ECS (Elastic Container Service)
- APIs (communicating with frontend) and AWS API Gateway 
- AWS lambda