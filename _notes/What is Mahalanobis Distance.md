---
title: What is Mahalanobis Distance
tree_state: 🌱
---

https://en.wikipedia.org/wiki/Mahalanobis_distance

$$d(\vec{x}, \vec{y})=\sqrt{(\vec{x}-\vec{y})^{T} S^{-1}(\vec{x}-\vec{y})}$$

- The Mahalanobis distance is the distance of a point from the center of mass divided by the width of the ellipsoid in the direction of that point.
- Ellipsoid is constructed by covariance matrix to account for correlations between features

## Suppose I wanted to calculate the Mahalanobis nearest neighbor
1. Calculate covariance matrix between all features which will allow you to scale your multidimensional ellipsoid
2. Then calculate the Mahalanobis distance between your point of interest and every other point
3. Report the $k$ closest points