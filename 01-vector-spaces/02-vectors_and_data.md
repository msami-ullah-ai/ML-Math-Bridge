# Vectors and Data

In machine learning, every data point is treated as a **vector**.

For example, in the Iris dataset, each flower is stored as:

[sepal length, sepal width, petal length, petal width]

So one flower becomes a vector with 4 numbers.  
The dataset becomes a collection of such vectors.

## Features vs Labels

**Features** are the input values (measurements of the flower).  
**Label** is the output we want to predict (the flower species).

Features form the vector. Each column in a matrix represents a feature  
Label is what the model learns to predict.

So dataSet includes features+label

## Why we treat data as vectors

Vectors allow us to:
- compare data points
- scale features
- apply mathematical operations
- train models efficiently

Most ML algorithms are built on vector operations, so converting data into vectors is the first step in learning.
