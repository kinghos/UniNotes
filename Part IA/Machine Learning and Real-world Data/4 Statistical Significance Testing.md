- Need a way to show that the smoothed system is significantly better
- Null Hypothesis: two result sets come from the same distribution
	- System 1 is equally as good as system 2
- Rejecting the null hypothesis means showing that the observed result is unlikely to have occurred by chance
- First choose a significance level $\alpha$
- Then try and reject the null hypothesis with confidence $1-\alpha$

#### Sign Test
- The sign test uses a binary event model
- Events correspond to documents
- Events have binary outcomes:
	- Positive: System 1 beats System 2
	- Negative: System 2 beats System 1
	- Tie: Equally well
Binomial distribution used
A two tailed test is more effective

#### Errors
- Type 1 - the test declares a difference when it doesn't exist
	- $\alpha$ is the probability of this
	- $1-\alpha$ is the specificity of a test
- Type 2 - the test declares no difference when it does exist
- $\beta$ is the probability of this
- $1-\beta$ is called the power of a test

Power issues can be fixed by using more data, or a more powerful test.
Specificity issues should never happen, meaning the test was applied incorrectly or the wrong test was used.
Common to ignore ties. Here ties will be treated by adding 0.5 events to the positive and 0.5 events to the negative side (and rounding up at the end)

Effect size = difference in measured results between systems
Significance = binary flag
Report both, separately but in neighbouring tables
Statements about differences should mention significance