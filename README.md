# Supplementary Materials for our ESWC 2017 Submission
This repository contains the supplementary materials used to reproduce the
experiments submitted to the [14th Extended Semantic Web Conference (ESWC 2017)](http://2017.eswc-conferences.org).

NB: This repository is in progress – Please check back later.

#### Table of Contents
1. [Dataset](#dataset)
2. [GATE Pipeline](#gate-pipeline)
3. [Knowledge Base](#knowledge-base)

## Dataset
The dataset used in our experiments are open access, computer science articles retrieved from [CORE](http://core.ac.uk) dataset [dump 2016](https://core.ac.uk/services#dataset).

## GATE Pipeline
This is the text mining pipeline used to extract relevant information from the dataset. The pipeline requires Java version 8.0 or better and [GATE](www.gate.ac.uk) version 3.0 or better.

When the pipeline loads successfully, you should see the following sequence of processing resources in the GATE Developer interface:

![alt text][pipeline]

## Knowledge Base
The provided knowledge base contains all the extracted entities from our dataset of 100 computer science articles. The semantic triples are expressed using the Resource Description Framework (RDF) syntax.

[pipeline]: https://github.com/SemanticSoftwareLab/Supplements-ESWC2017/blob/master/graphics/pipeline.png "Pipeline processing resources"
