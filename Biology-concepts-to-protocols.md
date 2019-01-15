## Concepts to Protocols

* This README links Biology concepts to the protocols that use them.

* Prerequisites: Basic knowledge of Biology, or an understanding of the [Biology Key Concepts README](https://github.com/scienceystuff/Biology-for-ComputerScientists/blob/master/Biology-key-concepts.md) and the [Immunology Key Concepts README](https://github.com/scienceystuff/Biology-for-ComputerScientists/blob/master/Biology-Immunology-concepts.md).

### Next Generation Sequencing (abbreviated NGS)

NGS is the description for the latest techniques and technology in DNA and RNA sequencing.  DNASeq and RNASeq are described here.

### DNA Sequencing (abbreviated DNASeq)
DNASeq determines the string of characters that comprise the total DNA of an organism.  Depending on the organism, its total DNA can be kilobases, megabases, or gigabases long.  There is a two-step process for DNASeq: wet-lab and *in-silico*

* Wet Lab
  * Wet Lab is a semi-official term in biology for any work done at the lab bench (with liquids, i.e. "wet"), such as growing or treating cells, and preparing a DNASeq library.
  * DNASeq has the following steps:
    * Extracting DNA from cells (including bacteria, if applicable)
    * Fragmenting the DNA to a set of overlapping substrings S that comprise the original DNA string D (note the exception below)
    * Using a commercial sequencer such as MiSeq from [Illumia](), PacBio from [Pacific Biosciences](), GridIon from [Oxford Nanopore Technologies]() abbreviated ONT, or Ion Proton from [Life Technologies]().  The differences among the commercial sequencers is beyond the scope of this README, but a few key points are:
      * Illumina hardware creates paired end reads, unless specifcally set up otherwise.  
      * Life Technologies hardware creates single-end reads only
      * ONT hardware creates long reads, that may be either single or paired end.
      * PacBio hardware creates long reads that are single end, and does not fragment DNA
      
* *In-Silico*
  * *In-silico*, literally "with silicon", is a semi-official term in biology for any computer-work as part of a scientific experiment
  * DNASeq may be performed for a number of different experiments.  *Very* briefly, the goal of *in-silico* work is to determine the original DNA string sequence from the output from the sequencer hardware, the purpose being to address an exeprimental hypothesis.
  * Depending on the experiment and the hypothesis, numerous algorithms and software exist to determine the aforementioned goal.  A few are mentioned here:
    * The [Burrows-Wheeler Transform](https://academic.oup.com/bioinformatics/article/25/14/1754/225615) creates a suffix array from an organism with a pre-determined DNA reference sequence string, and then matches the reads from the sequencer to their respective positions in the DNA reference string.
    * Bowtie and Bowtie2 are part of the [Tuxedo Suite](https://support.illumina.com/help/BS_App_RNASeq_Alignment_OLH_1000000006112/Content/Source/Informatics/Apps/TuxedoSuite_RNASeqTools.htm) of Bioinformatics software.  They use a suffix array, FM Index, and others.
    * [BBmap](https://jgi.doe.gov/data-and-tools/bbtools/bb-tools-user-guide/bbmap-guide/) uses a seed-extension algorithm to match the sequenced reads to their positions in the DNA reference string.
    * If no predetermined DNA reference sequence exist, then a [*de novo*](https://www.nature.com/articles/nmeth.1935) assembler is used instead.  
    
    
### RNASeq
RNASeq determines the string of characters that comprise the extracted RNA from an organism.  This may be the entire RNA (the transcriptome), or a specific set of RNA.  If a subset of RNA (or DNA) is repeatedly sequenced to increase the overall amount, this is called enrichment.  

Most of the wet lab steps are the same for DNASeq and RNASeq, or their differences are unimportant in the context of this README.  There are several differences for the *in-silico* steps, depending on if a reference string is available for the organism, and if the RNA was from a prokaryote or eukaryote organism.

If the RNA was from a prokaryote, then no splicing occurs, and DNASeq software and algorithms can typically be used.

If the RNA was from a eukaryote, then software that accounts for splicing **must** be used in the analysis.  A few examples are:

* [Trinity](https://github.com/trinityrnaseq/trinityrnaseq/wiki): designed for RNAseq *de novo* assembly, and can account for splicing
* [HISAT2](https://ccb.jhu.edu/software/hisat2/index.shtml): designed for RNASeq mapping (to a known reference sequence), and can account for splicing
* [STAR](https://github.com/alexdobin/STAR): designed for RNASeq mapping (to a known reference sequence), and can account for splicing
  
### Glossary

**read:** A single copy of the fragmented DNA string D.  In the case of PacBio, it is a substring S of the original, unfragmented DNA string D.
**library:** The fragmented DNA string F that will be determined as part of the sequencing process to define the unknown, original, unfragmented DNA string D
**paired end reads:** Given a DNA string S, two substrings d1 and d3 are created, with an unsequenced gap d2 in the middle called the insert. All paired end reads are combined to re-create the original and un-fragmented DNA string D, and the pairs of reads are used to validate both the consensus string, and the insert strings that were not sequenced.
        
        Example:
        DNA String:          AATTCCGGAATTGGAACC
        Read 1 Pair 1:       AATTCC
        Read 1 Pair 2:                   GGAACC
        Read 2 Pair 1:          TCCGAA     
        Read 2 Pair 2:                     AACC
        
        
**single end reads:** Given a DNA string S, a substring d1 is created. All reads are combined to re-create the original and un-fragmented DNA string D, and overlap among the sequenced reads is used to validate the position and accuracy of substrings.
        
        Example:
        DNA String:   AATTCCGGAATTGGAACC
        Read 1:       AATTCC
        Read 2:                   GGAACC
        Read 3:           CCGGAATT

