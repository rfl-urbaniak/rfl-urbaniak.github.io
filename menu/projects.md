---
layout: page
title: Projects
---

##  Legal Probabilism BNs [(github site)](https://rfl-urbaniak.github.io/LegalProbabilismBNs/)


`R` implementation of bayesian network methods for criminal evidence evaluation, using the examples  [Marcello Di Bello](https://www.marcellodibello.com/) and I used in our **Legal Probabilism** entry in the Stanford Encyclopedia of Philosophy.

- Directed Acyclic Graphs construction for various evidence idioms (hypothesis-evidence, multiple pieces of evidence, measurement error, synthesis nodes, evidence accuracy, opportunity, alibi, dependency between items of evidence, mixed DNA evidence evaluation).
- Integration of DAGs with conditional probability tables.
- Conversion to junction trees, calculation of priors.
- Updating a BN with new evidence, calculation of posterios.
- Propagating new information and converting a junction tree back to BN.
- A case study with a BN for the [Sally Clark case](https://en.wikipedia.org/wiki/Sally_Clark).
- Visualisation of marginal probabilities.
- Some mathematical background explained.


<p float="left">
  <img src="../images/SCpriors.jpeg" width="320" />
  <img src="../images/SCposterior.jpeg" width="320" />
</p>
