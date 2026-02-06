#### Overtraining
- Overtraining is when you think you are making improvements because measured performance goes up
- but in reality you are making the classifier worse because it generalises less well to real unseen data
- Also known as overfitting or type III errors
	- Choosing the test falsely to suit the significance of the sample
- Commonly seen through time effects (opinions changing over time)
Repeated use of test data leads to overtraining.

To avoid overtraining use large amounts of test data. You can detect overtraining by inspecting the most characteristic features for each class. You may find features that are unlikely to generalise.

#### Cross-validation
- Hard to avoid getting new test data each time
- As much training data as possible needs to be used
- We can avoid testing on the training set by using every bit of training data for testing, by iterating the test 

##### N-fold cross-validation
- Split data randomly into N equal sized folds
- For each fold X, use all other folds for training, test on fold X only
- The final performance is the average of the performances for each fold.
- If all splits perform equally well, this is a good sign.
$$\text{var}=\frac{1}{n}\sum^n_{i}(x_{i}-\mu)^2$$
$x_i$ - the score of the $i^{th}$ fold
$\mu$ - the average of the scores

##### Significance testing under N-fold cross-validation
- Compare two systems under N-fold cross-validation with each other
- Consider all of the X test folds together as one overall experiment, not as X different experiments
- Perform one test, counting positives, negatives and null out of the total number of mini events
- We don't care which fold a mini-event came from, as there won't be any repetition.

##### Variations
- Stratified cross-validation is a special case where the split is done in such a way it mirrors the distribution of classes observed in the overall data
- Jack-knifing is an extreme case of folding where you fold on individual data points
- Dependency-sensitive cross-validation is when you fold in such a way that known characteristics of data are isolated in a fold.

Cross validation gives some safety from overtraining but still uses data that is in some sense "seen". This means it is not good for incremental small improvements.

##### Validation corpus
- It is never used in training or testing
- We can use it to set parameters in any algorithm, before we start with training or testing
- It can also be used as a stopping criterion for feature engineering
	- We can stop fiddling with the features when the result on the validation corpus starts decreasing
- Then, and only then. do we measure on the test corpus (once)
