---
title: "Loss Functions in Linear Regression"
author: "Anjan Mondal"
date: "2025-06-22"
categories: [forecasting, benchmarking, python]
---


In almost every introductory class on Machine Learning, students learn Linear Regression where the task is to try and minimize an error function. The purpose of choosing an error function is to measure how much the model prediction deviates from the ground truth or measurement. 

The most common choice of the loss function is the Root Mean Squared Error **(RMSE)**   
$$  \sqrt{\frac{1}{m}  \sum_{i=1}^m \left(y^{(i)}-f(x)^{(i)} \right)^2}$$
In practice, it is simpler to minimize the 
Mean Squared Error **(MSE)** than the RMSE, and it leads to the same result (because the value that minimizes a function also minimizes its square root).  

There are many possible choices for a cost function.
One naive loss function could be to simply take the difference between the predicted and actual values? The problem is that when we aggregate these errors across multiple examples, some will be positive and others negative. This means they can cancel each other out, giving the illusion of a model that performs well even when it consistently makes large mistakes in both directions.


The Mean of Absolute Error **(MAE)** is also a valid loss function and can be useful in some cases.
$$\frac{1}{m} \sum_{i=1}^{m} \left| y^{(i)}-f(x)^{(i)}\right|$$ 

So what's the reason behind 


There are additional benefits of using RMSE over MAE. In the optimization step, the gradient step would be larger for RMSE than MAE, causing faster convergence for RMSE. With some experimentation, I also found that with the same number of epochs, RMSE parameters are closer to the true optimum than the parameters obtained through MAE.


>	Caveat: With lesser number of features, MAE performs on par with RMSE and it even performs better than RMSE in the presence of outliers.


Plot comparing path of MAE vs RMSE




There’s a more fundamental reason as to why we use RMSE for Linear Regression. Assuming Gaussian noise to the target variables, we can model our Regression problem as such - 


Use MLE to prove


So that was it, the fundamental reason why we use RMSE as the loss in Linear Regression. One might wonder what if the noise isn’t Gaussian. Well we then turn to a class of models called Generalized Linear Models and maybe that’s a post for some other time.





 




Test push
Notes - Experiment with MAE, show the convergence rate and the convergence path.

