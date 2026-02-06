## Feature Scaling

### What is a Machine Learning Model?

A **machine learning model** is a mathematical function that we train by feeding it data.  
During training, the model automatically adjusts its internal parameters using a learning algorithm to reduce prediction error.
After training, the model becomes a **trained model** with optimized parameters, which is then used on **new (unseen) data** to make predictions.

---

### What is Feature Scaling?

**Feature scaling** is the process of adjusting input features so that no single feature dominates the learning process due to its scale.

It helps:
- Prevent the model from becoming biased toward large-magnitude features
- Improve training stability and convergence
- Ensure the algorithm learns the true importance of each feature

---

Without scaling:
- Learning becomes unstable  
- Training becomes slow  
- The model becomes biased toward large-scale features  
- The best solution becomes harder to reach


## Mean and Standard Deviation

**Mean** is the average value of a feature.  
**Standard deviation (std)** shows how much the values vary from the average.

If the standard deviation is small, values are tightly packed around the mean.  
If it is large, values are more scattered.

Standard deviation helps ensure fair treatment for every feature during training.

### Steps to Compute Standard Deviation

1. Compute the difference of each value from the mean  
2. Square the differences  
3. Take the mean of the squared differences  
4. Take the square root  

Each feature has its own mean and standard deviation.

## What is scaling?

Feature scaling makes all features operate on similar ranges so that no feature dominates the learning.

A common method is **standardization**, using this formula:

(x − μ) / σ

where:
- μ = mean of the feature
- σ = standard deviation of the feature

## Why models get biased without scaling

If one feature has large values (e.g., income in thousands) and another has small values (e.g., age in years), the model will focus too much on the larger one even if it is not more important.

Scaling fixes this problem.

## Real example

Without scaling:
- income ≈ 50000
- age ≈ 22

With scaling:
- income ≈ 0.8
- age ≈ -0.3

Now the model learns from both fairly.
