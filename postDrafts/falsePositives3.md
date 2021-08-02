False positives
================

Hopefully, having convinced the reader that the false positive probability is non-negligible, I can now move to a probabilistic approach to the impact such probability can have on the value of evidence. Since I will use the likelihood ratio, a fairly standard measure of evidential strength, I first explain this notion, then explain one relevant formula and its derivation, leaving another perspective to another post.

The is a comparative measure of whether evidence *E* supports a hypothesis *H* more than a competing hypothesis *H*′, in symbols:
If the evidence supports *H* more than *H*′, the ratio would be above one, and if the evidence supports *H*′ more than *H*, the ratio would be below one. So, support levels correspond to deviations from one. The greater the likelihood ratio (for values above one), the stronger the evidence in favor of *H* as contrasted with *H*′. The smaller the likelihood ratio (for values below one), the stronger the evidence in favor of the competing hypothesis *H*′ as contrasted with *H*.

Experts sometimes testify by offering the likelihood ratio as a measure of the strength of the evidence. An expert, for instance, may testify that the blood-staining on the jacket of the defendant is ten times more likely to be seen if the wearer of the jacket hit the victim (prosecutor's hypothesis) rather than if he did not (defense's hypothesis) (CGG Aitken, Roberts, & Jackson, 2010, p. 38). Experts are typically advised not to comment on the posterior odds given the evidence. As this formulation of the Bayes's theorem makes clear, an assessment of the posterior odds will require a judgment about the prior odds, and the latter lies beyond the competence of an expert. A prominent forensic scientist recommends that experts \`not trespass on the province of the jury by commenting directly on the accused's guilt or innocence, and should generally confine their testimony to presenting the likelihood of their evidence under competing propositions' (CGG Aitken et al., 2010, p. 42).

Now, let us follow Colin Aitken, Taroni, & Thompson (2003) in investigating its impact on the likelihood ratio of the DNA match. We just add a bit more details to the derivation they present for the sake of clarity. For simplicity we stil assume that the false negative probability is 0, that is, that if the match is real, it will be reported with certainty. We abbreviate:

The formula we will end up with is:

where RMP stands for the random match probability and FPP for the false positive probability. We will assume that whether a (lack of) match is reported is independent of whether it is coincidental,
that the probability of true match if the suspect is a source is 1,
and that the probability that a true match is reported,
Here, for simplicity we take the probability of a false negative to be null; in fact, some of the reasons for taking false positives seriously are also reasons to take false negatives seriously, but let's deal with one problem at a time (and in the end, the impact of a false positive risk will be clear from the way the formula will be derived). Now, let us rewrite the numerator of the LR by extending the conversation, rewriting the probabilities of conjunctions in terms of conditional probability and simplifying:

Analogously, we can rewrite the denominator:
Putting and together, we have that:
Now, apply in four places:
Then, use in the numerator:
Finally, yields:
Once we abbreviate $\\pr{M\\vert \\n S}$ as RMP, $\\pr{R \\vert \\n M}$ as FPP and $\\pr{\\n M \\vert \\n S}$, we arrive at the desired formula.

Now, let us illustrate this impact for the range of FPP between 0 and 0.05, for two values of RMP: 10<sup>−9</sup> (often reported in the case of two single source samples over ten or more loci) and 10**<sup>−</sup>3 (sometimes obtained by means of less discriminating tests when the comparison involves a mixed sample).

Aitken, C., Roberts, P., & Jackson, G. (2010). Fundamentals of probability and statistical evidence in criminal proceedings (Practitioner Guide No. 1), Guidance for judges, lawyers, forensic scientists and expert witnesses. *Royal Statistical Society’s Working Group on Statistics and the Law*.

Aitken, C., Taroni, F., & Thompson, W. (2003). How the probability of a false positive affects the value of dna evidence. *Journal of Forensic Science*, *48*(1), 1–8. <https://doi.org/10.1520/jfs2001171>