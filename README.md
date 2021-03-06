# annotation-pipeline

This pipeline annotates a txt input file containing min 5 columns (`"Chr\tStart\tEnd\tRef\tAlt"`) with the annotations below.

## How to run .
`perl annotation-pipeline.pl -infile <NameOfYourFile>`

#### [ANNOVAR]
[ANNOVAR]: http://annovar.openbioinformatics.org/en/latest/
- **Func.refGene**:	Tells whether the variant hit exons or hit intergenic regions, or hit introns, or hit a non-coding RNA genes.
- **Gene.refGene**:	If the variant is exonic/intronic/ncRNA, this column gives the gene name (if multiple genes are hit, comma will be added between gene names); if not, the column will give the two neighboring genes and the distance to these neighboring genes.
- **GeneDetail.refGene**: 
- **ExonicFunc.refGene**:	Tells the functional consequences of the variant (possible values in this fields include: nonsynonymous SNV, synonymous SNV, frameshift insertion, frameshift deletion, nonframeshift insertion, nonframeshift deletion, frameshift block substitution, nonframshift block substitution)
- **AAChange.refGene**:	Gene name, the transcript identifier and the sequence change in the corresponding transcript. 
- **cytoBand**: Cytogenic band.
- **snp138**:	dbsnp138 annotation. if present then rs id will be present else -1

#### [Frequencies from 1000 genome new release]
[Frequencies from 1000 genome new release]: http://www.1000genomes.org/category/frequently-asked-questions/population
- **1000g2014oct_all**: All Individuals from the October 2014 release
- **1000g2014oct_eur**: European Individuals from the October 2014 release
- **1000g2014oct_afr**: African Individuals from the October 2014 release
- **1000g2014oct_amr**: Ad Mixed American Individuals from the October 2014 release
- **1000g2014oct_eas**: East Asian Individuals from the October 2014 release
- **1000g2014oct_sas**: South Asian Individuals from the October 2014 release

#### [NHLBI]
[NHLBI]: http://evs.gs.washington.edu/EVS/
- **esp6500_all**:	All 6503 Individuals
- **esp6500_ea**:	European American
- **esp6500_aa**:	African American

#### [ExAC] Exome Aggregation Consortium Data. v0.3 nonTCGA data
[ExAC]: http://exac.broadinstitute.org/
- **ExAC_ALL_nonTCGA**: Excluding TCGA cohorts (53,105 samples)
- **ExAC_AFR_nonTCGA**:
- **ExAC_AMR_nonTCGA**:
- **ExAC_EAS_nonTCGA**:
- **ExAC_FIN_nonTCGA**:
- **ExAC_NFE_nonTCGA**:
- **ExAC_OTH_nonTCGA**:
- **ExAC_SAS_nonTCGA**:

#### [cg69] Frequency in 69 samples sequenced at Complete Genomics  
[cg69]: http://www.completegenomics.com/public-data/69-genomes/	
####[nci60] Frequency in 60 Cell lines sequenced at NCI  
[nci60]: http://discover.nci.nih.gov/cellminer/home.do
####[ExAC] Exome Aggregation Consortium Data. v0.3
[ExAC]: http://exac.broadinstitute.org/ 
- **ExAC_ALL**: All Individuals (60,706 samples)
- **ExAC_AFR**: African 
- **ExAC_AMR**: American
- **ExAC_EAS**: Eastern Asian
- **ExAC_FIN**: Finnish
- **ExAC_NFE**: Non-Finnish Europian
- **ExAC_OTH**: Other
- **ExAC_SAS**: South Asian

#### [ClinSeq]
[ClinSeq]: http://www.genome.gov/20519355
- **Clinseqc_genotypes**:	The number of genotypes with MPG score >=10.
- **Clinseqc_homref**:	Number of genotypes where all alleles seen are the reference allele (I.e., if haploid, one reference allele, and if diploid, two reference alleles).
- **Clinseqc_het**:	Number of diploid genotypes for which one allele is the reference allele, and the other is the variant allele .
- **Clinseqc_homvar**:	Number of genotypes where all alleles seen are the variant allele (I.e., if haploid, one copy of the variant allele, and if diploid, two copies of the variant allele).
- **Clinseqc_hetnonref**:	Number of diploid genotypes for which one allele is the variant allele, and the other is a third allele that is not the reference and not the variant allele.
- **Clinseqc_other**:	Any genotype that cannot be categorized into one of the above categories, including haploid third alleles (which are non-reference and not the variant allele), diploid homozygous third alleles and diploid heterozygous genotypes which do not contain the variant allele.
- **Clinseqc_refallele**:	Number of reference alleles observed in genotypes with MPG score >=10. Haploid homref and diploid het genotypes will contribute one copy, while diploid homref genotypes will contribute two to this count.
- **Clinseqc_varallele**:	Number of variant alleles observed in genotypes with MPG score >=10. Haploid homnonref and diploid het and hetnonref genotypes will contribute one copy, while diploid homnonref genotypes contribute two to this count.
- **Clinseqfreq_homref**:	Frequency of homozygous reference genotypes.
- **Clinseqfreq_het**:	Frequency of heterozygous genotypes where the reference is one of the alleles.
- **Clinseqfreq_homvar**:       Frequency of homozygous non-reference genotypes.
- **Clinseqfreq_hetnonref**:    Frequency of heterozygous genotypes where the reference is not one of the alleles.
- **Clinseqfreq_refallele**:    Frequency of the reference allele.
- **Clinseqfreq_varallele**:    Frequency of the variant allele.
- **Clinseqref_is_minor**:      Flag 1 if the reference is the minor allele.
- **Clinseqc_major**:	The number of major alleles, which can be either the reference or the variant allele.
- **Clinseqc_minor**:	The number of minor alleles, which can be either the reference or the variant allele.
- **Clinseqmaf**:	The frequency of the minor allele compared to the sum of all alleles.
- **Clinseqchisquare**:	The chi-square value (NOT p-value) calculated using the genotypes AA, Aa, aa where A is the major allele and a is the minor allele (major and minor can only be reference or variant)

#### [CADD]
[CADD]: http://cadd.gs.washington.edu/
- **CADD**:  Combined Annotation Dependent Depletion (CADD) Score
- **CADD_Phred**:  Combined Annotation Dependent Depletion (CADD) Score

#### [SIFT]
[SIFT]: http://sift.jcvi.org/
- **SIFT Prediction**:  
	Prediction from SIFT (DAMAGING, TOLERATED, Not scored, Damaging due to stop, N/A, DAMAGING *Warning! Low confidence.)
- **SIFT Score**:  
	0 = DAMAGING,  
	1 = TOLERATED,  
	N/A = Damaging due to stop, Not scored, N/A  

#### [PolyPhen-2]
[PolyPhen-2]: http://genetics.bwh.harvard.edu/pph2/
- **PPH2 Prediction**:(benign, possibly damaging, probably damaging)
- **PPH2 Class**: (neutral, deleterious)
- **PPH2 Probability**: (neutral, deleterious)

#### [clinvar_20150330]
[clinvar_20150330]: http://www.ncbi.nlm.nih.gov/clinvar/

#### [cosmic70]
[cosmic70]: http://cancer.sanger.ac.uk/cancergenome/projects/cosmic/

#### [HGMD]
[HGMD]: https://portal.biobase-international.com/hgmd/pro/global.php#other
NIH Users can create account and access the database [here]. Enter the code 1881-6975-97565225 in the license field during the account registration process.
[here]: https://portal.biobase-international.com/cgi-bin/portal/login.cgi
- **hgmd_Acc-No**: hgmd Acc Number
- **hgmd_Category**: Category as defined by hgmd.
- **hgmd_GeneName**: Gene Name
- **hgmd_Phenotype**: Associated Disease

#### [MATCH] Trial  
[MATCH]: http://www.cancer.gov/about-cancer/treatment/clinical-trials/nci-supported/nci-match
- **MATCH_ArmID**: Name of the MATCH Trial Treatment Arm.  
Details are available [here]
[here]: https://matchbox.nci.nih.gov/matchbox/views/treatmentArmsDetails.html?treatmentArmId=EAY131-A&treatmentArmsList=true
  

#### [DoCM] Database of Curated Mutations  
[DoCM]: http://docm.genome.wustl.edu/
- **DoCM Disease**: Name of the cancer type
- **DoCM PMID**: PubMed ID

#### [canDL] Cancer Driver Log  
[canDL]: https://candl.osu.edu/browse
- **CanDL_Diagnosis** Diagnosis as listed on the server  
- **CanDL_Level_of_Evidence** Level of evidence.     
	Tier 1: Alteration has matching FDA approved or NCCN recommended therapy    
	Tier 2: Alteration has matching therapy based on evidence from clinical trials, case reports, or exceptional responders.  
 	Tier 3: Alteration predicts for response or resistance to therapy based on evidence from pre-clinical data (in vitro or in vivo models)  
 	Tier 4: Alteration is a putative oncogenic driver based on functional activation of a pathway  
- **CanDL_PMIDs** PubMed ID

#### [TCC] Targated Cancer Care  
[tcc]: https://targetedcancercare.massgeneral.org/
- **targated_cancer_care.Gene** Gene Name
- **targated_cancer_care.AA** Amino Acid Change


#### [My Cancer Genome]   
[My Cancer Genome]: http://www.mycancergenome.org/
- **MyCG_Gene**: Name of the gene
- **MyCG_Codon**: Codon change in database
- **MyCG_cDNA Change**: cDNA change in database
- **MyCG_Link(s)**: Link to the page data is extracted from  
- This update does not contain the name of diagnosis as annotation but it contains the link to the website which can give much more detail information about the mutation  
- Because the genomic changes are based on backlocation; the cDNA change in database and the mutation in question may not be same.  

#### [CIViC] Clinical Interpretation of Variants in Cancer  
[CIViC]: https://civic.genome.wustl.edu/#/home
- **civic_PMID**: PubMed ID  
- **civic_Rating**:   
- **civic_EvidenceLevel**:  
- **civic_Diagnosis**:  

#### ICGC, TCGA and Pediatric NextGen Studies. 

[** Pediatric Studies Log **](https://docs.google.com/spreadsheets/d/1BHg-I0tLbz6OGHxy4FIb4M0GSHZV4FuEamVX0AT71yE/edit#gid=0)  

[**ICGC_09202015**](https://dcc.icgc.org/projects)  
[**TCGA_07142015**](http://www.cbioportal.org/)  
[**ALL_22237106**](http://www.ncbi.nlm.nih.gov/pubmed/22237106)  
[**ALL_22897843**](http://www.ncbi.nlm.nih.gov/pubmed/22897843)  
[**ALL_22897847**](http://www.ncbi.nlm.nih.gov/pubmed/22897847)  
[**ALL_23212523**](http://www.ncbi.nlm.nih.gov/pubmed/23212523)  
[**ALL_23334668**](http://www.ncbi.nlm.nih.gov/pubmed/23334668)  
[**AML_23153540**](http://www.ncbi.nlm.nih.gov/pubmed/23153540)  
[**DIPG_22661320**](http://www.ncbi.nlm.nih.gov/pubmed/22661320)  
[**EPEN_24553141**](http://www.ncbi.nlm.nih.gov/pubmed/24553141)  
[**EPEN_24553142**](http://www.ncbi.nlm.nih.gov/pubmed/24553142)  
[**ETMR_24316981**](http://www.ncbi.nlm.nih.gov/pubmed/24316981)  
[**EWS_25010205**](http://www.ncbi.nlm.nih.gov/pubmed/25010205)  
[**EWS_25186949**](http://www.ncbi.nlm.nih.gov/pubmed/25186949)  
[**EWS_25223734**](http://www.ncbi.nlm.nih.gov/pubmed/25223734)  
[**GBM_18772396**](http://www.ncbi.nlm.nih.gov/pubmed/18772396)  
[**GBM_23079654**](http://www.ncbi.nlm.nih.gov/pubmed/23079654)  
[**HEP_23887712**](http://www.ncbi.nlm.nih.gov/pubmed/23887712)  
[**HGG_20068183**](http://www.ncbi.nlm.nih.gov/pubmed/20068183)  
[**HGG_22286061**](http://www.ncbi.nlm.nih.gov/pubmed/22286061)  
[**HGG_22286216**](http://www.ncbi.nlm.nih.gov/pubmed/22286216)  
[**HGG_23417712**](http://www.ncbi.nlm.nih.gov/pubmed/23417712)  
[**HGG_24705250**](http://www.ncbi.nlm.nih.gov/pubmed/24705250)  
[**HGG_24705251**](http://www.ncbi.nlm.nih.gov/pubmed/24705251)  
[**LGG_23104868**](http://www.ncbi.nlm.nih.gov/pubmed/23104868)  
[**LGG_23222849**](http://www.ncbi.nlm.nih.gov/pubmed/23222849)  
[**LGG_23583981**](http://www.ncbi.nlm.nih.gov/pubmed/23583981)  
[**MED_21163964**](http://www.ncbi.nlm.nih.gov/pubmed/21163964)  
[**MED_22265402**](http://www.ncbi.nlm.nih.gov/pubmed/22265402)  
[**MED_22722829**](http://www.ncbi.nlm.nih.gov/pubmed/22722829)  
[**MED_22722829_G**](http://www.ncbi.nlm.nih.gov/pubmed/22722829)  
[**MED_22832583**](http://www.ncbi.nlm.nih.gov/pubmed/22832583)  
[**MIX_24055113**](http://www.ncbi.nlm.nih.gov/pubmed/24055113)  
[**MIX_24710217**](http://www.ncbi.nlm.nih.gov/pubmed/24710217)  
[**MRT_22797305**](http://www.ncbi.nlm.nih.gov/pubmed/22797305)  
[**NBL_22142829**](http://www.ncbi.nlm.nih.gov/pubmed/22142829)  
[**NBL_22367537**](http://www.ncbi.nlm.nih.gov/pubmed/22367537)  
[**NBL_22416102**](http://www.ncbi.nlm.nih.gov/pubmed/22416102)  
[**NBL_23202128**](http://www.ncbi.nlm.nih.gov/pubmed/23202128)  
[**NBL_23334666**](http://www.ncbi.nlm.nih.gov/pubmed/23334666)  
[**NBL_24147068**](http://www.ncbi.nlm.nih.gov/pubmed/24147068)  
[**NBL_25517749**](http://www.ncbi.nlm.nih.gov/pubmed/25517749)  
[**NBL_26121087**](http://www.ncbi.nlm.nih.gov/pubmed/26121087)  
[**NEO_22187960**](http://www.ncbi.nlm.nih.gov/pubmed/22187960)  
[**OST_24703847**](http://www.ncbi.nlm.nih.gov/pubmed/24703847)  
[**OST_25512523**](http://www.ncbi.nlm.nih.gov/pubmed/25512523)  
[**RB_22237022**](http://www.ncbi.nlm.nih.gov/pubmed/22237022)  
[**RB_24688104_G**](http://www.ncbi.nlm.nih.gov/pubmed/24688104)  
[**RMS_22142829**](http://www.ncbi.nlm.nih.gov/pubmed/22142829)  
[**RMS_24272621**](http://www.ncbi.nlm.nih.gov/pubmed/24272621)  
[**RMS_24332040**](http://www.ncbi.nlm.nih.gov/pubmed/24332040)  
[**RMS_24436047**](http://www.ncbi.nlm.nih.gov/pubmed/24436047)  
[**RMS_24436047_T**](http://www.ncbi.nlm.nih.gov/pubmed/24436047)  
[**RMS_24793135**](http://www.ncbi.nlm.nih.gov/pubmed/24793135)  
[**RMS_24824843**](http://www.ncbi.nlm.nih.gov/pubmed/24824843)  
[**RMS_26138366**](http://www.ncbi.nlm.nih.gov/pubmed/26138366)  
[**SAR_20601955**](http://www.ncbi.nlm.nih.gov/pubmed/20601955)  
[**UVM_TCGA**](https://tcga-data.nci.nih.gov/tcga/tcgaCancerDetails.jsp?diseaseType=UVM&diseaseName=Uveal%20Melanoma)  
[**WT_24909261**](http://www.ncbi.nlm.nih.gov/pubmed/24909261)  
[**WT_25190313**](http://www.ncbi.nlm.nih.gov/pubmed/25190313)  
[**WT_25313908**](http://www.ncbi.nlm.nih.gov/pubmed/25313908)  
[**WT_25670082**](http://www.ncbi.nlm.nih.gov/pubmed/25670082)  
And data downloaded from [FoundationMedicine](https://pediatric-data.foundationmedicine.com/)

#### 57 [ACMG] genes and the pertinent information.
[ACMG]:https://www.acmg.net/docs/ACMG_Releases_Highly-Anticipated_Recommendations_on_Incidental_Findings_in_Clinical_Exome_and_Genome_Sequencing.pdf
- **Gene.refGene**
- **ACMG_Disease**
- **ACMG_Age-to-Report**
- **ACMG_Gene-Reviews-PubMedID**
- **ACMG_Inheritance**
- **ACMG_Known-vs-Expected**
- **ACMG_LSDB**


