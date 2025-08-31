# Early Prediction of Sepsis

**Competition:** [PhysioNet Challenge 2019](https://physionet.org/content/challenge-2019/1.0.0/)  
**Research Aim:** Develop a model to predict sepsis at an early stage, before clinical diagnosis.

---

## Challenges
- **Limited Raw Features:** Only 40 features are available in the dataset.  
- **High Missing Rates:** Most features have missing rates above 90%.  
- **Variable-Length Inputs:** The number of available records varies at each hour.  
- **Label Imbalance:** Only 7.26% of patients develop sepsis (1.8% of total records).  

---

## Contributions
- Address dataset imbalance and variable-length time series issues  
- Improve clinical outcome prediction  
- Enhance model interpretability  

---

## Methodology
**Pipeline:**  
`Input → Feature Engineering → Missing Value Imputation (LOOF) → Sampling (Down/Up) → Modeling (XGBoost)`

### Feature Engineering
- **Feature Selection:** Remove non-informative features (`Bilirubin_direct`, `TroponinI`, `Fibrinogen`)  
- **Missingness Indicators:** Add features reflecting missing data patterns  
- **Sliding-Window Statistics:** Compute mean, variance, and other time-windowed statistics  
- **Empirical Scores:** Incorporate clinical scores such as SOFA and ∆SOFA  
- **Textual Representation:** Convert `[column name] [value]` into embeddings using **BioClinicalBERT**  

---

## Evaluation
- **Evaluation Metric:** *[Specify metric used]*  
- **Evaluation Strategy:** *[Specify validation strategy]*  

---

## Addressing Key Challenges
- **High Missing Rate:** Missing-value imputation + missingness indicators  
- **Limited Features & Variable-Length Inputs:** Feature engineering and BioClinicalBERT representations  
- **Imbalanced Dataset:** Explore up-sampling, down-sampling, and weighted loss approaches  
