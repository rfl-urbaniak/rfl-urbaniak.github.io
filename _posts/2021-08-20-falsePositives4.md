---
layout: post
title: "False positives in DNA identification 4"
author: "Rafal Urbaniak"
---

Last time we derived one formula for the impact of false positive probability on the value of DNA evidence. Today, we'll look at a seemingly different formula to get a better perspective. Buckleton, Bright, & Taylor (2018) give a formula for the impact of errors on likelihood ratio different from the one we discussed before. Since the derivation is simpler and it turns out that, in fact, this is simply a more general formula, of which the one we already discussed is just a particular instance, it is worth taking a look.

First, Buckleton et al. (2018) make the conceptual distinction between the probability that an error occurs (![E](https://latex.codecogs.com/png.latex?E "E")) and the probability that a match is reported if it does. In terms of our notation, we have:

\begin{align}
e  = \mathsf{P}(E) = \mathsf{P}(E \vert S) = \mathsf{P}E \vert \neg S)
\end{align}

That is, we denote the probability of error as $e$, and we assume it doesn't depend on whether the prosecution hypothesis is true (whether the suspect is the source).


Separately, the formula includes the probability of a reported match if an error occurs, also assumed to be independent of whether the prosecution hypothesis is true:
\begin{align}
k  =  \mathsf{P}(R \vert E, S) = \mathsf{P}(R \vert E, \neg S)
\end{align}
\noindent Further, it is assumed that the probability of false negatives is zero ($\mathsf{P}(R \vert S, \neg E) =1$) and the probability of reported match if no error occurs and the defense hypothesis is true is RMP ($\mathsf{P}(R \vert \neg E, \neg S)=RMP$).


Now the derivation:
\begin{align}
LR  = \frac{\mathsf{P}(R\vert S)}
{\mathsf{P}(R \vert \neg S)}
\end{align}
\begin{align}
 = \frac{\mathsf{P}(R \vert \neg E, S)\mathsf{P}(\neg E \vert S) + \mathsf{P}(R \vert E, S)\mathsf{P}(E \vert S)}
{\mathsf{P}(R \vert \neg E, \neg S) \mathsf{P}(\neg E \vert \neg S) + \mathsf{P}(R \vert E, \neg S)\mathsf{P}(E \vert \neg S)}
\end{align}
\begin{align}
 = \frac{1(1-e) + ke}
{RMP(1-e)+ke}  = \frac{1-e+ke}{RMP  - e\times RMP + ke} \\
 = \frac{1 - (1-k)e}{RMP(1-e)+ke}
\end{align}



Note now that if you think of an error as something that guarantees a mistaken identification, $k$ becomes $1$ and $e$ becomes the false positive rate. On this assumption we have:
\begin{align}
\frac{1 - (1-k)e}{RMP(1-e)+ke}  = \frac{1-e+e}{RMP(1-e)+e}
\end{align}

\begin{align}
 = \frac{1}{RMP - e\times RMP + e} = \frac{1}{1 + e(1-RMP)}
\end{align}

which is the same as the formula obtained by Aitken, Taroni, & Thompson (2003) if we take ![e](https://latex.codecogs.com/png.latex?e "e") to be FPP, as we should on the assumption that ![k=1](https://latex.codecogs.com/png.latex?k%3D1 "k=1").










Aitken, C., Taroni, F., & Thompson, W. (2003). How the probability of a false positive affects the value of dna evidence. *Journal of Forensic Science*, *48*(1), 1–8. <https://doi.org/10.1520/jfs2001171>

Buckleton, J. S., Bright, J.-A., & Taylor, D. (2018). *Forensic dna evidence interpretation*. CRC press.
