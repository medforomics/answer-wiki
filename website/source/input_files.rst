Input Files for ANSWER
======================

Manifest File
-------------

Data Files
----------

-  VCF File for all samples (Tumor/Normal)
-  Special Variables in the INFO field (most of optional)
-  ANN: SNPEff Annotation
-  DP: Tumor Read Depth (not optional)
-  AF: Tumor Mutational Allele Frequency (not optional)
-  NormalDP: Normal Read Depth
-  NormalAF: Normal Mutational Allele Frequency
-  RNASeqDP: Normal Read Depth
-  RNASeqAF: Normal Mutational Allele Frequency
-  CallSet: Algorithm used to predict variant
-  GNOMAD\_AF: GNOMAD POPMAX
-  GNOMAD\_HG19\_VARIANT: chr-pos-ref-alt to link to GNOMAD website
-  GNOMAD\_HOM: Number of homozygous samples in GNOMAD

-  CNV Files
-  CNR: Bait Coverage Files (example.answerplot.cnr)
-  CNS: Segment Coverage Files (example.answerplot.cns)
-  TXT: Copy Number Prediction File (example.cnv.answer.txt)
-  B-Allele Freq: File of Common SNP B-Allele Frequency File
   (example.ballelefreq.txt)

-  Viral Results (tab-delimited see example.viral\_results.txt)
-  SampleID: Tumor or Normal Sample ID
-  VirusName: Short Name for Virus
-  VirusAcc: Refseq Genome ID
-  VirusDescription: Genome Name
-  ViralReadCt: Number of Reads

-  TMB (csv see example.TMB.csv)
-  Metric: TMB or MSI
-  Value: Score
-  Class: Classification of Score ie TMB-High or MSS

-  Mutational Signature Files
-  TXT File
-  PNG File

-  RNA Files

   -  FPKM Gene Abundance File
   -  Translocation/Gene Fusion File
   -  Exons Skipping

-  TN Concordance File

Alignment Files for IGV
-----------------------

-  Tumor DNA BAM and BAI
-  Normal DNA BAM and BAI
-  Tumor RNA BAM and BAI

Cbioportal Files
----------------

-  Somatic MAF

