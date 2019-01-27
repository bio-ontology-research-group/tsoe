# Task Specific Ontology Evaluation
## Guide to the Ontology evaluation data
- The data and source code usedin this project can be accessed at: http://bio2vec.net/data/goplus_contribution/
- The data folder contains two main directories *source* and *ontologies*:
### Source:
- This directory contains the main source code used in this project:
    - *ProcessOntology.groovy*: used to reason over ontologies and extract axioms and classes.
    - *getMetadata.groovy*: used to extract metadata annotation properties from ontologies.
    - *AddAncestors.pl* : used to propagate protein-GO associations over the GO hierarchy.
    - *runWord2Vec1.py* :used to obtain protein vector representations from ontology axioms and GO associations.
    - *runWord2Vec2.py* : used to obtain protein vector representations from ontology axioms, ontology metadata and GO associations using a pre-trained Word2Vec model (pre-trained model available at: http://bio2vec.net/data/pubmed_model/)
    - *ParseGOA.pl* : used to extract GO associations from GOA file.
    - *getPPImapping.pl* : used to extract Uniprot PPI mappings from STRING network and mapping file.
    - *process_vectors.py*: used to simplify the vectors output for further processing by merging each protein's vector in one line.
    - *getVecsOnly.pl*: used to extract the numerical vectors only from Word2Vec output.
    - *getCosineSim.py*: used to calculate the pairwise vector cosine similarity for a list of protein pairs in an input file.
### Ontologies:
- This directory contains a set of subdirectories, each corresponding to one of the following ontologies: GO, GO-PLUS, CL, CHEBI, UBERON, PO, PATO, SO, FAO, OBA, CARO, PR, NCBITaxon and Phenomenet.
- Each of the directories contains the following files:
    -   *axioms.lst*: all logical axioms of that ontology.
    -   *goplus_*****.lst*: the inter-ontology axioms in GO-plus referring to concepts in this ontology.
    -   *metadata.lst*: annotation property axioms of this ontology.
    -   *ontology_corpus1*: corpus containing GO axioms and the inter-ontology axioms in GO-plus corresponding to that ontology.
    - 	*ontology_corpus2*: corpus containing GO axioms, the logical axioms from this ontology and the inter-ontology axioms in GO-plus corresponding to that ontology.
    -	*ontology_corpus3*:corpus containing GO axioms, the logical axioms from this ontology, the inter-ontology axioms in GO-plus corresponding to that ontology, GO metadata and the metadata from this ontology.
    -	*Vectors1*: The vectors obtained from running *runWord2Vec1.py* over *ontology_corpus1* and the protein-GO associations.
    -   *Vectors2*: The vectors obtained from running *runWord2Vec1.py* over *ontology_corpus2* and the protein-GO associations.
    -   *Vectors3*: The vectors obtained from running *runWord2Vec2.py* over *ontology_corpus3* and the protein-GO associations.
- The *Phenomenet* directory contains:
    -   *axioms.lst*: list of logical axioms of Phenomenet.
    -   *allaxioms.lst*: axioms when using GO-plus with Pheneomnet.
    -   *DiseasePheno_Assoc.lst*: Disease to phenotype associations.
    -   *GenePheno_Assoc.lst*: Gene to phenotype associations.
    -   *Filtered_Vectors.lst*: List of vectors obtained for the genes and diseases listed.

## Final notes
For any comments or help needed, please send an email to: fzohrasmaili@gmail.com
