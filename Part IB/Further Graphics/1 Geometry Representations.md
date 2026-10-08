#### Parametric curves and surfaces
Surfaces can be represented as a map from a 2D plane to a surface in 3D. Generalised, it can be a map from an m-dimension space to an n-dimensional space, thus m degrees of freedom with the object embedded in an n-dimensional space

For example, a planar curve can be represented with $m=1,n=2$. 
The position on the curve is $\mathbf{p}(t)=(x(t),y(t))$ where $X\subseteq \mathbb{R}^m,Y\subseteq \mathbb{R}^n$

Bezier curves are a weighted combination of basis functions. The weights are vectors.
$$\mathbf{p}(t)=\sum^n_{i=0}\mathbf{p}_{i}B^n_{i}(t)$$
$$B_{i}^n(t)={{n}\choose{i}}t^i(1-t)^{n-i}$$
