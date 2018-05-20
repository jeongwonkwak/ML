# Naive Bayes
- A classification algorithm that draws on conditional probability

## Bayes Theorem
- Allows us to calculate a posterior probability from a prior probability
- Here is the formula. Note that the denominator is simply P(R): https://cl.ly/001p0y3n1e2l

## Naive Bayes
- We will assume that our probabilities are independent, which is the 'naive' part of naive bayes. Specifically, we assume that P(A and B) = P(A) * P(B)
- In practice, although naive, this makes the algorithm very fast
- P(A | B) * P(B) = P(B | A) * P(A), and we can drop the P(B) to find that P(A | B) is proportional to P(B | A) * P(A). https://cl.ly/0f0s2V3a0Q3V
- We can then break the formula in the link above into this by following the naive assumption: https://cl.ly/422F0o3c2n1m
- Given that we then have the proportional probabilities, we can normalize them to get the probabilities of each case. 

### A General Approach to the Naive Bayes Algorithm
- Say that we want to find the probability that an email is spam. 

#### Steps:
- 1) Find a list of feature words that indicate whether something is spam ('easy', 'money', 'cheap', for e.g.)
- 2) Flip the event and conditional: P(Spam | 'easy', 'money', 'cheap') is proportional to P('easy', 'money', 'cheap' | Spam) * P(Spam)
- 3) Make the naive assumption: P('easy', 'money', 'cheap' | Spam) = P('easy' | Spam) * P('money' | Spam) * P('cheap' * Spam)
- 4) Do this for both P(Spam | words) and P(Not Spam | words) and get two values, then normalize the results to get the true probabilities

### Generalizing to Higher Classes
- Generalizing to higher dimensions is pretty trivial with naive bayes: we basically just find the conditional proportional probability of each class and normalize them to get the true probability.
