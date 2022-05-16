## What is convex function?
In mathematics, a real-valued function is called **convex**, when there are two points above the graph of the function and a line segment is constructed joining those two points, then the line does not lie below the graph.

A function is said to be **convex** if and only if the region above its graph is a **convex set**

### So, what is convex set?

In geometry, a **convex set** is a subset of Euclidean Space, if given any two points in the subset, the subset contains the whole line segment that joins them. Example as shown in below image.

Examples of convex and not convex:

|**Convex**| **Not Convex**|
:---:|:---:
|[![convex.png](https://i.postimg.cc/bNFWG15Z/Convex-polygon-illustration1.png)](https://i.postimg.cc/bNFWG15Z/Convex-polygon-illustration1.png "Convex")| [![not convex.png](https://i.postimg.cc/mZj0svNN/220px-Convex-polygon-illustration2.png)](https://i.postimg.cc/mZj0svNN/220px-Convex-polygon-illustration2.png "Not convex")|

Image source: Wikipedia

## Properties of convex function

1. A convex function refers to a function whose graph is shaped like a cup U
2. A twice differential function of single variable is convex if and only if its second derivate is non-negative. Example: quadratic function (x^2)
3. A strictly convex function has exactly one local minimum point, which is also the global minimum point
4. The sum of 2 convex function is also convex function

## Convex function in ML/DL

A lot of the common loss functions, including the following, are convex functions:

- L2 loss
- Log Loss
- L1 regularization
- L2 regularization

[![nonconvex-function.png](https://i.postimg.cc/QtVthQKj/nonconvex-function.png)](https://postimg.cc/9R5VBqBk "Non convex function")
*Non convex Error function in ML/DL*

The process of using mathematical techniques such as gradient descent to find the minimum of a convex function is known as **convex optimization**. For complete details, refer book here - [Convex Optimization](https://web.stanford.edu/~boyd/cvxbook/bv_cvxbook.pdf)

Many variations of gradient descent are guaranteed to find a point close to the minimum of a strictly convex function.  Similarly, many variations of stochastic gradient descent have a high probability of finding a point close to the minimum of a strictly convex function.

Deep models are never convex functions. Remarkably, algorithms designed for convex optimization tend to find reasonably good solutions on deep networks anyway, even though those solutions are not guaranteed to be a global minimum.