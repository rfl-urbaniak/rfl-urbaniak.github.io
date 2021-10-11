---
layout: post
title: "False positives in DNA identification 5"
author: "Rafal Urbaniak"
---


In a few recent posts we discussed the error probability for false
positives in DNA evidence evaluation. Now, let’s think about the error
probability for false negatives and its impact on the value of
exculpatory DNA evidence. Consider the probability of no match being
reported if an error has been made, analogus to *k* in the previous calculations:

\begin{align}
l & = \mathsf{P}()\neg R \vert E, S} = \mathsf{P}(\neg R \vert E, \neg S) = \mathsf{P}(\neg R\vert E)
\end{align}


 Now, the
likelihood ratio calculations, assuming *l* = 1, go as follows:

\begin{align}
\mathsf{LR}(\neg R, S, \neg S) & = \frac{\mathsf{P}(\neg R \vert S)}{\mathsf{P}()\n R \vert \n S)} \\
& = \frac{\mathsf{P}(\neg R \vert \neg E, S)\mathsf{P}(\neg E \vert S) + \mathsf{P}(\neg R \vert E, S}\mathsf{P}(E \vert S)}
{\mathsf{P}(\neg R \vert \neg E, \neg S}\mathsf{P}(\neg E \vert \neg S} + \mathsf{P}(\neg R \vert E,\neg S)\mathsf{P}(E \vert \neg S)} \\
& = \frac{0 (1-e) +  le}
{(1-RMP)(1-e) + le} \\
& = \frac{le}
{1- RMP - e + eRMP + le} = \frac{le}{1-RMP + e(l + RMP -1)}\\
& = \frac{e}{1 - RMP + eRMP} = \frac{e}{1+(e-1)RMP}
\end{align}




If the error rate is 0, then the numerator is 0 and so is the , as it
should. In such a case, the evidence is completely exculpatory, the
posterior probability that the suspect is the source will be also 0. If
the error rate is not 0, the numerator simply is the probability of
error, and the numerator takes values between 1 − *R**M**P* and 1,
depending on the value of *e*. Quite crucially, 1 in the denominator is
decreased by (1−*e*)*R**M**P*, which with usually very low RMP in the
case of DNA evidence is a very small change as compared to one, so the
denominator stays very close to 1 even if *e* is very high, and the
effectively simply is $\\approx \\nicefrac{e}{1} = e$. The lines in
Figure , strictly speaking, do not overlap, but the difference between
them (with *R**M**P* being fairly low) is negligible.


``` r
rmp9 <- 10e-16
rmp3 <- 10e-3
fnp <- seq(0,0.5, by = 0.001)

lr9n <- fnp/(1 + ((fnp -1) * rmp9))
lr3n <- fnp/(1 + ((fnp -1) * rmp3))

fnpTable <- data.frame(fnp,   lr9n,  lr3n)

library(tidyr)
fnpTableLong <- gather(fnpTable,line,value,c(lr9n,lr3n), factor_key=TRUE)


ggplot(fnpTableLong, aes(x=fnp,y=value, color = line))+  geom_line()+theme_tufte()+ylab("Likelihood ratio")+xlab("False negative probability") +scale_color_manual(values = c(1,2),labels =
              c(expression(paste("RMP=",10^{-16})),expression(paste("RMP=",10^{-3}))))+ggtitle("Impact of false negative probability on likelihood ratio")+ theme(legend.position = c(0.9,.7))+ylim(c(0,0.5))+ labs(color = "RMP")
```

<img src="https://rfl-urbaniak.github.io/images/fig-fnplr-1.png" width="100%" style="display: block; margin: auto;" />
