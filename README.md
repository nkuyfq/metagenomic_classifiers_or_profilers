# metagenomic_classifiers_or_profilers
A repository recording state-of-the-art alignment-based taxonomic classifiers or profilers for metagenomic sequencing data.
## Introduction
According to previous studies, both taxonomic classifiers and profilers are commonly used in shotgun metagenomics applications which are based on the second or third sequencing technologies. This is typically done by comparing sequencing reads to a database with reference sequences. Notably, there have been so many tools developed for such aims. And scientists are still developing new tools surpassing the earlier ones, especially for the third sequencing technologies which are usually characterized by long read and high error rates. I am trying to track the dynamics of these tools.
## The classifiers or profilers
I will list the tools from the following fields: sequencing platforms, strategy and database. 
| Name  | Sequencing platforms | Strategy | Type | Reference genomes/Pathogenic spectrum | Publish Year |
|:---------:|:-----------:|:---------:|:----------:|:---------:|:---------:|
|[Centrifuge](https://ccb.jhu.edu/software/centrifuge/manual.shtml)|Short reads|Burrows-Wheeler transform (BWT) and the Ferragina-Manzini (FM) index|DNA-to-DNA|Custom (Bacteria, Archaea, Fungi, Viruses, Protozoa etc.)|2016|
|[Kraken2](https://github.com/DerrickWood/kraken2)|Short reads|k-mer|DNA-to-DNA|Custom (Bacteria, Archaea, Fungi, Viruses, Protozoa etc.)|2019|
|[mOTUs 3](https://motu-tool.org/index.html)|Short reads|marker gene|DNA-to-marker|Bacteria and Archaea|2022|
|[MetaPhlAn4](https://huttenhower.sph.harvard.edu/metaphlan)|Short reads|marker gene|DNA-to-marker|Bacteria, Archaea and Eukaryotes|2023|
|[KMCP](https://github.com/shenwei356/kmcp)|Short reads|k-mer|DNA-to-DNA|Custom (Bacteria, Archaea, Fungi, Viruses, Protozoa etc.)|2023|
|[SingleM](https://wwood.github.io/singlem/)|Short reads|marker gene|DNA-to-marker|Bacteria and Archaea|2024|
|[MetaKSSD](https://github.com/yhg926/MetaKSSD)|Short reads|marker gene|DNA-to-marker|Bacteria and Archaea|2025|
|[Meteor2](https://github.com/pythseq/meteor2)|Short reads|gene catalogue|DNA-to-marker|Bacteria, Archaea and Eukaryotes|2025|
|[Metamaps](https://github.com/DiltheyLab/MetaMaps)|Long reads|minimizer|DNA-to-DNA|Custom (Bacteria, Archaea, Fungi, Viruses, Protozoa etc.)|2019|
|[Melon](https://github.com/xinehc/melon)|Long reads|marker gene|DNA-to-marker|Bacteria and Archaea|2024|
|[Taxor](https://github.com/JensUweUlrich/Taxor)|Long reads|k-mer|DNA-to-DNA|Custom (Bacteria, Archaea, Fungi, Viruses, Protozoa etc.)|2024|
|[Lemur + Magnet](https://github.com/treangenlab/lemur)|Long reads|marker gene|DNA-to-marker|Bacteria, Archaea and Fungi|2024|
|[Sourmash](https://sourmash.readthedocs.io/en/latest/index.html)|Short and long reads|k-mer|DNA-to-DNA|Custom (Bacteria, Archaea, Fungi, Viruses, Protozoa etc.)|2022|
|[Sylph](https://github.com/bluenote-1577/sylph)|Short and long reads|k-mer|DNA-to-DNA|Custom (Bacteria, Archaea, Fungi, Viruses, Protozoa etc.)|2024|
|[Xtree](https://github.com/two-frontiers-project/2FP-XTree)|Short and long reads|k-mer|DNA-to-DNA|Custom (Bacteria, Archaea, Fungi, Viruses, Protozoa etc.)|2025|
## The tools or wrappers for downloading reference genomes
I will list the tools or wrappers for downloading reference genomes from NCBI RefSeq or GenBank.  
### 1.**centrifuge-download** from Centrifuge  
It's provided by the classifier Centrifuge [Centrifuge](https://ccb.jhu.edu/software/centrifuge/manual.shtml). Based on the **ftp_path** field in the assembly_summary.txt downloaded from, for example, the RefSeq (https://ftp.ncbi.nlm.nih.gov/genomes/refseq/bacteria/assembly_summary.txt) or GenBank Bacteria (https://ftp.ncbi.nlm.nih.gov/genomes/genbank/bacteria/assembly_summary.txt) directory, this Perl wrapper can download complete genomes or scaffolds of Archaea, Bacteria, Fungi, Invertebrate, Protozoa, Vertebrate and Virus from NCBI RefSeq and GenBank with multi-threads. It's suitable for building index for Centrifuge. Anyway, the downloaded sequences are also useful for other classifiers to build custom databases, like [Kraken2](https://github.com/DerrickWood/kraken2), [Sourmash](https://sourmash.readthedocs.io/en/latest/index.html) and [Sylph](https://github.com/bluenote-1577/sylph).  

Note: this wrapper will uncompress downloaded sequences (either complete genomes or scaffolds or contigs) into flat fasta files, which will cost hard-disk spaces especially when you plan to download Invertebrate and Vertebrate sequences.

### 2.**kraken2-build** from Kraken2  
It's provided by the classifier [Kraken2](https://github.com/DerrickWood/kraken2). Based on the command *kraken2-build*, users are able to download and build custom databases. According to the [manual page](https://github.com/DerrickWood/kraken2/wiki/Manual#custom-databases), the command *kraken2-build* will download complete genomes of Archaea, Bacteria, Fungi, Protozoa, and Virus from NCBI RefSeq or NCBI non-redundant protein/nucleotide databases. This command provide a one-stop method to build custom databases for Kraken2.

Note: this wrapper will only download complete genomes of pathogens from NCBI **RefSeq**, which might not suit your needs. The pre-built databases can be accessed through https://benlangmead.github.io/aws-indexes/k2.

### 3.genome_updater
I will directly quote the introduction from [genome_updater](https://github.com/pirovc/genome_updater). It is a bash script that downloads and updates (non-redundant) snapshots of the NCBI Genomes repository (RefSeq/GenBank) with advanced filters, detailed logs and reports, file integrity checks (MD5, gzip), NCBI taxonomy and GTDB integration and support for parallel downloads. genome_updater uses the assembly_summary.txt to retrieve data. Moreover, genome_updater is able to filter or keep a limited number of assemblies for each taxa. For example, *Escherichia coli* has thousands of genomes in RefSeq, users can choose to download only a small subset of *E. coli* sequences by using the "-A" option. It will download compressed files from NCBI or GTDB, which will use less hard-disk spaces than centrifuge-download.

Note: The format change of **ftp_path** field in the assembly_summary.txt might cause download failures when you use genome_updater in some cases. So be careful to check the supported format (e.g., https://ftp.ncbi.nlm.nih.gov/genomes/all/GCF/036/600/855/GCF_036600855.1_ASM3660085v1). If the last character of **ftp_path** field is a slash, this bash script will fail to run.

## The tools for dereplicating reference genomes
Classifiers like [Sylph](https://github.com/bluenote-1577/sylph) and [Xtree](https://github.com/two-frontiers-project/2FP-XTree) use de-replicated reference genomes to avoid abundance bias. For Archaea and Bacteria, the recommended tools are [skDER](https://github.com/raufs/skDER) and [dRep](https://drep.readthedocs.io/en/latest/overview.html). For Virus, the recommended tool is [vclust](https://github.com/refresh-bio/vclust).

