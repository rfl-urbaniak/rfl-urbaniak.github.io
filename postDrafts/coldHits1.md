False positives
================

To better appreciate the theoretical virtues of likelihood ratios, it is instructive to look at a case study, DNA evidence, focusing in particular on so-called cold-hit matches. This is what we will do over the next few posts.

DNA evidence is one of the most widely used forms of quantitative evidence currently in use. It may be used to corroborate other evidence in a case, or as the primary incriminating evidence. For example, suppose different investigative leads point to an individual, Mark Smith, as the perpetrator. The investigators also find several traces at the crime scene left by the perpetrator. Laboratory analyses show that the genetic profile associated with the traces matches Smith. In this scenario, the DNA match corroborates the other evidence against Smith. In contrast, suppose the police has no other investigative lead except the traces left at the crime scene. Hoping to find the perpetrator, the police run the genetic profile associated with the traces through a database of profiles and find a match, a so-called *cold-hit*.

Cold-hit DNA matches have been the focus of intense discussion in recent years. Since in cold-hit cases there is little or no other evidence, cold-hit matches are often the primary item of evidence against the defendant. Some believe that this circumstance weakens the case. Others disagree. This debate illustrates how probability theory---in particular, the likelihood ratio---can help to assess the strength of evidence at trial. What follows examines some of the main arguments.

For concreteness, consider the California rape and murder case of Diana Sylvester. In 2008, many years after the crime, John Puckett was identified as a unique 9-loci match through a database search of 338,000 profiles. He was the only individual in the database who matched the traces collected from the victim Diana Sylvester in 1972. According to an expert witness, the particular pattern of alleles present in the material was (conservatively) expected to occur randomly among Caucasian men with a frequency of 1 in 1.1 million. This is the *random match probability* (RMP). The random match probability---often interpreted as the probability that someone who is not the source would coincidentally match, $\\pr{\\textsf{match} \\vert \\neg \\textsf{source}}$---is a common measure of the strength of a DNA match.

The lower the RMP, the more strongly incriminating the match. The rationale here is that a low random match probability suggests that it is unlikely that two people would share the same DNA profile. In line with what we already discussed, strictly speaking, a match is strong evidence that the defendant is the source only if the probability that the person who left the traces (the \`source') would match is significantly greater than RMP. In practice, when it comes to DNA evidence, it is often assumed that P(match|source) is very high.

Although clearly 1 in 1.1 million should not be confused with the probability of Puckett's innocence (see for details), the small figure indicates it is very unlikely that a random person unrelated to the crime would match. The match is therefore strong evidence of Puckett's guilt. Assuming that the probability of a match if Puckett indeed was the source was (practically) 1, the likelihood ratio is simply 1.1 × 10<sup>6</sup>.

``` r
eIfh <- 1
eIfnH <- (1/1.1e6)
lr <- eIfh/eIfnH
lr
```

    ## [1] 1100000

During the pretrial hearing, however, Bicka Barlow, the DNA expert for the defense, pointed out that this was a cold-hit case. No evidence tied Puckett to the crime other than the cold-hit match, Puckett's previous rape convictions and the fact that he was in the area at the time of the murder. In order to correctly assess the probative value of the cold-hit match, Barlow argued, the random match probability should be multiplied by the size of the database. The result of such a multiplication is called the *database match probability* (DMP). In Puckett's case, the multiplication of $\\nicefrac{1}{1.1\\times 10^6}$ by 338, 000 resulted in a database match probability of approximately .3.

``` r
dmp <- 1/1.1e6 * 338e3
1/dmp
```

    ## [1] 3.254438

which is a less impressive number than the original RMP (the likelihood ratio for the DMP is approximately 3.25). According to this calculation, it was no longer very unlikely that an unrelated person from the database would match, and so the cold-hit DNA match was no longer strong evidence of guilt. At least, this was Barlow's argument.

Barlow followed a 1996 report by the National Research Council called NRC II (National Research Council, 1996), preceded by an earlier report on DNA evidence called NRC I (National Research Council, 1992). NRC II recommended precisely what Balrow did: that in cold-hit cases RMP should be multiplied by the database size, yielding DMP. The underlying idea was that the larger the size of the dataset, the higher the database match probability, and the lower the strength of the match. This correction was meant to guard against the heightened risk of mistaken matches for the innocent people in the database. To see however, if this was sound advice, we need to look under the hood. This is what we will get started on in the next post.

National Research Council. (1992). *DNA technology in forensic science <span class="csl-no-emph">\[NRC I\]</span>*. Committee on DNA technology in Forensic Science, National Research Council.

National Research Council. (1996). *The evaluation of forensic DNA evidence <span class="csl-no-emph">\[NRC II\]</span>*. Committee on DNA technology in Forensic Science, National Research Council.
