#### Models
A deterministic model is fixed - this might for instance be used by a physical scientist when they do not care about noise or randomness.
A probability model introduces noise in order to be more accurate to the data presented. It informs the fitting routine how much attention to pay to outliers

#### Machine Learning vs Data Science
Machine learning is based on the idea of writing a probability model, and fitting the model from data.

Machine learning is interested in application, while data science is interested in learning about the dataset

#### Views of probability models
- Code e.g. NumPy 
- Random variable notation e.g. $\text{Temp}_{i}\sim \alpha \sin(t_{i})+\text{Normal}(0,\sigma^2)$

- Convention states that uppercase letters are random variables and lowercase are constants or data points
- $X_{1},X_{2}\sim U[0,1]$ declares two independent variables
- $(Y,Z) \sim\dots$ indicates that $Y$ and $Z$ 
- Saying two variables are independent implicitly assumes parameters are true
- $=$ means "always equal when I run it" whereas $\sim$ means they are distributed the same