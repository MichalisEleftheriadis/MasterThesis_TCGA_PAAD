# MasterThesis_TCGA_PAAD
Master Thesis - euc.ac.cy

# Construction of a cuproptosis-related lncRNA predictive signature for pancreatic cancer patients

## Description
Cuproptosis is a new form of cell death in various tumours [1]. However, the mechanism of cuproptosis in pancreatic cancer has not been well studied. Long noncoding RNAs (lncRNAs) are RNAs with lengths of over 200 nucleotides that generally do not encode proteins [2]. 

Ten cuproptosis-related lncRNAs were recently found to effectively assess the prognosis and molecular profile of clear cell renal cell carcinoma patients [3]. However, the mechanism of the copper-mediated death process in pancreatic cancer remains unclear, and there has been no study of cuproptosis-associated lncRNAs in pancreatic cancer. In this study we will aim to explore the functions of lncRNAs related to cuproptosis in pancreatic cancer and develop a prognostic predictive model. 

RNA sequencing and clinicopathological data will be derived from The Cancer Genome Atlas (TCGA-PAAD) and randomly divided into training and validation groups. 
We will focus on 19 cuproptosis-related genes (CRGs) from a previously published article [4]: NFE2L2, NLRP3, ATP7B, ATP7A, SLC31A1, FDX1, LIAS, LIPT1, LIPT2, DLD, DLAT, PDHA1, PDHB, MTF1, GLS, CDKN2A, DBT, GCSH, and DLST) After downloading the original files, the numbers of mutations and mutation sites of each gene in each sample will be extracted and used to construct a mutation matrix file.

## Construction of a cuproptosis‑associated lncRNA predictive signature
We will randomly divide PAAD patients into a training set and a validation set and perform univariate Cox regression analysis on the training set to screen cuproptosis-related lncRNAs associated with overall survival (OS), with P < 0.05 as the criterion.

To avoid model overfitting, LASSO (least absolute shrinkage and selection operator) regression analysis will be conducted using the R package “glmnet” to further screen out lncRNAs closely related to cuproptosis genes in PAAD. Multivariate Cox regression analysis will be conducted on the screened lncRNAs. The cuproptosis-related lncRNAs that we will identify will be used to construct a prognostic signature for PAAD patients.

Using the risk score calculated with the newly constructed signature, the patients in the training set and validation set will be divided into high-risk and low-risk groups based on the median risk score. To compare the OS of PAAD patients in the high- and low-risk groups, we will perform Kaplan–Meier survival analysis using the R packages “survival” and “survminer”. The “timeROC” R package will be used to evaluate the accuracy of the novel cuproptosis-related lncRNA signature for predicting the OS of PAAD patients, and the validation set will be used to confirm the predictive performance of the novel signature.

To assess the applicability of the cuproptosis-related lncRNA predictive signature, we will divide the patients into different groups according to patient age and tumour stage and analysed the performance of the model for predicting BC progression in subgroups with different clinical characteristics by Kaplan–Meier survival analysis
