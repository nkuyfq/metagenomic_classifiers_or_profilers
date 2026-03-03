# metagenomic_classifiers_or_profilers
A repository recording state-of-the-art taxonomic classifiers or profilers for metagenomic sequencing data.
## Introduction
According to previous studies, both taxonomic classifiers and profilers are commonly used in shotgun metagenomics applications which are based on the second or third sequencing technologies. This is typically done by comparing sequencing reads to a database with reference sequences. Notably, there have been so many tools developed for such aims. And scientists are still developing new tools surpassing the earlier ones, especially for the third sequencing technologies which are usually characterized by long read and high error rates. I am trying to track the dynamics of these tools.
## The tools
I will list the tools from the following fields: sequencing platforms, strategy and database. 
| Name  | Sequencing platforms | Strategy | Database | Reference genomes/Pathogenic spectrum | Publish Year |
|:---------:|:-----------:|:---------:|:----------:|:---------:|:---------:|
|[Centrifuge](https://ccb.jhu.edu/software/centrifuge/manual.shtml)|Short reads|Burrows-Wheeler transform (BWT) and the Ferragina-Manzini (FM) index|DNA|Custom (Bacteria, Archaea, Fungi, Viruses, Protozoa etc.)|2016|
|[Kraken2](https://github.com/DerrickWood/kraken2)|Short reads|k-mer|DNA|Custom (Bacteria, Archaea, Fungi, Viruses, Protozoa etc.)|2019|
|[mOTUs 3](https://motu-tool.org/index.html)|Short reads|marker gene|DNA|Bacteria and Archaea|2022|
|[MetaPhlAn4](https://huttenhower.sph.harvard.edu/metaphlan)|Short reads|marker gene|DNA|Bacteria, Archaea and Eukaryotes|2023|
|[KMCP](https://github.com/shenwei356/kmcp)|Short reads|k-mer|DNA|Custom (Bacteria, Archaea, Fungi, Viruses, Protozoa etc.)|2023|
|[SingleM](https://wwood.github.io/singlem/)|Short reads|marker gene|DNA|Bacteria and Archaea|2024|
|[MetaKSSD](https://github.com/yhg926/MetaKSSD)|Short reads|marker gene|DNA|Bacteria and Archaea|2025|
|[Meteor2](https://github.com/pythseq/meteor2)|Short reads|gene catalogue|DNA|Bacteria, Archaea and Eukaryotes|2025|
|[Metamaps](https://github.com/DiltheyLab/MetaMaps)|Long reads|minimizer|DNA|Custom (Bacteria, Archaea, Fungi, Viruses, Protozoa etc.)|2019|
|[Melon](https://github.com/xinehc/melon)|Long reads|marker gene|DNA|Bacteria and Archaea|2024|
|[Taxor](https://github.com/JensUweUlrich/Taxor)|Long reads|k-mer|DNA|Custom (Bacteria, Archaea, Fungi, Viruses, Protozoa etc.)|2024|
|[Lemur + Magnet](https://github.com/treangenlab/lemur)|Long reads|marker gene|DNA|Bacteria, Archaea and Fungi|2024|
|[Sourmash](https://sourmash.readthedocs.io/en/latest/index.html)|Short and long reads|k-mer|DNA|Custom (Bacteria, Archaea, Fungi, Viruses, Protozoa etc.)|2022|
|[Sylph](https://github.com/bluenote-1577/sylph)|Short and long reads|k-mer|DNA|Custom (Bacteria, Archaea, Fungi, Viruses, Protozoa etc.)|2024|
|[Xtree](https://github.com/two-frontiers-project/2FP-XTree)|Short and long reads|k-mer|DNA|Custom (Bacteria, Archaea, Fungi, Viruses, Protozoa etc.)|2025|

