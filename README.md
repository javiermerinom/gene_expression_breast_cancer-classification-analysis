# Gene Expression Analysis for Breast Cancer Classification and Survival Analysis

## 🏗️ Project Context
This was a research project developed as teamwork for the third term of the Post-Degree Diploma in Data Analytics in Langara College.

## 📌 Project Overview  

This repository contains the implementation of a breast cancer classification and survival analysis pipeline using TCGA-BRCA RNA-seq data. The project explores gene expression patterns, applies differential expression analysis (DEA), performs dimensionality reduction, and benchmarks multiple machine learning models across classification tasks (Normal vs. Tumor, Early vs. Late stage, multi-stage classification, and survival prediction).  

⚠️ Please note: this repository does **not** include the cloud deployment and dashboard components described in the report.  

---

## 🎯 Objective  

The main objectives of this project are:  
- To examine differences in gene expression across breast cancer stages.  
- To identify key biomarkers for early detection and prognosis.  
- To classify tumor vs. normal samples and cancer stages using supervised and unsupervised learning techniques.  
- To predict patient survival using Random Survival Forest models.  

---

## 🛠 Tools & Technologies  

- **Languages & Libraries:** Python, scikit-learn, XGBoost, RandomForest, Logistic Regression, SHAP  
- **Feature Selection & Dimensionality Reduction:** DESeq2 (R), PCA, LDA, NCA, PCoA  
- **Visualization:** Matplotlib, Seaborn, 3D plots for PCA/LDA/PCoA  
- **Data Source:** TCGA-BRCA mRNA-seq dataset (The Cancer Genome Atlas)  
- **Survival Modeling:** Random Survival Forest  

---

## 📊 Key Steps  

1. **Data Preparation & Normalization**  
   - Integration of RNA-seq counts and clinical metadata.  
   - Variance Stabilizing Transformation (VST) / log2 normalization.  

2. **Exploratory Data Analysis (EDA)**  
   - Patient demographics, stage distribution, and survival trends.  
   - Visualization of gene expression distributions and outliers.  

3. **Differential Expression Analysis (DEA)**  
   - DEG detection using DESeq2.  
   - Visualization: volcano plots, heatmaps, and clustering.  

4. **Dimensionality Reduction**  
   - PCA, PCoA (unsupervised).  
   - LDA, NCA (supervised).  

5. **Model Building & Evaluation**  
   - Benchmarked classifiers: Random Forest, XGBoost, Logistic Regression.  
   - Classification tasks:  
     - Normal vs. Tumor  
     - Early vs. Late stage  
     - Multi-stage (I–IV) classification  
   - GridSearchCV for hyperparameter tuning.  

6. **Survival Analysis**  
   - Random Survival Forest applied to DEG-filtered gene sets.  
   - Evaluation using C-index and survival curve predictions.  

---

## 🚀 Results  

- DEG filtering significantly improved classification performance compared to full gene sets.  
- XGBoost consistently outperformed other models across classification tasks .  
- Supervised dimensionality reduction (LDA, NCA) yielded better separation of classes than unsupervised methods .  
- Survival analysis achieved moderate predictive performance (C-index ≈ 0.57) , with survival curves generated for exploratory use.  

**Model Benchmarking Summary**

| Task                          | Best Model                  | Accuracy | AUC / C-index | Recall (Positive) | Key Insight |
|-------------------------------|-----------------------------|----------|---------------|-------------------|-------------|
| Normal vs. Tumor              | NCA + XGBoost (DEG-filtered) | **99%**  | High AUC ROC / AUPRC  | Strong across all metrics | Robust separation of tumor vs. normal samples |
| Early vs. Late Stage          | PCA + Random Forest (DEG-filtered) | 71%   | Balanced AUC | **0.58 recall** (Late stage) | Prioritized recall to avoid missing Late-stage cases |
| Stage I–IV Classification     | LDA + XGBoost (DEG-filtered) | Lower (~50–60%)  | Weak AUC | Low recall | Struggled to distinguish intermediate stages; needs additional clinical features |
| Survival Prediction           | Random Survival Forest (RSF) | —        | **C-index 0.571**  | — | Modest discriminative ability; survival curves provided for exploratory use |

---

## 📂 Repository Structure  

```bash
├── Data/                 # TXT check for information
├── Src/            # Jupyter notebooks for EDA, DEA, modeling, and survival analysis. R file for download data set.  
├── Documentation/              # Final project report and presentation
├── Output/              # Gene information
├── README.md             # Project overview (this file)

---

## 🙌 Acknowledgments  
Developed by:  
- Javier Merino  
- Meyliani Sanjaya  
- Angeli De los Reyes  
- Nay Zaw Lin  
