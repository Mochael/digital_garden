---
title: What is independent component analysis
tree_state: 🌱
---
- Assume there exist true independent sources $s_1(t), s_2(t)$ that are dependent on time.
- Assume that the observed signals $x_1(t), x_2(t)$ are linear combinations of the underlying true sources.
$$
\begin{bmatrix} 
x_1(t) \\
x_2(t)
\end{bmatrix} 
= 
\begin{bmatrix} 
a_{11} & a_{12}\\
a_{21} & a_{22}
\end{bmatrix}
\begin{bmatrix} 
s_1(t) \\
s_2(t)
\end{bmatrix} \implies X(t) = A S(t)
$$

The goal is to find a linear transformation $L$ so that we can recover the original sources. We can acheive this by finding $L$ such that $L X(t) = S(t)$, where $L$ is our best guess at the inverse of the mixing matrix $A$.

The results of ICA compared to PCA are shown here.
[pca_vs_ica](../search_pics/pca_vs_ica.png)