# Supplementary Materials for our ESWC 2017 Submission
This repository contains the supplementary materials used to reproduce the
experiments submitted to the [14th Extended Semantic Web Conference (ESWC 2017)](http://2017.eswc-conferences.org).

NB: This repository is in progress – Please check back later.

#### Table of Contents
1. [Dataset](#dataset)
2. [GATE Pipeline](#gate-pipeline)
3. [Knowledge Base](#knowledge-base)
  1. [Publishing the Knowledge base](#publishing-the-knowledge-base-through-fuseki)
  2. [License](#license)

## Dataset
The dataset used in our experiments are open access, computer science articles retrieved from [CORE](http://core.ac.uk) dataset [dump 2016](https://core.ac.uk/services#dataset).

## GATE Pipeline
This is the text mining pipeline used to extract relevant information from the dataset. The pipeline requires Java version 8.0 or better and [GATE](www.gate.ac.uk) version 3.0 or better.

When the pipeline loads successfully, you should see the following sequence of processing resources in the GATE Developer interface:

![alt text][pipeline]

## Knowledge Base
The provided knowledge base contains all the extracted entities from our dataset of 100 computer science articles. The semantic triples are expressed using the Resource Description Framework (RDF) syntax.

### Vocabularies
The triples in our knowledge base use a number of (linked open) vocabularies:

| Vocabulary/Ontology    | Namespace in KB | Description   | URL  |
| ------------- |:-------------:|:-----|:-------------|
| Publication Ontology (PUBO) | pubo | PUBO vocabularies are used to express the relations between documents, annotations and their inter-relations. | http://lod.semanticsoftware.info/pubo/pubo |
| SALT Rhetorical Ontology (SALT) | sro | Used for describing rhetorical elements (claims and contributions) of documents. | http://salt.semanticauthoring.org/ontologies/sro   |
| Resource Description Framework (RDF) | rdf | Formal representation of semantic triples. | http://www.w3.org/1999/02/22-rdf-syntax-ns |
| RDF Schema (RDFS) | rdfs | Schema used in our knowledge base, as well as DBpedia ontology. | http://www.w3.org/2000/01/rdf-schema |
| Content Ontology | cnt | Used for representing the literal (verbatim) content of extracted annotations.| http://www.w3.org/2011/content |
| DBpedia Ontology | dbpedia | Used for grounding documents' topics with DBpedia ontology resources. | http://dbpedia.org/resoource/|

### Publishing the knowledge base through Fuseki
The knowledge base can be published with [Apache Jena Fuseki](https://jena.apache.org/documentation/serving_data/) that can servce RDF data over HTTP. 

1. You need to [download](https://jena.apache.org/download/#apache-jena-fuseki) Fuseki server first. Follow the instructions on the download page for installation. The experiments descibed in our paper are based on Fuseki version 2.0.0. 
1. The knowledge base triples generated in our experiments are located in the [knowledge-base](../master/knowledge-base) folder. Unzip the [triples.zip](../master/knowledge-base/triples.zip) file to your disk and publish it through Fuseki using either of the following approaches:

   a) You can create an empty dataset with Fuseki and upload the .nq file using the "upload files" tab.

   b) Alternatively, you can use Apache Jena's [TDB-loader command](https://jena.apache.org/documentation/tdb/commands.html#tdbloader) to copy the triples to a directory on your disk and publish the directory through Fuseki:

   ```/JENA_INSTALLATION/bin/tdbloader --loc=/PATH/TO/TRIPLESTORE /PATH/TO/triples.nq```
   
1. After publishing the knowledge base, verify that all of the triples are uploaded. A triple count on the knowledge base should return 1,712,452 triples.

### License

The knowledg-base (triples.zip) is distributed under the terms of the [Creative Commons Attribution License v4.0](https://creativecommons.org/licenses/by/4.0/). You can find a copy of the license in the [knowledge-base](../master/knowledge-base) folder.

[pipeline]: https://github.com/SemanticSoftwareLab/Supplements-ESWC2017/blob/master/graphics/pipeline.png "Pipeline processing resources"
