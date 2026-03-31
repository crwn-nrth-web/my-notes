---
title: Bayesianism
draft: false
tags:
  - philosophy
---
[[alternative-to-Bayesianism]]
It is a theory based in mathematics and is about how to evaluate how a piece of evidence supports a theory in terms of probability

The main idea is that if there is uncertainty in a hypothesis, evidence can raise or lower the probability of the hypothesis
$$P(h|e) = \frac{P(h) \times P(e|h)}{[P(h) \times P(e|h)] + [P(\tilde{h} ) \times P(e|\tilde{h})]}$$
- $P(h)$ = **prior probability** = probability of hypothesis without considering the evidence e 
- $P(e|h)$ = **likelihoods of evidence in theory**
- $P(h|e)$ = **posterior probability** = probability of hypothesis in light of evidence e

We can say that evidence $e$ confirms hypothesis $h$ if $P(h|e) > P(h)$ i.e. e confirms h if it makes h more probable than it would otherwise be.

According to the **subjectivist interpretation**, probabilities are degrees of belief. A probability measures a person's degree of confidence in the truth of some proposition. So each person can have different values of probabilities for the same hypothesis and evidence based on their degree of belief.

According to Bayesianism, a rational agent will update their degrees of belief so that their new overall confidence in h is derived from their old value of $P(h|e)$ i.e. $P_{new}(h) = P_{old}(h|e)$. $P_{new}(h)$ becomes the agent's new prior probability for h, for use in assessing how to react to the next piece of evidence.

Applying this to Bayesianism:
- we see a person's degree of belief by seeing their gambling behavior = which bets would they accept and which they would reject
- A person's *subjectively fair odds* is the odds on a given bet such that the person would be equally willing to take either side of the bet
	- generally, to bet on h at odds of $X: 1$ is to be willing to risk losing $\$ X$ if h is false and in return gain $\$ 1$ if h is true. So, a large X corresponds to a lot of confidence in h. The subjectively fair odds for a bet on h are $X:1$ and that person's degree of belief in h is $X/(X+1)$

Degree of belief for h will be related to your degree of belief for other propositions as well, such as $h \& j$ or $not-h$. So, a person’s belief system at a particular time can be described as a network of subjective probabilities. According to Bayesianism, all of life is a series of gambles, in which our behavior manifests our bets about what the world is like.

Bayesians claim to give a theory of when a person’s total network of degrees of belief is “coherent,” or rational. They argue that a coherent set of degrees of belief has to follow the standard rules of the mathematics of probability.

**Axioms of Bayesianism**:
1. All probabilities are numbers between 0 and 1 (inclusive)
2. if a proposition is a tautology, then it has a probability of 1
3. if h and $\tilde{h}$ are exclusive alternatives (they cannot both be true) then $P(h \text{ or } \tilde{h}) = P(h) + P(\tilde{h})$
4. $P(h|j) = P(h \& j)/P(j)$ provided that $P(j) > 0$ 

#### convergence or the "washing out" of prior proabilities
Bayesianism argues that although prior probabilities are freely chosen and might be weird initially, the starting point gets “washed out” by incoming evidence, so long as updating is done rationally.

> "Consider two people with very different prior probabilities for h, but the same likelihoods for all possible pieces of evidence (e1, e2, e3 . . .). And suppose the two people see all the same actual evidence. Then these two people’s probability for h will get closer and closer. It can be proved that for any amount of initial disagreement about h, there will be some amount of evidence that will get the two people to any specified degree of closeness in their final probabilities for h." (Theory and Reality, Godfrey-Smith)
#### Bayesianism as a possible solution to Hume's problem of induction
Bayes' theorem can be applied repeatedly i.e. the posterior probability can be plugged in as the new prior probability 

E.g. = $e_1$ = sun rises today, $e_2$ = sun rises yesterday, $e_3$ = . . .

However, Bayesianism does not solve hume's [[Hume-on-the-problem-of-induction|problem-of-induction]] because Bayes' theore is a necessary condition of coherence for a set of probability assignments; it restricts what Pr can be assigned to one proposition given that assigned to others. But nothing prevents a person from making two coherent probability assignments, one before the  evidence comes in (t0) and one afterwards (t1)

I could ‘defy’ Bayes theorem by changing all the related probabilities at t1 to achieve coherence. E.g. $P(h \text{ at } t_1) ≠ P(h|e \text{ at } t_0)$
