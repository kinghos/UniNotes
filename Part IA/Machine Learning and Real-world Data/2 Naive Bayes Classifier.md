Problems with lexicons:
- Limited to human intuition
- Static and cannot react to language change (e.g. "sick!")
- Requires many hours of human labour to build

#### Machine Learning
- A program that learns from data
- Adapts its behaviour after having been exposed to new data
- ...and does so without explicit programming
- ...implicitly, from data alone

- Features are easily observable properties of the data
	- The features of a movie review will be the words they contain
- Classes are the meaningful labels associated with the data which are not easily automatically observable
	- In our case the classes are the two sentiments: pos and neg
- Classification is a function that maps from features to a target class
	- In our case, from the words from a review to a sentiment

Given C which is the classes (here $C=\{ pos, neg \}$) and O which is the observed features (here a set of words) we get a probabilistic classifier:
$$P(pos|w_{1},w_{2}\dots w_{n})$$
A single class is decided by choosing the one with the highest probability given the features
$$\hat{c}=\text{argmax}_{c\in C}P(c|O)$$
#### Naive Bayes Classifier
Simple probabilistic classifiers based on applying Bayes' theorem
$$P(c|O)=\frac{P(c)P(O|c)}{P(O)}$$
$c_{NB}=\text{argmax}P(c|O)=\text{argmax}P(c|O)\frac{P(c)P(O|c)}{P(O)}=\text{argmax}P(c)P(O|c)$
We can remove $P(O)$ because it is constant during a given classification and does not affect the result of argmax

Naive Bayes makes a strong (naive) independence assumption between the observed features. Hence,
$$c_{NB}=\text{argmax}P(c)\prod^n_{i=1}P(w_{i}|c)$$

In the training phase, we collect whatever information is needed to calculate $P(w_i|c)$ and $P(c)$
In the testing phase we apply the above formula to derive $c_{NB}$, the classifiers decision.
This is supervised ML because you use information about the classes during training.

Training - making observations about some known data set
Testing - the process of applying the knowledge obtained in the training stage to some new, unseen data
**Never test on data that a system is trained on**
