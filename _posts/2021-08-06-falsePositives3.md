---
layout: post
title: "False positives in DNA identification 3"
author: "Rafal Urbaniak"
---



Hopefully, having convinced the reader that the false positive probability is non-negligible, I can now move to a probabilistic approach to the impact such probability can have on the value of evidence. Since I will use the likelihood ratio, a fairly standard measure of evidential strength, I first explain this notion, then explain one relevant formula and its derivation, leaving another perspective to another post.


The **likelihood ratio** is a comparative measure of whether evidence $E$ supports a hypothesis $H$ more than a competing hypothesis $H'$, in symbols:
\begin{align}
\label{eq:LR}
\mathsf{LR}(E,H,H') & = \frac{P(E \vert H)}{P(E \vert H')}.
\end{align}


If the evidence supports $H$ more than $H'$, the ratio would be above one, and if the evidence supports $H'$ more than $H$, the ratio would be below one.  So, support levels correspond to deviations from one.  The greater the likelihood ratio (for values above one), the stronger the evidence in favor of $H$ as contrasted with $H'$. The smaller the likelihood ratio (for values below one), the stronger the evidence in favor of the competing hypothesis $H'$ as contrasted with $H$.


Experts sometimes testify by offering the likelihood ratio as a measure of the strength of the evidence. An expert, for instance, may testify that the blood-staining on the jacket of the defendant is ten times more likely to be seen if the wearer of the jacket hit the victim (prosecutor's hypothesis) rather than if he did not (defense's hypothesis) (CGG Aitken, Roberts, & Jackson, 2010, p. 38). Experts are typically advised not to comment on the posterior odds given the evidence. As this formulation of the Bayes's theorem makes clear, an assessment of the posterior odds will require a judgment about the prior odds, and the latter lies beyond the competence of an expert. A prominent forensic scientist recommends that experts \`not trespass on the province of the jury by commenting directly on the accused's guilt or innocence, and should generally confine their testimony to presenting the likelihood of their evidence under competing propositions' (CGG Aitken et al., 2010, p. 42).


Now, let us follow Colin Aitken, Taroni, & Thompson (2003) in investigating its impact on the likelihood ratio of the DNA match. We just add a bit more details to the derivation they present for the sake of clarity. For simplicity we stil assume that the false negative probability is 0, that is, that if the match is real, it will be reported with certainty. We abbreviate:

\begin{center} \hspace{10mm}
\begin{tabular}{lp{9cm}}
$S$ & The specimen comes from the suspect. \\
$R$ & A match is reported. \\
$M$ & There is a true match.
\end{tabular}
\end{center}
