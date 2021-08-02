---
layout: post
title: "False positives in DNA identification 3"
author: "Rafal Urbaniak"
---



Hopefully, having convinced the reader that the false positive probability is non-negligible, I can now move to a probabilistic approach to the impact such probability can have on the value of evidence. Since I will use the likelihood ratio, a fairly standard measure of evidential strength, I first explain this notion, then explain one relevant formula and its derivation, leaving another perspective to another post.


The **likelihood ratio** is a comparative measure of whether evidence $E$ supports a hypothesis $H$ more than a competing hypothesis $H'$, in symbols:
\[
\label{eq:LR}
\mathsf{LR}(E,H,H') & = \frac{\mathsf{P}(E \vert H)}{\mathsf{P}(E \vert H')}.
\]


If the evidence supports $H$ more than $H'$, the ratio would be above one, and if the evidence supports $H'$ more than $H$, the ratio would be below one.  So, support levels correspond to deviations from one.  The greater the likelihood ratio (for values above one), the stronger the evidence in favor of $H$ as contrasted with $H'$. The smaller the likelihood ratio (for values below one), the stronger the evidence in favor of the competing hypothesis $H'$ as contrasted with $H$.


Experts sometimes testify by offering the likelihood ratio as a measure of the strength of the evidence. An expert, for instance, may testify that the blood-staining on the jacket of the defendant is ten times more likely to be seen if the wearer of the jacket hit the victim (prosecutor's hypothesis) rather than if he did not (defense's hypothesis) (CGG Aitken, Roberts, & Jackson, 2010, p. 38). Experts are typically advised not to comment on the posterior odds given the evidence. As this formulation of the Bayes's theorem makes clear, an assessment of the posterior odds will require a judgment about the prior odds, and the latter lies beyond the competence of an expert. A prominent forensic scientist recommends that experts \`not trespass on the province of the jury by commenting directly on the accused's guilt or innocence, and should generally confine their testimony to presenting the likelihood of their evidence under competing propositions' (CGG Aitken et al., 2010, p. 42).


Now, let us follow Colin Aitken, Taroni, & Thompson (2003) in investigating its impact on the likelihood ratio of the DNA match. We just add a bit more details to the derivation they present for the sake of clarity. For simplicity we stil assume that the false negative probability is 0, that is, that if the match is real, it will be reported with certainty. We abbreviate:


| $S$ | The specimen comes from the suspect. |
| $R$ | A match is reported.                 |
| $M$ | There is a true match.               |


The formula we will end up with is:

\[
\tag{FPP-LR} \mathsf{LR}(R, S, \neg S) & = \frac{1}{RMP + [ FPP \times (1-RMP)]}
\]

 where RMP stands for the random match probability and FPP for the false positive probability. We will assume that whether a (lack of) match is reported is independent of whether it is coincidental,

\[\mathsf{P}(R \vert M \wedge S)  = \mathsf{P}(R \vert M \wedge \neg S) = \mathsf{P}(R \vert M)\]
\[\mathsf{P}(R \vert \neg M \wedge S)  = \mathsf{P}(R \vert\neg M \wedge \neg S) = \mathsf{P}(R \vert \neg M)\]
that the probability of true match if the suspect is a source is 1,
\[
\mathsf{P}(M\vert S) = 1  \,\,\, \mbox{ so also } \,\,\, \mathsf{P}(\neg M \vert S)=0,
\]
and that the probability that a true match is reported,
\[\mathsf{P}(R \vert M) & = 1.\]



The formula we will end up with is:

\[
\mathsf{LR}(R, S, \n S)  = \frac{1}{RMP + [ FPP \times (1-RMP)]}
\]
\noindent where RMP stands for the random match probability and FPP for the false positive probability. We will assume that whether a (lack of) match is reported is independent of whether it is coincidental,
\[
\mathsf{P}(R \vert M \et S)  = \mathsf{P}(R \vert M \et \n S) = \mathsf{P}(R \vert M)
\]
\[
\mathsf{P}(R \vert \n M \et S)  = \mathsf{P}(R \vert\n M \et \n S) = \mathsf{P}(R \vert \n M),
\]
that the probability of true match if the suspect is a source is 1,
\[
\mathsf{P}(M\vert S) = 1  \,\,\, \mbox{ so also } \,\,\, \mathsf{P}()\n M \vert S)=0,
\]
and that the probability that a true match is reported,
\[
\mathsf{P}(R \vert M)  = 1.
\]



Here, for simplicity we take the probability of a false negative to be null; in fact, some of the reasons for taking false positives seriously are also reasons to take false negatives seriously, but let's deal with one problem at a time (and in the end, the impact of a false positive risk will be clear from the way the formula will be derived). Now, let us rewrite the numerator of the LR by extending the conversation, rewriting the probabilities of conjunctions in terms of conditional probability and simplifying:

\[
\mathsf{P}(R\vert S)  = \frac{\pr{R\et S}}{\pr{S}}   = \frac{\mathsf{P}(R \et M \et S) + \mathsf{P}(R \et \n M \et S)}
{\mathsf{P}(S)} \]
\[
 = \frac{\mathsf{P}(R \vert M \et S)\mathsf{P}(M \vert S)\mathsf{P}(S) + \mathsf{P}(R \vert \n M \et S)\mathsf{P}()\n M \vert S)\mathsf{P}(S)} {\mathsf{P}(S)}  \]\[
 = \mathsf{P}(R \vert M \et S)\mathsf{P}(M \vert S) + \mathsf{P}(R \vert \n M \et S)\mathsf{P}()\n M \vert S)
\]

\noindent  Analogously, we can rewrite the denominator:
\[
\mathsf{P}(R \vert \n S)  = \mathsf{P}(R \vert M \et \n S)\mathsf{P}(M \vert \n S) +
\mathsf{P}(R \vert \n M \et \n S)\mathsf{P}(\n M \vert \n S)
\]

Putting these together, we have that:
\[
\mathsf{LR}(R,S, \n S)  = \frac{\mathsf{P}(R \vert M \et S)\mathsf{P}(M \vert S) + \mathsf{P}(R \vert \n M \et S)
\mathsf{P}(\n M \vert S)}
{\mathsf{P}(R \vert M \et \n S)\mathsf{P}(M \vert \n S) +
\mathsf{P}(R \vert \n M \et \n S)\mathsf{P}(\n M \vert \n S)}
\]
Now, apply one of the identities in four places:
\[
\mathsf{LR}(R,S, \n S)  = \frac{
\mathsf{P}(R \vert M)\mathsf{P}(M \vert S) + \mathsf{P}(R \vert \n M)\mathsf{P}(\n M \vert S)
}{
\mathsf{P}(R \vert M )\mathsf{P}(M \vert \n S) +
\mathsf{P}(R \vert \n M)\mathsf{P}(\n M \vert \n S)
}
\]
Then, rewrite  the numerator:
\[
\mathsf{LR}(R,S, \n S)  = \frac{
\mathsf{P}(R \vert M) \times 1 + \mathsf{P}(R \vert \n M)\times 0
}{
\mathsf{P}(R \vert M )\mathsf{P}(M \vert \n S) +
\mathsf{P}(R \vert \n M)\mathsf{P}(\n M \vert \n S)
}
\]
Finally, we have:
\[
\mathsf{LR}(R,S, \n S) & = \frac{1}
{\mathsf{P}(R \vert  M)\mathsf{P}( M \vert \n S) + \mathsf{P}(R \vert \n M)\mathsf{P}(\n M \vert \n S)}
\]
Once we abbreviate $\mathsf{P}(M\vert \n S)$ as RMP, $\mathsf{P}(R \vert \n M)$ as FPP and $\mathsf{P}(\n M \vert \n S)$, we arrive at the desired formula.
