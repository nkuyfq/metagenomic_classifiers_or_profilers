# metagenomic_classifiers_or_profilers
A repository recording state-of-the-art taxonomic classifiers or profilers for metagenomic sequencing data.
## Introduction
According to previous studies, both taxonomic classifiers and profilers are commonly used in shotgun metagenomics applications which are based on the second or third sequencing technologies. This is typically done by comparing sequencing reads to a database with reference sequences. Notably, there have been so many tools developed for such aims. And scientists are still developing new tools surpassing the earlier ones, especially for the third sequencing technologies which are usually characterized by long read and high error rates. I am trying to track the dynamics of these tools.
## The tools
I will list the tools from the following fields: sequencing platforms, strategy and database. 
| Name  | Sequencing platforms | Strategy | Database | Reference genomes/Pathogenic spectrum |
|:-------:|:---------:|:------:|:------:|:------:|
|[Kraken2](https://github.com/DerrickWood/kraken2)|Short reads|k-mer|DNA|Custom (Bacteria, Archaea, Fungi, Viruses, Protozoa etc.)|
|[Sourmash](https://sourmash.readthedocs.io/en/latest/index.html)|Short and long reads|k-mer|DNA|Custom (Bacteria, Archaea, Fungi, Viruses, Protozoa etc.)|
|[Taxor](https://github.com/JensUweUlrich/Taxor)|Long reads|k-mer|DNA|Custom (Bacteria, Archaea, Fungi, Viruses, Protozoa etc.)|
|[Sylph](https://github.com/bluenote-1577/sylph)|Short and long reads|k-mer|DNA|Custom (Bacteria, Archaea, Fungi, Viruses, Protozoa etc.)|
|[Xtree](https://github.com/two-frontiers-project/2FP-XTree)|Short and long reads|k-mer|DNA|Custom (Bacteria, Archaea, Fungi, Viruses, Protozoa etc.)|
