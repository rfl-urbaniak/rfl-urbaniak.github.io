---
layout: post
title: "False positives in DNA identification 3"
author: "Rafal Urbaniak"
---



Hopefully, having convinced the reader that the false positive probability is non-negligible, I can now move to a probabilistic approach to the impact such probability can have on the value of evidence. Since I will use the likelihood ratio, a fairly standard measure of evidential strength, I first explain this notion, then explain one relevant formula and its derivation, leaving another perspective to another post.


The \textbf{likelihood ratio} is a comparative measure of whether evidence $E$ supports a hypothesis $H$ more than a competing hypothesis $H'$, in symbols:
\begin{align}
\label{eq:LR}
\mathsf{LR}(E,H,H') & = \frac{\pr{E \vert H}}{\pr{E \vert H'}}.
\end{align}
