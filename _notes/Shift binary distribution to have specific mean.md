---
title: Shift binary distribution to have specific mean
tree_state: 🌱
---

Programmatically we can find a value such that if we add it to the distribution of scores and apply the sigmoid, we get the desired mean for the sample  

```
def sigmoid_adjustment_to_get_desired_mean(x_series, desired_mean):  
    """ Find a solution for sigmoid adjustment using the Newton-Raphson method """  
  
 # Define a function that we are trying to minimize_outcome def f(x):  
        return (pd.Series(sigmoid(x_series + x))).mean() - desired_mean  
        # return ((pd.Series([sigmoid(z + x) for z in x_series])).mean() - desired_mean)  
  
 # Find the adjustment to add to the original values return optimize.newton(f, 0.1)
 
 ```