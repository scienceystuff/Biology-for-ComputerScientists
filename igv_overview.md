## Introduction
This writeup provides an overview of how to install and use the Integrated Genome Browser (IGV), as well as a description of the preliminary methods and results for the Radiation Survivor Cohort study.

## Terminology

**Reference Sequence**: Also abbreviated 'REF'. A string of 'A', 'T', 'C', and 'G' characters, which has been created by analyzing multiple datasets of DNA strings from individuals of the same organism. It typically also has features that define substrings of the DNA sequence, such as Gene, Coding Sequence (CDS), exons, and introns. There are several online repositories that store reference sequences for organisms, and each has different organizational nomenclature. The source of a given reference sequence can usually be inferred by the type of identifier present for a feature; for example, XM_015136048.2 is from NCBI.

**Locus**: (plural loci) is a fixed position on a chromosome in the reference sequence of an organism. Usually refers to a gene locus.

**Gene**: A feature present in a reference sequence. The organizational structure of features is Gene -> Transcript -> Exon/Intron. For more information, see [this writeup](https://github.com/scienceystuff/Biology-for-ComputerScientists).

**SNP**: Single Nucleotide Polymorphism. Within this context, this term defines a region of an organism's DNA that has a single character difference when compared to an accepted reference sequence.

**Indel**: Insertion or Deletion. An Insertion is a string of characters that has been added into an organisms's DNA sequence an any position, when the organism's DNA is compared to an accepted reference sequence string. A deletion is a string of characters that is not contained within the organism's DNA sequence, but when this string is compared to an accepted reference sequence, the given string is present.

**IGV**: Short for the Integrated Genome Browser, it is a tool created by the Broad Institute. It has several possible uses, but in this context, it is used to visualize how 

**Allele**: The form of a gene, determined by its DNA sequence. In diploid organisms, there will be two alleles that determine an organism's genotype. For more information, [see this link](https://www.nature.com/scitable/definition/allele-48).

**Genotype**: How a given characteristic of an organism is defined, based on the pairs of alleles. In a diploid organism, if both alleles are the same at a given locus, then the organism has a homozygous genotype for that described characteristic. If one of the pair of alleles is different, then the orgniams has a heterozygous genotype for that described characteristic. 

**Phenotype**: The outward appearance of a feature in an organism, which is defined by one or more genotypes. The organizational structure of phenotype is Phenotype --determined by--> Genotype(s) --determined by--> Gene DNA sequence string

## Install IGV
The Integrated Genome Browser (IGV) is a multi-purpose visualization tool. In this context, it is used to visualize the genotype of an organism, and uses Tracks to show or map data.

Installation instructions can be found on the [IGV website](https://software.broadinstitute.org/software/igv/download), but a brief summary is provided here. Using the IGV-WEB browser-based IGV is not recommended.

* Prerequisites:
  * Java must be installed prior to installation
  * Computer running the latest version of Mac OSX or Windows 10
  * At least 2 GB RAM
  * Mouse with a left and right button (Note: If a 2-button mouse is unavailable, on Mac OSX a right-click can be performed by pressing the Control Key and then clicking, or customizing the track pad under System Preferences).
  
* Steps:
  * Navigate to the [IGV Website](https://software.broadinstitute.org/software/igv/download) and click to download the appropriate version of IGV.
  * Double-click the downloaded file, and run the installer.
![](https://github.com/scienceystuff/Biology-for-ComputerScientists/blob/Latest/data_and_images/igv_screenshot1.png)

## IGV Interface Overview
To begin, note that IGV can be a bit buggy, irrespective of your actions. Save your work frequently, and if you run into a situation where commands do not seem to work, exit IGV and restart it.

IGV typically opens to a blank session. From here, you can continue working on this new session, or open a saved session. These options are available under the 'File' menu.
![](https://github.com/scienceystuff/Biology-for-ComputerScientists/blob/Latest/data_and_images/igv_screenshot2.png)

The following image shows IGV when a VCF file, and the hg38 human genome have been loaded
![](https://github.com/scienceystuff/Biology-for-ComputerScientists/blob/Latest/data_and_images/igv_screenshot3.png)


* View: The window where tracks display data.
* Tracks: How data is displayed in IGV. For example, in the image above, track 1 lists the SNPs that appear for each listed sample, and track 2 lists the Indels that appear for each listed sample. The size of the track can be modified with the mouse, or under settings. Track 3 lists the gene features for the human genome hg38 assembly, and you can visualize how SNPs and Indels map to each gene feature.
  * Track settings: There are numerous track settings, and a full description can be found on the IGV website. In this context, you primarily will need to collapse or expand the track. To expand (show more) or collapse (show less) a track, right click on the track, and select the appropriate setting.
* Gene or Locus Window: You can either enter a gene or a locus for that gene in this window. For example, to view the gene 'ATM', you can either enter 'ATM' in this window, or you can enter 'chr11:108,220,832-108,371,099'.
* Zoom: To zoom in, you can double-click on a given feature of interest. This will also center the view. You can also zoom in and out using the zoom stepper in the upper right hand corner. You can also pan the view by left-clicking and dragging inside a track.
