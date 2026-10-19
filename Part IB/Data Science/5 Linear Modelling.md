#### Linear models
A linear model is 
- A prediction model, with a response variable and feature variables
- in which the response and the features are numeric
- and the response vector is predicted by a linear combination of known feature vectors weighted by unknown parameters

#### Least squares estimation
The vector of prediction errors is called the residual vector
We can fit the model using least squares estimation. this means finding parameters to minimise mean square error
$$\begin{align}
y&\approx~\beta_{1}e^1 +\dots+\beta_{K}e^K \\
\epsilon&=y-({\beta_{1}}e^1+\dots+\beta_{K}e^K)
\end{align}
$$