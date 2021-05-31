---
layout: page
title: Projects
---

* TOC
{:toc}


##  Legal Probabilism BNs with `R` ([github](https://rfl-urbaniak.github.io/LegalProbabilismBNs/))


`R` implementation (with `bnlearn`) of bayesian network methods for criminal evidence evaluation, using the examples  [Marcello Di Bello](https://www.marcellodibello.com/) and I used in our **Legal Probabilism** entry in the *Stanford Encyclopedia of Philosophy*.

- Directed Acyclic Graphs construction for various evidence idioms (hypothesis-evidence, multiple pieces of evidence, measurement error, synthesis nodes, evidence accuracy, opportunity, alibi, dependency between items of evidence, mixed DNA evidence evaluation).
- Integration of DAGs with conditional probability tables.
- Conversion to junction trees, calculation of priors.
- Updating a BN with new evidence, calculation of posterios.
- Propagating new information and converting a junction tree back to BN.
- A case study with a BN for the [Sally Clark case](https://en.wikipedia.org/wiki/Sally_Clark).
- Visualisation of marginal probabilities.
- Some mathematical background explained.


<p float="left">
  <img src="../images/SCpriors.jpeg" width="450" />
  <img src="../images/SCposterior.jpeg" width="450" />
</p>


## MC in backtesting of optimized trading strategies

Implementation in R of Monte Carlo methods for gauging uncertainty in algorithmic trading strategy evaluation. Illustrates how correcting for multiple testing in optimization can undermine claims to significance.




[DOCUMENTATION UNDER CONSTRUCTION]





## Short-term impact of personal attacks on Reddit user activity

In cooperation with [Samurai Labs](https://www.samurailabs.ai/), we tracked 148,317 users and identified personal attacks among 182,528 posts and comments using their high precision software. I analyzed the data from three perspectives: (i) classical statistical methods, (ii) Bayesian estimation, and (iii) model-
theoretic analysis with hurdle and zero-inflated models. They agree: personal attacks decrease the victims' activity.


[DOCUMENTATION UNDER CONSTRUCTION]




##  Bayesian estimation of multi-class bias in word2vec embeddings


We propose Markov chain Monte Carlo methods to supersede cosine-distance-based bias measures such as WEAT and argue that the resulting
picture is not as clear as it initially might have seemed.

[DOCUMENTATION UNDER CONSTRUCTION]




## Probabilistic coherence measures over bayesian networks

Algorithms for calculating main existing coherence measures over bayesian networks, with a new method essentially relying on the causal structure, implemented in R, building on bnlearn, with application to multiple counterexamples to earlier proposals.



[DOCUMENTATION UNDER CONSTRUCTION]

## Long-term impact of personal attacks on Reddit user activity

Another cooperation with [Samurai Labs](https://www.samurailabs.ai/). Methods for multiple time series with covariates deployed to study the impact of personal attacks on
25k users of Reddit over 10 weeks.
