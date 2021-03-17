---
title: Notes on Exon Skipping with ASOs
tree_state: 🌱
---

Given exon and antisense oligosequence predict how well the ASO is going to be able to skip the given exon.

- People with Duchenne Muscular Distrophy (DMD) are missing exons in the genes that control dystrophin protein production (the dystrophin gene is our largest gene with 79 exons).
- The exons in these gene are fit together like puzzle pieces, so if an exon is an important puzzle piece and it's missing then it will create serious issues. Becker Muscular Distrophy (BMD) is when an exon is missing but the rest of the exon puzzle pieces can still fit together. DMD is when the pieces cannot be fit together due to the exons that are missing.
- If all of the exons cannot fit together, then your body will produce completely non-functional dystrophin protein.
- Antisense oligonucleotides (AOs) can be used to hide exons, so that when these additional exons are ignored by our cell's protein production mechanisms, the remaining exons actually fit together and your body will be able to produce the dystrophin protein.
- Dystrophin protein- the protein normally sits in the membrane that surrounds muscle fibres like a skin, and protects the membrane from damage during muscle contraction. Without dystrophin the muscle fibre membranes become damaged and eventually the muscle fibres die.
  - It's a very large protein with a section in the middle consisting of lots of repeated segments. Individuals with BMD have some of these repeated segments missing, but the protein still works. and People with BMD have relatively mild symptoms- often being able to still walk into their 40s and 50s.
- The goal of using these techniques is to kind of convert DMD to BMD and prolong the amount of muscular ability that these people have.

# Definitions

https://www.musculardystrophyuk.org/progress-in-research/background-information/what-is-exon-skipping-and-how-does-it-work/

Exon- a segment of a DNA or RNA molecule that actually contains the information coding for a protein or peptide sequence

Intron- segment of DNA/RNA that is just filler code and that is sometimes called ‘junk DNA’

Antisense oligonucleotides- A short piece of genetic material (DNA or RNA) which can bind to a specific gene and change how the code is read. They can be used as a “molecular patch” to mask errors in the genetic code, this is known as exon skipping and this is in clinical trial for Duchenne muscular dystrophy. Certain types of antisense oligonucleotides are also being investigated in the laboratory for their ability to completely switch off genes, this is known as gene silencing.



## How to Makes ASO

1. Select "target gene transcript" (part of the gene you want to edit) and strategy
2. open source web-based bioinformatics tools like SpliceAid 2 and Human Splicing Finder can help you identify "predicted splice motifs" (means patterns in DNA that they should you could use)
3. select what cell type you want to test your ASO on
4. figure out what you are going to use to transfer the ASO into someone's DNA
5. test your ASO against a control ASO to see if your ASO is actually binding better than say a random ASO
6. AOs can be further optimised by ‘micro-walking’ and shifting the AO annealing sites in either direction to ensure the most amenable splice motifs have been targeted
   1. One important parameter to consider when designing primers for RT-PCR analysis of the full-length and AO-induced transcripts is to place the forward and reverse primers a few exons away from the targeted exon. We have now encountered several examples where targeting one exon for exclusion from the mature mRNA also influences recognition and retention of flanking exons and introns.

# Paper 2

The rational design of an exon skipping oligonucleotide involves the choice of an antisense sequence, usually between 15 and 32 nucleotides, targeting the exon that is to be skipped. Although parameters describing the target site can be computationally estimated and several have been identified to correlate with efficacy, methods to predict efficacy are limited. Here, an *in silico* (in silico just means on the computer which is takes its name since computer chips are made of silicon) pre-screening approach is proposed, based on predictive statistical modelling.

- Duchenne muscular dystrophy (DMD) dataset

Most predictive parameters (They used k fold cross validation to select features)

1. the binding energetics of the oligonucleotide to the RNA
2. the distance in bases of the target site from the splice acceptor site, as the two most predictive parameters

They fit a linear regression model on skipping efficiency:

- Skipping efficacy was always based on the ratio of skipped to native transcript observed following nested reverse transcription polymerase chain reaction (nested PCR) analyses
- $\frac{\text{skipped transcript}}{\text{skipped transcript + native transcript}}$
- The authors of previous studies defined a ‘good’ level of exon skipping to be greater than 25–30 percent

They thresholded their model at 30% skipping efficiency and compared with which oligonucleotides actually have 30% skipping efficiency.

