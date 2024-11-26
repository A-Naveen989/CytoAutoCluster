# CytoAutoCluster

This repository contains Python code to prepare the benchmark data set Levine_32dim, which can be used to test clustering algorithms.

The dataset comprises 32-dimensional mass cytometry data, including protein levels for 265,627 cells, 32 protein markers, and 14 manually gated cell populations from 2 individuals. Cluster labels exist for 39% (104,184) of the cells. Please take a look at the information below for additional details. The repository benchmark-data-Levine-13-dim contains Python code to prepare a second benchmark data set with lower dimensionality (13 dimensions).

**The data set is sourced from the following paper:-**

Levine et al. (2015). Data-Driven Phenotypic Dissection of AML Reveals Progenitor-like Cells that Correlate with Prognosis. Cell, 162, pp. 184-197. http://www.sciencedirect.com/science/article/pii/S0092867415006376

**Raw data can be accessed through Cytobank:-**

32-dimensional benchmark data set: https://www.cytobank.org/cytobank/experiments/46102
If you use these data sets, please look at the paper by Levine et al. (2015).

**Mass Cytometry**

Mass cytometry, also known as CyTOF, is a recent technology for analyzing single cells in bulk. It is like flow cytometry, but it can measure more characteristics per cell.

Just like in flow cytometry, datasets include the levels of protein markers for every cell. Mass cytometry machines can analyze hundreds of cells every second, measuring approximately 40 protein expression levels per cell. An average data set consists of hundreds of thousands of cells in each sample.

Protein levels can help identify cell types, called populations, and their functional states. Mass cytometry frequently includes examining groups of cells, such as identifying specific cell groups such as established disease indicators, identifying cell groups in particular functional conditions, or comparing percentages of groups among samples.

The traditional method for analyzing flow cytometry data involves "gating", which entails visually seeking out clusters or areas of high density in a sequence of two-dimensional scatter plots. While this is effective for flow cytometry data with few dimensions, it becomes less dependable and challenging to manage with more dimensions. Various research teams have recently created algorithms for automatically identifying cell populations to tackle this issue.

**Paper by Levine and colleagues in 2015**

Levine et al. (2015) (reference and link above) presented PhenoGraph, a novel algorithm based on graphs identifying clusters in complex mass cytometry data. They applied it to analyze the diversity of cells in AML patients.

Levine et al. utilized two standard datasets of normal human bone marrow cells in their study to showcase the effectiveness of PhenoGraph. The evaluations confirmed that PhenoGraph successfully identified various immune cell populations in healthy human bone marrow cells.
Figures 2A-B, S2A-C, and Data S1A-F utilize data sets, while in the study, Figures S2D and Data S1G-I involve different data sets. 

The data sets provided by the authors are now accessible to the public, and we have discovered them to be highly beneficial for evaluating clustering algorithms in high-dimensional spaces. 

Data set with 32 dimensions as a standard for comparison 

This data set comprises protein expression levels from healthy human bone marrow mononuclear cells (BMMCs) of two healthy individuals, measured in 32 dimensions using mass cytometry (CyTOF). (The data set referenced as "benchmark data set 2" in the study by Levine et al. 2015.) 

The data set consists of 265,627 cells and includes 32 surface marker proteins with a dimensionality of p = 32. Cluster labels for 14 central immune cell populations have been manually assigned to 39% (104,184) of the cells, while the remaining 61% (161,443) are designated as "unassigned". The cells belong to two individuals named H1 and H2. Populations were assigned 72,463 cells for individual H1, while 118,888 cells remained unassigned, totalling 191,351. Populations were assigned 31,721 cells for individual H2, with 42,555 remaining unassigned (74,276 cells). 

Manual gating utilized 19 out of the 32 surface markers. The following 19 items are: CD3, CD4, CD7, CD8, CD15, CD16, CD19, CD20, CD34, CD38, CD41, CD44, CD45, CD61, CD64, CD123, CD11c, CD235a/b, and HLA-DR. Levine et al. (2015) utilized all 32 surface markers to identify cell populations using PhenoGraph automatically. FoPleaseefer to Levine et al. (2015), Supplemental Experimental Procedures. 
 for more information
**Intention**

We have developed Python code to prepare and export these benchmark datasets in standard formats, simplifying access for researchers in different fields to evaluate clustering algorithms. The R code in this repository is for the 32-dimensional benchmark data set, while the companion repository benchmark-data-Levine-13-dim has code for the 13-dimensional benchmark data set.
The data files that Levine et al. (2015) shared on Cytobank are in FCS format, with a single FCS file for each manually gated cell population (cluster). The FCS, an efficient binary file format, is most commonly used in the flow cytometry community. Nevertheless, it necessitates unique software tools for entry, which means it is not easily reachable for researchers in different fields.

Moreover, applying an arcsinh transformation before conducting gating or automated analysis is standard practice. This behaves like a log transform at high values but resembles a linear transform for small values; this is necessary because CyTOF data contains numerous small and negative values. The arcsinh transform typically uses a scale factor of 5 for CyTOF data and 150 for flow cytometry data, as Bendall et al. 2011, Supplementary Figure S2 suggested. Other transforms, such as logical or biexponential, are commonly utilized for flow cytometry data.

## Overview
This Python script is a comprehensive tool for analyzing data and predicting outcomes based on input datasets. It is designed to streamline data preparation, visualization, and modelling processes.

## Steps Performed
1. Reads input data from a CSV file.
2. Cleans the data by handling missing values and outliers.
3. Conducts exploratory data analysis (EDA), including:
   - Generating summary statistics.
   - Creating plots such as histograms, scatter plots, and correlation matrices.
4. Prepares the data for modelling by:
   - Encoding categorical variables.
   - Splitting the data into training and test sets.
5. Trains a machine learning model (e.g., Random Forest, Linear Regression).
6. Evaluate model performance using accuracy, RMSE, or R² metrics.
7. Saves the trained model and outputs predictions to a file.

## How to Run
1. Install dependencies:
   ```bash
   pip install -r requirements.txt
Requirements
Python 3.8 or higher
Libraries: pandas, numpy, matplotlib, sci-kit-learnable

This structure ensures that anyone viewing your repository can quickly understand the script's purpose and how to use it. 
