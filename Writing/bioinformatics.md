---
title: 'SnpReportR: A Tool for Clinical Reporting of RNAseq Expression and Variants'
tags:
  - Expression
  - Precision Medicine
  - Human Genomics
  - RNA-Seq
  - Clinical Report
  - Genetic testing
  - Reporting research results
  - Variants
  - Genetic test reports

authors:

  - name: Ahmad Al Khleifat 
	Ahmad.al_khleifat@kcl.ac.uk	
	orcid: 0000-0002-7406-9831
affiliation: Institute of Psychiatry, Psychology & Neuroscience, King's College London. Maurice Wohl Clinical Neuroscience Institute
	5 Cutcombe Road, Denmark Hill, London, SE5 9RX 
  - name: Jenny Leopoldina Smith
	jlsmith3@fredhutch.org
affiliation: Clinical Research Division, Fred Hutchinson Cancer Research Center
	1100 Fairview, Ave., Seattle, WA, 98109
	orcid: 0000-0003-0402-2779
  - name: Brandon M. Blobner
	bmb83@pitt.edu
	orcid: 0000-0003-0734-1492
affiliation: Division of Gastroenterology, Hepatology and Nutrition, Department of Medicine, University of Pittsburgh, 4200 Fifth Avenue, Pittsburgh, PA 15260
  - name: Sierra D. Miller
	sierra.miller@nist.gov
orcid: 000-0002-3200-428X
affiliation: National Institute of Standards and Technology, 100 Bureau Drive, Gaithersburg, MD 20899-8970
  - name: Kymberleigh Pagel
kpagel1@jhu.edu 
orcid: 0000-0001-8544-925
affiliation: Institute for Computational Medicine, Johns Hopkins University
220 Hackerman Hall. 3400 N. Charles St.
Baltimore, MD  21218
  - name: Annie Nadkarni
	anadkarn@andrew.cmu.edu
	affiliation: Carnegie Mellon University, School of Computer Science
	5000 Forbes Ave, Pittsburgh, PA 15213
  - name: Melanie Gainey
	mgainey@andrew.cmu.edu
	orcid: 0000-0002-4782-9647
	affiliation: Carnegie Mellon University Libraries
	4909 Frew Street, Pittsburgh, PA, 15213
  - name: Olaitan I. Awe
	laitanawe@gmail.com 
	orcid: 0000-0002-4257-3611
	affiliation: University of Ibadan
  - name: Manuel Belmadani
	manuel.belmadani@pm.me
	orcid: 0000-0002-5820-5979
  - name: Alan M. Cleary
	acleary@ncgr.org
	orcid: 0000-0002-6567-5346
affiliation: National Center for Genome Resources, 2935 Rodeo Park Dr E, Santa Fe, NM 87505
  - name: Nicholas P. Cooley
	npc19@pitt.edu
	orcid: 0000-0002-6029-304X
affiliation: Department of Biomedical Informatics, University of Pittsburgh
  - name: Shamika Dhuri
	dhurishamika@gmail.com 
	orcid: 0000-0003-3931-5694
	affiliation: Carnegie Mellon University, Mellon College of Science 
	5000 Forbes Ave, Pittsburgh, PA 15213
  - name: Virginie Grosboillot
	virginie.grosboillot@hest.ethz.ch
	orcid: 0000-0002-8249-7182
affiliation: Laboratory of Food Microbiology, Institute for Food, Nutrition and Health, ETH Zurich, Zurich, Switzerland 
  - name: Brian Haas
bhaas@broadinstitute.org
affiliation: Broad Institute
415 Main Street, Cambridge, MA 02142 
  - name: Samuel Hokin
	shokin@ncgr.org
	orcid: 0000-0002-9746-2783
affiliation: National Center for Genome Resources, 2935 Rodeo Park Dr E, Santa Fe, NM 87505
  - name: Ekaterina Orlova
	eko8@pitt.edu	
	orcid: 0000-0002-7129-5796
affiliation: Department of Human Genetics, Graduate School of Public Health, University of Pittsburgh, 130 De Soto Street, Pittsburgh, PA, 15261
  - name: Meghana Pagadala
mpagadal@ucsd.edu
orcid: 0000-0002-7591-6035
affiliation: University of California San Diego
9500 Gilman Dr, La Jolla, CA 92093
  - name: Stephen Price
	sprice1@andrew.cmu.edu
	orcid: 0000-0001-9072-7518
affiliation: Carnegie Mellon University, 5000 Main Street, Pittsburgh, PA 15213
  - name: Adelaide Rhodes
	adelaide.rhodes@nih.gov
	orcid: 0000-0002-1714-1972
	affiliation: National Center for Biotechnology Information
	National Library of Medicine
	8600 Rockville Pike
	Bethesda, MD 20894
  - name: Janice Kyla Nascimento Smith
	janice.k.n.smith@gmail.com 
	affiliation: Software Engineer
	Boston, MA, 02109
  - name: Chaitanya Srinivasan
	csriniv1@andrew.cmu.edu 
	orcid: 0000-0002-1487-541X
affiliation: Computational Biology Department, School of Computer Science, Carnegie Mellon University, 5000 Forbes Ave, Pittsburgh, PA 15213
  - name: Barry Zorman
	Barry.Zorman@bcm.edu
	affiliation: Baylor College of Medicine
	Houston, TX 77030
  - name: Ben Busby
orcid: 0000-0001-5267-4988
affiliation: DNAnexus
1975 El Camino, Mountain View, CA

date: 7 June 2021
bibliography: paper.bib
---
# Abstract

With the increasing availability of next-generation sequencing (NGS), patients and non-specialists health care professionals are obtaining their genomic information without sufficient bioinformatics skills to analyze and interpret the data. In January 2021, four teams of scientists, clinicians, and developers from around the world worked collaboratively in a virtual hackathon to create a framework for the automated analysis and interpretation of RNA sequencing data in the clinic. Here, we present SnpReportR : A Tool for Clinical Reporting of RNAseq Expression and Variants aimed for use by clinicians and others without in-depth knowledge of genetics.


# Introduction

In clinical practice and biomedical research, next-generation sequencing (NGS) and subsequent identification of genomic variants including single nucleotide variations or polymorphisms, small insertions or deletions, and structural variants is an established method used to investigate the genetic causes and associations of disease. While whole genome and whole exome sequencing are relatively expensive, RNA-sequencing (RNA-seq) is a highly cost-effective and versatile method that assays both gene sequence and expression, thus yielding both genetic and functional signatures in a single technique (Hong et al., 2020; Horak et al., 2016; Narrandes and Xu, 2018). In cancer diagnostics, specifically, RNA-Seq provides a means of detecting nucleotide-level resolution of mutations within transcribed regions of oncogenes and tumor suppressor genes for expressed loci.


While RNA-seq is a powerful tool for characterizing tumors, identifying and interpreting the variants that are relevant to the diagnosis or understanding of disease within a patient remains challenging. The biopsy tissue sampled for the analysis can be composed of a mix of tumor and normal cells that leads to averaged gene expression data from a heterogeneous mixture of cells (Yoshihara et al., 2013; Fan et al., 2020). Another practical challenge for using gene expression data is the need for sophisticated tools that may require significant bioinformatics expertise and high-performance computing to carry out the data processing and analysis (Fernald et al., 2011). For those outside the immediate field of genetics such as researchers, hospital staff, the interpretation of findings is particularly challenging. Therefore, it is important to have tools that take into account these gaps in specialized bioinformatics knowledge. 


We, therefore, developed SnpReportR, a clinical genetic reporting framework for the automated analysis and interpretation of RNA sequencing data. The software is designed for use by clinicians and other users without an in-depth background in genetics. 


# Methods

In a coordinated codeathon, teams worked collaboratively with the same dataset to provide a framework for clinical reporting of RNA-Seq research. The gene expression datasets used as test data in this study were obtained from publicly available databases from The DataBase of Kashiwa Encyclopedia of Researchers of multi-Omics data (DBKERO) (https://kero.hgc.jp/). The raw cell files were reanalysed using HISAT2 and featureCounts to obtain summarised expression values for transcripts. Differential expression was performed by using edgeR. CAVIAR was then used to distinguish causal variants from other signals in the data, such as population stratification.The vcf files produced from the CTAT Mutations pipeline v2.5 are analyzed using vcfR v1.12.0 and the bioconductor package Variant Annotation v1.36.0. Genomic visualizations are completed with Gviz v1.34.1 and the snpReportR tool provides a helper function to create genomic references for use with Gviz .  Finally, the tool generates two reports, one is aimed for clinical use and the second aimed for researchers, informing the interpretation of genetic variants pertaining to the gene provided by the user. Both reports provide RNA-Seq summary analysis which includes diseases association, disease gene identification, gene prioritization, tissue expression information, supported with data visualisation and 5 recent publications related to the identified gene.  Tissue expression, disease association, publication, and snp data for differentially expressed genes is extracted from HumanMine (Smith et al., 2012) using the InterMineR v1.1 R package.  These multifaceted and integrated results were used to construct an interactive clinical report, which is sent to the user via gmailr (Jim Hester, 2019) and the HTML email produced using the Blastula v.0.3.2. The report  is generated using a customized Rmarkdown template with parameterized inputs, which allows for easy customization.


## Test Data

For demonstration purposes, we identified a dataset that was agreeable for all teams’ efforts and was used solely as an example for showcasing the workflow. This does not represent the kind of patient-level data that would be best suited to this analysis pipeline. The resulting dataset is a lung cancer dataset (Suzuki et al., 2019; ENA accession: PRJDB6952) corresponding to 23 lung cancer cell lines treated with 95 compounds including approved receptor tyrosine kinase inhibitors and epigenetic targeting drugs. High-throughput RNA-seq was conducted with four different drug concentrations at three time points (24,48,72h).

## Tables, figures and so on

Please remember to introduce tables (see Table 1) before they appear on the document. We recommend to center tables, formulas and figure but not the corresponding captions. Feel free to modify the table style as it better suits to your data.

Table 1. Three cell lines and four treatments were included for testing (124 total samples). 
(Suzuki et al., 2019; ENA accession: [PRJDB6952]( https://ddbj.nig.ac.jp/BPSearch/bioproject?acc=PRJDB6952)) 
| Cell Line | Drug | Number of Samples |
| -------- | -------- | -------- |
| A549 | (+)-JQ1 (Inhibitor_BET (BRD4)) | 12 |
| | DMSO (Control) | 9 |
|  | Etoposide (Inhibitor_Topo II) | 11 |
|  | Temsirolimus (Inhibitor_mTOR) | 11 |
| H1299 | (+)-JQ1 (Inhibitor_BET (BRD4)) | 11 |
|  | DMSO (Control) | 9 |
|  | Etoposide (Inhibitor_Topo II) | 12 |
|  | Temsirolimus (Inhibitor_mTOR) | 11 |
| II-18 | (+)-JQ1 (Inhibitor_BET (BRD4)) | 8 |
|  | DMSO (Control) | 8 |
|  | Etoposide (Inhibitor_Topo II) | 11 |
|  | Temsirolimus (Inhibitor_mTOR) | 11 |


![BioHackrXiv logo](./biohackrxiv.png)
 
Figure 1. A figure corresponding to the logo of our BioHackrXiv preprint.

# Other main section on your manuscript level 1

Feel free to use numbered lists or bullet points as you need.
* Item 1
* Item 2

# Discussion and/or Conclusion

We recommend to include some discussion or conclusion about your work. Feel free to modify the section title as it fits better to your manuscript.

# Future work

And maybe you want to add a sentence or two on how you plan to continue. Please keep reading to learn about citations and references.

For citations of references, we prefer the use of parenthesis, last name and year. If you use a citation manager, Elsevier – Harvard or American Psychological Association (APA) will work. If you are referencing web pages, software or so, please do so in the same way. Whenever possible, add authors and year. We have included a couple of citations along this document for you to get the idea. Please remember to always add DOI whenever available, if not possible, please provide alternative URLs. You will end up with an alphabetical order list by authors’ last name.

# Jupyter notebooks, GitHub repositories and data repositories

* Please add a list here
* Make sure you let us know which of these correspond to Jupyter notebooks. Although not supported yet, we plan to add features for them
* And remember, software and data need a license for them to be used by others, no license means no clear rules so nobody could legally use a non-licensed research object, whatever that object is

# Acknowledgements
Please always remember to acknowledge the BioHackathon, CodeFest, VoCamp, Sprint or similar where this work was (partially) developed.

# References

Leave thise section blank, create a paper.bib with all your references.
