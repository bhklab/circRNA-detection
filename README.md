## Detection of non-coding RNAs and assessment of their predictive value for mono therapies

Julia Nguyen<sup>1,\$</sup>, Anthony Mammoliti<sup>1,2,\$</sup>, Sisira Kadambat Nair<sup>1</sup>, Emily So<sup>1,2</sup>, Farnoosh Abbas Aghababazadeh<sup>1</sup>, Christoper Eeles<sup>1</sup>, Ian Smith<sup>1,2</sup>, Petr Smirnov<sup>1,2</sup>, Housheng Hansen He<sup>1,2</sup>, Ming-Sound Tsao<sup>1,2</sup>, Benjamin Haibe-Kains<sup>1,2,3,4,5,6,#</sup>


<sup>1</sup>Princess Margaret Cancer Centre, University Health Network, Toronto, Ontario, Canada\
<sup>2</sup>Department of Medical Biophysics, University of Toronto, Toronto, Ontario, Canada\
<sup>3</sup>Department of Computer Science, University of Toronto, Toronto, Ontario, Canada\
<sup>4</sup>Ontario Institute of Cancer Research, Toronto, Ontario, Canada\
<sup>5</sup>Vector Institute for Artificial Intelligence, Toronto, ON M5G 1L7, Canada\
<sup>6</sup>Biostatistics Division, Dalla Lana School of Public Health, Toronto, ON M5T 3M7, Canada
 

<sup>$</sup> These authors contributed equally to the present work\
<sup>#</sup> Corresponding author: Benjamin Haibe-Kains, Princess Margaret Cancer Centre, University Health Network, Toronto, Ontario M5G 2C4 Canada


<br>

### **Transcript Quantification**

<ins> *Description:*</ins> circRNA, mRNA, and corresponding gene expression was quantified across 48 cell line biological replicates from three pharmacogenomic datasets (gCSI, CCLE, GDSC2) with poly(A)-selected RNA-seq data. Consistency of transcript quantification was compared using UMAP. Transcript stability was assessed across the dataset pairs.

<br>

**1.** Reproducible Snakemake pipelines for running CIRI2 and CIRCexplorer2 on cell line biological replicates and lung cancer patient data can be found under: "/data/snakemake_pipelines"

**2.** Transcript expression quantification (run script: "/code/transcript_quantification.R")

**3.** Dimensionality reduction analysis of transcript quantification (run script: "/code/umap.R")

**4.** Computation of stability indices of transcripts across dataset pairs (run script: "/code/si_distribution.R")


<br />

### **circRNA**

<ins> *Description:*</ins> CIRI2 and CIRCexplorer2 was ran on 48 cell line biological replicates (gCSI, CCLE, GDSC2) with poly-A selected RNA-seq data and lung cancer patient data with both poly-A + Ribo-depleted RNA-seq data. circRNA detection levels were compared between cell line and patient data. A survival analysis (Overall Survival) was performed using the Ribo-depleted lung patient data due to yielding high circRNA expression, in comparison to the cell lines.

<br>

**1.** Cell line biological replicate analysis - data under "/data/processed_cellline" (run script: "/code/circRNA_celllines.R")

**2.** Lung adenocarcinoma patient analysis - data under "/data/processed_lung" (run script "/code/circRNA_lung.R")

**3.** Quantification of unique circRNA transcripts and distribution across RNA-seq selection protocols (run script "/code/unique_lung_transcripts.R")

**4.** Survival analysis on lung adenocarcinoma patient data (run script: "/code/survival_lung.R")


<br />

### **mRNA**

<ins> *Description:*</ins> Features that may predict mRNA stability were processed, and influence was computed through supervised learning.  The association between mRNA stability and drug response was investigated.

<br>

**1.** Generation of data.frame with transcript stability indices and genomic feature data - data under - "/data/transcript_stability" (run script: "/code/transcript_stability.R")

**2.** Identification of quantile usage for stable/unstable transcripts using Kuncheva Index (run script: "/code/overlap.R)

**3.** Feature influence after permuting each feature (n=20,000) (run script: "/code/feature_influence.R")

**4.** Assessing association between stability and predictive value for *known* gene biomarkers (run script: "/code/biomarker_forest.R")

**5.** Assessing association between stability and predictive value for across *all* genes (run script: "/code/hist_pred_value.R")




