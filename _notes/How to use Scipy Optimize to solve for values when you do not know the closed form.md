---
title: How to use Scipy Optimize to solve for values when you do not know the closed form
tree_state: 🌱
---

How does Scipy Optimize Newton Work?

Suppose we want to figure out some values $x_0$ such that the value of some function $f(x_0)$ approaches $z$. 

We can do this with `scipy.optimize.newton`.
- First, you need to create a loss function which could essentially be the difference between $f(x_0)$ and $z$ (the function and your desired output)

`scipy.optimize.newton(func, x0, fprime=None, args=(), tol=1.48e-08, maxiter=50, fprime2=None, x1=None, rtol=0.0, full_output=False, disp=True)`
- The most important inputs you need to run an optimizer is the loss function `func` and the initial guess for the optimal $x_0$ (i.e. $x^*_0$)
- Inputting the first and second derivatives allow you have a quicker optimization (by using a different method in the backend of `scipy.optimize`) but the optimization can still be run (albeit worse performing) without these inputs


Here is an example where we are trying to find some value $x_0$ that when multiplied to the function $e^{2x}log(2x+1)$ will have the mean of the data equal to $7$.

```
from scipy import optimize

# Dataset
x_series = np.arange(-100,100)
# Value of z
desired_output = 7

def loss_function(x):
	return np.mean(xe^{2x_series}log(2x_series+1)) - desired_output

optimize.newton(loss_function, 0.1)
```