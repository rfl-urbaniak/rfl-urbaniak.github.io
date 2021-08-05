---
layout: post
title: "False positives in DNA identification 4"
author: "Rafal Urbaniak"
---

Last time we derived one formula for the impact of false positive probability on the value of DNA evidence. Today, we'll look at seemingly different formula to get a better perspective. Buckleton, Bright, & Taylor (2018) give a formula for the impact of errors on likelihood ratio different from the one we discussed before. Since the derivation is simpler and it turns out that in fact this is simply a more general formula, of which the one we already discussed is just a particular instance, it worth taking a look.

First, Buckleton et al. (2018) make the conceptual distinction between the probability that an error occurs (![E](https://latex.codecogs.com/png.latex?E "E")) and the probability that a match is reported if it does. In terms of our notation, we have:

\begin{align*}
e & = \mathsf{P}(E) = \mathsf{P}(E \vert S) = \mathsf{P}E \vert \n S)
\end{align*}

That is, we denote the probability of error as $e$, and we assume it doesn't depend on whether the prosecution hypothesis is true (whether the suspect is the source).


Separately, the formula includes the probability of a reported match if an error occurs, also assumed to be independent of whether the prosecution hypothesis is true:
\begin{align*}
k & =  \mathsf{P}(R \vert E, S) = \mathsf{P}R \vert E, \n S)
\end{align*}
\noindent Further, it is assumed that the probability of false negatives is zero ($\mathsf{P}(R \vert S, \n E) =1$) and the probability of reported match if no error occurs and the defense hypothesis is true is RMP ($\mathsf{P}R \vert \neg E, \neg S)=RMP$).





Buckleton, J. S., Bright, J.-A., & Taylor, D. (2018). *Forensic dna evidence interpretation*. CRC press.
