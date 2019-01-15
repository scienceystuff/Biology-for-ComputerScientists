## Immunology Concepts

* Prerequisites: Basic knowledge of Biology, or a readthrough of the [Biology Key Concepts](https://github.com/scienceystuff/Biology-for-ComputerScientists/blob/master/Biology-key-concepts.md)

Immunology is an extremely complex field, and the goal is to provide a generalized overview of important concepts as they relate to Bioinformatics.  At a fundamental level, the immune system constantly surveils for bacteria, viruses, fungi, or other foreign threats (non-self) that can harm the organism (self), which it accomplishes in several ways.  Briefly, the human immune system recognizes a foreign threat by examining a surface protein sequence on cells called the Human Leukocyte Antigen (HLA), or Major Histocompatibility Complex (MHC) in non-human animals. Foreign threats will not have the HLA-I (or MHC-I) protein, and will be targeted for attack. It should be noted that the immune system is in a constant "arms race" against foreign threats, and several microorganisms have evolved ways to hide from detection by this surveillance.

The HLA-I (MHC-I) protein is important, because it helps to identify and target cells that should be attacked, while avoiding attacking host organism cells.  An important concept to grasp is that immune cells do not have "eyes"; they can only identify foreign microorganisms if they do not submit the proper "all clear" signal, which is the MHC-I complex that is unique to the host organism.  This is also why organ transplantation requires matching of the HLA-I and not just the same blood type.  Regardless if the organ is critically needed by the host, if the cells in a transplanted organ do not display the exact (or nearly exact, in the case of an organ match for transplants) HLA-I protein, the immune system will attack the cells in the transplanted organ and destroy the organ.

There is also a second HLA protein, called the HLA-II (MHC-II).  This protein is only used by Professional Antigen Presenting Cells, or specialized cells of the Innate Immune System and Adaptive Immune System who identify an antigen (a short string of proteins) that is part of a foreign threat, and then present this antigen to other cells, thereby activating an Immune System response.

There are numerous potentially harmful (called pathogenic) microorganisms that can attack an organism.  Very broadly, they can be grouped into two categories: Intracellular, and Extracellular.  Intracellular is defined as a pathogen (or harmful microorganism) that will only affect the host organism if it is inside one of the host organism's cells.  Extracellular is defined as a pathogen that will harm the host organism's cells after it has initially breached immune system defenses, is inside the host organism, but not inside any host organism cells (or rather, it will harm the host organism's cells, but it will not enter inside any of the host organism's cells). Three types of pathogens will be introduced: viruses, bacteria, and fungi.

* Viruses
  * Are neither prokaryote not eukaryote, but usually behave in a similar manner to the host organism that they are infecting
  * Are always intracellular
  * Viruses attack cells in the organism by evading detection from immune system surveillance, sneaking past the protective outer membrane of cells, evading built-in defenses and detection within the cell, and then using the metabolic machinery of the cell to create more virus copies.
  * Sometimes this process results in inexact copies of the virus being produced (mutations), which can lead to changes in how the virus functions.  An example is the Influenza (Flu) virus, which frequently undergoes mutations.
* Bacteria
  * Are prokaryotes
  * Are usually extracellular, but can be intracellular
  * Bacteria attack cells in the organism by evading detection from immune system surveillance, then causing harm to nearby cells, usually by the release of toxins that are produced by the bacteria, or by out-competing host cells for nutrients.
* Fungi
  * Are eukaryotes
  * Are nearly always extracellular, but rarely can be intracellular
  * Fungi harm cells in the organism by evading detection from immune system surveillance, then causing harm to nearby cells, usually by the release of toxins that are produced by the bacteria, or by out-competing host cells for nutrients.


The immune system can be described hierarchically as follows:

![](data_and_images/ImmuneSystem_overview.png)

Immune System
* Innate -> activates Adaptive, surveils for foreign microorganisms
* Adaptive  -> focused defense against foreign microorganisms, provides continued defense against pre-recognized foreign microorganisms
* Other Immunity -> Nonspecific immunity that serves as a first barrier against foreign microorganisms, such as friendly (commensal) bacteria on the skin that prevent the growth of harmful (pathogenic) bacteria

To attack an extracellular microorganism, the B-cells of the immune system are trained to recognize a foreign antigen sequence (string), and then create an antibody that will bind to any sequence string matching it. To attack an intracellular microorganism, the immune system will train CD8+ T-cells to look for a specific change in the sequence of the HLA-I (MHC-I) protein, and if a cell shows this change, then the CD8+ T-cell will take control of that cell and trigger apoptosis.  Apoptosis is the ordered self-destruct function that a cell can undergo when it has been infected by an intracellular microorganism, if it is behaving incorrectly, or if it has reached a certain age.


### Glossary

apoptosis: the function that triggers a controlled and ordered self-destruct of a cell

B-cell: a cell within the Adaptive Immune System that creates antibodies

CD4+ T-cell: a cell within the Adaptive Immune System that signals nearby host cells, including Immune System Cells, to take action against a foreign microorganism

CD8+ T-cell: a cell within the Adaptive Immune System that searches for host cells that do not display the correct HLA-I (MHC-I) protein sequence, and then orders any such cells to start apoptosis

Dendritic cell: a professional antigen-presenting cell that is part of the Innate Immune System. It also removes cellular debris.

Macrophage: a professional antigen-presenting cell that is part of the Innate Immune System.  It also removes cellular debris
