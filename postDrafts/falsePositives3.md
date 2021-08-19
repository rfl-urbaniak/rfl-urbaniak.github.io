False positives
================

Last time we derived one formula for the impact of false positive probability on the value of DNA evidence. Today, we'll look at seemingly different formula to get a better perspective. Buckleton, Bright, & Taylor (2018) give a formula for the impact of errors on likelihood ratio different from the one we discussed before. Since the derivation is simpler and it turns out that in fact this is simply a more general formula, of which (FPP-LR) is just a particular instance, it worth taking a look.

-    For instance, in Dwayne Johnson (2003) samples were accidentally swapped. In Lukis Anderson (2012) the material has been carried over by the responding paramedics. In one case, German police invested a considerable amount of time and effort searching for the so-called Phanotm of Heilbronn, whose DNA profile was found on evidence from a large variety of crimes. A bountly of 300k EUR was placed on hear head. It turned out she was an innocent employee involved in the production of cotton swabs used accross the country.

-    For instance, in 2011 the Las Vegas Metropolitan Police Department acknowledge that samples of two men suspected of a 2001 robbery were switched, leading to the exclusion of the perpetrator and four years of incarceration of the other suspect. The mistake came to light only because the perpetrator was later on arrested for an unrelated crime. In a high-profile case of a serial rapist, the notorious Night Stalker who committed more than 140 sexual assualts in London, the actual perpertrator came to the attention of the police quite soon, but a DNA test excluded him (falsely so, because the samples had been mistakenly switched), and so his spree continued for months.

-    While single-source sample comparison is not too prone to this sort of error, the interpretation of mixtures---which is usually what is needed in sexual assault cases---is quite complicated. Here is an illustration of this fact. Dror & Hampikian (2011) re-examined a 2002 Georgia rape trial in which two forensic scientists had concluded that the defendant could not be excluded as a contributor to the mixture of sperm from inside the victim (the defendant was found guilty). The evidence---DNA mixture and the DNA profiles of the victim and three suspects together those pieces of information that were highly relevant (such as the DNA amplification conditions) was sent to 17 lab technicians for examination. One of them agreed that the defendant could not be excluded as a contributor. Twelve considered the DNA exclusionary, and four found it inconclusive. If the quantity of DNA is limited, there is uncertainty about the number of contributors and about whetehr any alleles are missing, determining which alleles to assign to which contributor to some extent involves educated guesses on the part of the analysts. This suggests there is an element of subjectivity in mixed DNA interpretation.

Moreover, such errors are not easy to detect. Since DNA evidence carries so much weight in the fact-finders mind, it is very unusual to procceed with additional time- and cost-consuming DNA tests. It is also unusal that the suspect or their family can on their own afford further tests. For instance, an additional test exonerated Timothy Durham, sentenced to 3000 years for the rape of a young girl in Oklahoma City. So far there are two more cases known in the US where re-testing exonerated the accussed: Josiah Sutton, whose case we already mentioned, and Gilbert Alejandro. Even more troubling is that errors from contamination or mislabeling of samples often cannot be detected with further DNA testing, because they will simply replicate the same misdentification. Sometimes, a lab discovers their own error and reports it, but this is a rather unlikely turn of events.

DNA identification is to some extent prone to errors which are not measured by the random match probability, and no serious attempts to systematically quantify error rates in DNA testing have been made. Anecdotal reports about false matches suggest that errors take place more often than RMP would entail, but how often we should expect them remains unclear (Thompson, 2013). Regular proficiency tests used in accreddited DNA laboratories involve comparison of samples from known sources, but they are criticized for being unrealistically easy (yet, it happens that analysts fail them). Sometimes, corrective action files are made available, and then they aren't too impressive. For instance, the Santa Clara County district attorney's crime laboratory between 2003 and 2007 caught 14 instances of evidence cross-contamination with staff DNA, three of contamination by unknown person, and six of DNA contamination from other samples, three cases of DNA sample switch, one mistake in which the analyst reported an incorrect result, and three errors in the computation of the statistics to be reported. Of course, these are errors that were caught, and so one might argue that they show that labs are pretty good at catching their own errors. This, however, is an optimistic intepretation. These errors have been discovered due to unusual circumstances that led to the double-checking of the results. These circumstances, however, do not normally arise. It is not always the case that when a mistake is made the result implicates a staff member or an unknown person who was too young at the time of the crime to have committed it, for instance. Crucially, a match with a person whom the analyst might already know is a suspect is not an outcome that would raise an eyebrow and lead to a double-check.

``` r
rmp9 <- 10e-9
rmp3 <- 10e-3
fpp <- seq(0,0.05, by = 0.001)

lr9 <- 1/(rmp9 + (fpp * (1-rmp9)))
lr3 <- 1/(rmp3 + (fpp * (1-rmp3)))


fppTable <- data.frame(fpp,   lr9,  lr3, ref = rep(16.8, length(fpp)))

library(tidyr)
fppTableLong <- gather(fppTable,line,value,c(lr9,lr3,ref), factor_key=TRUE)


ggplot(fppTableLong, aes(x=fpp,y=value, lty = line))+ geom_line()+ylim(c(0,400))+
  theme_tufte()+ylim(c(0,400))+
  ylab("Likelihood ratio")+
  xlab("False positive probability")+
  scale_linetype_manual(values = c(1,2,3),labels = c(expression(paste("RMP=",10^{-9})),expression(paste("RMP=",10^{-3})),"reference at 16.8"))+
  ggtitle("Impact of false positive probability on likelihood ratio")+ 
  theme(legend.position = c(0.85,.7))+ labs(lty = "RMP") 
```

<img src="https://rfl-urbaniak.github.io/images/fig-fpplr-1.png" width="100%" style="display: block; margin: auto;" />

We illustrate this impact for the range of FPP between 0 and 0.05, for two values of RMP: ![10^{-9}](https://latex.codecogs.com/png.latex?10%5E%7B-9%7D "10^{-9}") (often reported in the case of two single source samples over ten or more loci) and ![10{^-3}](https://latex.codecogs.com/png.latex?10%7B%5E-3%7D "10{^-3}") (sometimes obtained by means of less discriminating tests when the comparison involves a mixed sample). The upshot is that even a small increase in FPP can lower the likelihood ratio dramatically, which is yet another reason not to ignore FPP in DNA evidence evaluation. In our illustration, we look at two pieces of DNA evidence with the two RMP rates at ![1\*10^8](https://latex.codecogs.com/png.latex?1%2A10%5E8 "1*10^8") and ![100](https://latex.codecogs.com/png.latex?100 "100"), respectively. If the false positive probability reaches 0.02, they fall down to ![\\approx 49.99](https://latex.codecogs.com/png.latex?%5Capprox%2049.99 "\approx 49.99") and ![\\approx 33.55](https://latex.codecogs.com/png.latex?%5Capprox%2033.55 "\approx 33.55"), and they get fairly close to each other already at ![FPP=0.05](https://latex.codecogs.com/png.latex?FPP%3D0.05 "FPP=0.05"), where they are ![\\approx 20](https://latex.codecogs.com/png.latex?%5Capprox%2020 "\approx 20") and ![\\approx 16.8](https://latex.codecogs.com/png.latex?%5Capprox%2016.8 "\approx 16.8").

Buckleton, J. S., Bright, J.-A., & Taylor, D. (2018). *Forensic dna evidence interpretation*. CRC press.

Dror, I. E., & Hampikian, G. (2011). Subjectivity and bias in forensic DNA mixture interpretation. *Science & Justice*, *51*(4), 204–208. <https://doi.org/10.1016/j.scijus.2011.08.004>

Thompson, W. C. (2013). Forensic dna evidence: The myth of infallibility. In S. Krimsky & J. Gruber (Eds.), *Genetic explanations: Sense and nonsense* (pp. 227–347). Harvard University Press.
