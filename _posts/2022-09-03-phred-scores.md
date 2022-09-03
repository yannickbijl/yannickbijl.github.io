---
layout: post
date: 2022-09-03 00:00:00 +0100
tags: Bioinformatics
categories: Bioinformatics
title: 'Phred Scores'
---

Phred scores are a common metric in bioinformatics to assign quality, in most cases to individual bases (A, T, C, G). Though they are used as quality scores, Phred scores actually represent a probability. A lower Phred score indicates a lower probability.

In many cases, including the quality of sequenced nucleotides, the probability tells the certainty that the given result is correct. In the case of the nucleotides it gives the certainty that the nucleotide is correctly sequenced. The lower Phred scores represent a lower certainty, and in turn a lower quality. This same concept can be applied to sequence alignment quality and the determination of consensus sequences. Phred scores are rarely seen outside of bioinformatics, if at all.

Phred scores are calculated as the base 10 logarithm ($\log_{10}$) of a given probability that the value is incorrect ($P$). The Phred score is made positive and scaled by multiplying with $-10$. This gives the following formula:  
&nbsp;&nbsp;&nbsp;&nbsp; $Q = -10 \log_{10}P$

Thus a probability of 0.1 (10%, 1 in 10) will give us a Phred score ($Q$) of 10. Whereas a probability of 0.01 (1%, 1 in 100) will give a $Q$ score of 20. The pattern continues with each ten-fold decrease in the probability being a 10 point increase in the Phred scores. Of course it is also possible to go from a Phred score to a probability using the formula below:  
&nbsp;&nbsp;&nbsp;&nbsp; $P = 10 \dfrac{-Q}{10}$

Though we can have small differences explained with normal numbers now, the real smart thing about Phred is the encoding that con now be done. The Phred scores can be encoded into single characters by using ASCII encoding. To ensure that the characters are readable and visible (no whitespace charatcers) the value 33 is added to the Phred score. Thus $Q=$ 10 becomes the character `+`. With this we can have values and quality scores matching in two lines beneath each other, saving a lot of space in comparison to writing the value 99.9% each time.
