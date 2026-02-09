Sometimes a review will be neither positive nor negative - a third, neutral, class can be introduced. However, there could be subcategories in neutral reviews - e.g. lukewarm reviews and pro-con reviews

Human judgement is the only empirically available source of truth in decisions which are influenced by subjective judgement.
- Something is true if several humans agree on their judgement, independently of each other
- The more they agree, the more true it is

#### Agreement metrics
$$\bar{P_{a}}=\frac{1}{N}\sum ^{N-1}_{i=0}\left( \frac{\text{observed rater-rater pairs in agreement on item i}}{\text{possible rater-rater pairs}} \right)$$
- N is the number of items
- Pairwise observed agreement $\bar{P}_{a}$: average ratio of observed to possible rater-rater agreements

- We need to calculate the proportion of a rater-rater pair agreement that we would expect by chance $\bar{P_c}$
- Our model of chance is then 2 independent raters choosing a class blindly
$$P(\text{both neg or pos})=P(\text{positive})^2+P(\text{negative})^2$$

#### Fleiss' Kappa
- Measures the reliability of agreement between a fixed number of raters when assigning categorical ratings
$$\kappa=\frac{\bar{P}_{a}-\bar{P}_{e}}{1-\bar{P}_{e}}$$
- Observed agreement $\bar{P}_{a}$: average ratio of observed to possible pairwise agreements
- Chance agreement $\bar{P}_{e}$: sum of squares of probabilities of each category
- Numerator is agreement achieved above chance, denominator is agreement attainable above chance
- If $\kappa$ is 1 then raters are in complete agreement, 0 is no agreement beyond chance
- $\kappa$ can be negative
- Beyond that, there is no universally accepted interpretation
- Generally $\kappa=0.8$ is good agreement
