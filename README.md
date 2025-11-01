# 🫀 ECG Diagnostic Model using Logistic Regression

## Overview
This project implements a machine learning pipeline for **ECG arrhythmia classification** using a **Logistic Regression** model. The goal is to accurately diagnose 13 different cardiac conditions from ECG signals.  

The model leverages **feature extraction**, **PCA for dimensionality reduction**, **class weighting** to handle imbalanced data, and **category mapping** to group similar conditions.

### Cardiac Conditions
1. Atrial Arrhythmias
2. Ventricular Arrhythmias
3. Junctional Rhythyms
4. Sinus Rhythym Abnormalities
5. Conduction Blocks
6. Pre-excitation Syndromes
7. Ischemic Changes
8. Ventricular/Atrial Hypertrophy
9. Premature/Escape Beats
10. Axis/Rotation Abnormalities
11. Interval Abnormalities
12. Waveform Abnormalities
13. Miscellaneous

---

## Dataset
The model uses the **ECG Arrhythmia dataset** from [PhysioNet](https://physionet.org/content/ecg-arrhythmia/1.0.0/).  

- **Format:** ECG recordings in `.mat` files  
- **Number of samples:** 10,450 ECG recordings  
- **Classes:** 10 condition categories (0–9), derived from mapping 13 broader categories.

---

## Key Techniques

- **Feature Extraction:** Extracted key signal characteristics from ECG waveforms.
- **PCA (Principal Component Analysis):** Reduced high-dimensional features to improve model efficiency.
- **Class Weighting:** Handled imbalanced classes using optimal weights calculated with `compute_class_weight` from scikit-learn.

---

## Model
- **Algorithm:** Logistic Regression  
- **Multi-label handling:** `MultiOutputClassifier`  
- **Implementation:** Scikit-learn (`LogisticRegression`, `MultiOutputClassifier`)  
- **Hardware:** CPU

---

## Results

### Classification Report

| Class | Precision | Recall | F1-score | Support |
|-------|----------|-------|---------|--------|
| 0     | 0.58     | 0.97  | 0.73    | 2119   |
| 1     | 0.31     | 0.75  | 0.44    | 492    |
| 2     | 0.12     | 0.06  | 0.08    | 218    |
| 3     | 0.20     | 0.01  | 0.02    | 76     |
| 4     | 0.20     | 0.44  | 0.27    | 684    |
| 5     | 0.30     | 0.60  | 0.40    | 202    |
| 6     | 0.33     | 0.17  | 0.23    | 23     |
| 7     | 0.13     | 0.12  | 0.13    | 73     |
| 8     | 0.70     | 0.99  | 0.82    | 5122   |
| 9     | 0.27     | 0.85  | 0.41    | 1441   |

**Averages:**

| Metric       | Value |
|-------------|-------|
| Micro Avg    | Precision: 0.50, Recall: 0.88, F1: 0.63 |
| Macro Avg    | Precision: 0.32, Recall: 0.50, F1: 0.35 |
| Weighted Avg | Precision: 0.54, Recall: 0.88, F1: 0.66 |
| Samples Avg  | Precision: 0.61, Recall: 0.92, F1: 0.68 |

**Overall Accuracy:** 87.79%

---

## Future Improvements

- Explore advanced ML models like Random Forests or Gradient Boosting.
- Implement deep learning architectures for raw ECG signals.
- Apply data augmentation to improve performance on minority classes.
- Optimize hyperparameters and PCA components for higher accuracy.

---

## License

This project is released under the MIT License.

---

## References

Zheng, J., Guo, H., & Chu, H. (2022). A large scale 12-lead electrocardiogram database for arrhythmia study (Version 1.0.0). PhysioNet. RRID:SCR_007345. https://doi.org/10.13026/wgex-er52

Zheng, J., Chu, H., Struppa, D., Zhang, J., Yacoub, S. M., El-Askary, H., Chang, A., Ehwerhemuepha, L., Abudayyeh, I., Barrett, A. S., Fu, G., Yao, H., Li, D., Guo, H., & Rakovski, C. (2020). Optimal multi-stage arrhythmia classification approach. Scientific Reports, 10, 1–12.

Goldberger, A., Amaral, L., Glass, L., Hausdorff, J., Ivanov, P. C., Mark, R., Mietus, J. E., Moody, G. B., Peng, C.-K., & Stanley, H. E. (2000). PhysioBank, PhysioToolkit, and PhysioNet: Components of a new research resource for complex physiologic signals. Circulation, 101(23), e215–e220. RRID:SCR_007345.

---

## Author

Ryan Spencer
