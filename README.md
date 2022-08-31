# Genetic Contributions to Urgency Urinary Incontinence in Women
**Repository Authors:** Megan Carnes (mcarnes@rti.org) and Jesse Marks (jmarks@rti.org)

Updated analyses for the paper [Genetic Contributions to Urgency Urinary Incontinence in Women](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4439377/) Richter et al. 2015.

The Repository Authors reran the GWAS in the Richter et al. paper with some updates and additional analyses. See the description below.

---

<br><br>

The Women’s Health Initiative (WHI) is a long-term, multi-site longitudinal study funded by the National Heart, Lung, and Blood Institute. The WHI collected data on urgency urinary incontinence from all participants at enrollment and closeout and from a subset of women at intervals throughout the study. The WHI-Genomics & Randomized Trials Network (GARNET) is a sub-study with 4,894 genotyped post-reproductive white women funded by National Human Genome Research Institute.  

We previously published a GWAS using the GARNET sub-study comparing 1,102 cases to 405 controls in the discovery cohort and 1,133 cases  to 371 controls in the replication cohort (2,235 UI cases and 776 UI controls total). For this study, we updated the GARNET study UI GWAS using a modern automated analytic pipeline. The updated analysis includes a revised list of modeled covariates, ancestry defined by comparison to 1000 Genomes instead of HapMap, and an extra LiftOver step that allows for imputation against the most updated reference panel ([TOPMed](https://imputation.biodatacatalyst.nhlbi.nih.gov/#!pages/home)). See details below. The newly generated GWAS results closely resemble the original study and the top genes remained consistent. The data were downloaded from the database of Genotype and Phenotypes ([dbGaP](dbgap.ncbi.nlm.nih.gov/)) Study Accessions: phs000200.v12.p3 and phs000315.v8.p3.  

Quality control was performed with an open-source automated [genotype array qc workflow](https://github.com/RTIInternational/biocloud_gwas_workflows/tree/master/genotype_array_qc) developed by RTI International. Quality control was performed on each consent group separately. Genotype variants were filtered based on deviation from Hardy-Weinberg equilibrium (0.0001) and low call rate (0.03). Ancestral background of the samples was determined using [STRUCTURE](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1461096/) with the 1000G reference populations EUR, CHB, and YRI using the definition EUR=CHB<0.25 && YRI<0.25. Samples were removed based on the following filtering criteria: relatedness, low call rate, excessive homozygosity, and sex discrepancies. The two consent groups were combined post genotype QC and imputed together with the TOPMed imputation server using the TOPMed reference panel with Minimac4 v1.5.7 and Eagle v2.4. TOPMed imputation converts genomic coordinates to GRCh38. SNPs were filtered based on a sample MAF filter of 0.01 and imputation quality (rsq) of 0.8.  

Cases were defined as women who at any time during the study (self-) reported they had symptoms of UUI, reporting that they usually leak when they feel the need to urinate and can’t get to the toilet fast enough, more than once a month, and who leaked sufficiently to wet or soak their underpants or clothes. Controls were defined as women who initially did not report UUI and did not develop it during the study.  Covariates included (1) age, defined as the participant age at enrollment and treated as a continuous variable, (2) obesity, defined as body mass index (BMI) of 30 kg/m2 or greater, (3) diabetes, defined as reporting being told by a doctor they had diabetes, (4) parity, defined as nulliparous, 1–2 births, 3 or more births, and (5) genotype principal components that explained at least 75% of the phenotypic variance. The final analysis included 2,322 cases and 817 controls. 

The imputed genotype data were tested for association with UUI using logistic regression models. These tests were performed using the [RVTESTS](https://github.com/zhanxw/rvtests) software implemented in an open-source automated [GWAS workflow](https://github.com/RTIInternational/biocloud_gwas_workflows/tree/master/association_testing/rvtests) developed by RTI International.  

A gene analysis was then performed using [FUMA](https://fuma.ctglab.nl/) requires GRCh37 coordinates, so the GWAS summary statistics were then converted back to GRCh37 from GRCh38 [LiftOver](http://hgdownload.soe.ucsc.edu/admin/exe/linux.x86_64/liftOver).  


 
