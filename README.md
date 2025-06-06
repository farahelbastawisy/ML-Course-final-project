# Multiclass Kidney Disease Risk Prediction

This repository contains Farah El-Bastawisy’s Machine-Learning course **final project**, which builds and evaluates several supervised models to predict chronic kidney disease (CKD) risk levels from routine clinical and demographic data. A Streamlit web application is included so non-technical users can obtain real-time predictions.

---
## 1  Project Highlights
- **Dataset size:** 20 k+ patient records, 45 features (vitals, labs, comorbidities, lifestyle)
- **Pre-processing pipeline:** missing-value imputation, one-hot encoding, feature scaling, class balancing with SMOTE
- **Models trained (13):** Logistic Regression, KNN, Naïve Bayes, SVM (linear & RBF), Decision Tree, Random Forest, AdaBoost, Gradient Boosting, XGBoost, Bagging, Voting, Stacking
- **Best performer:** Random Forest → **94.19 % accuracy** on the held-out test set
- **Deployment:** Streamlit app (`app.py`) + pretrained pickled model and scaler (tracked via **Git LFS**)

---
## 2  Repository Structure
| Path | Purpose |
|------|---------|
| `Machine_learning_Project_Final (2).ipynb` | End-to-end notebook: EDA ➜ preprocessing ➜ training ➜ evaluation |
| `app (1).py` | Streamlit front-end for live CKD prediction |
| `kidney_model (1).pkl` | Trained Random Forest model (Git LFS) |
| `scaler (1).pkl` | StandardScaler fitted on training data (Git LFS) |
| `kidney_disease_dataset.csv` | Raw cleaned dataset |
| `Requirments.txt` | Exact Python dependencies |
| `.gitattributes` | Git LFS tracking rules |

---
## 3  Quick Start
```bash
# Clone with Git LFS support (required for .pkl files)
git clone https://github.com/farahelbastawisy/ML-Course-final-project.git
cd ML-Course-final-project
git lfs pull            # fetch large files

# Create virtual environment (optional but recommended)
python -m venv .venv
. .venv/Scripts/activate  # Windows

# Install dependencies
pip install -r Requirments.txt
```

### Run the Jupyter notebook
```bash
jupyter notebook "Machine_learning_Project_Final (2).ipynb"
```
Run the whole notbook to allow you to open streamlit app

### Launch the Streamlit app locally
```bash
streamlit run "app (1).py"
```
Open the URL provided in the terminal (default: `http://localhost:8501`) and enter patient data to obtain a CKD risk prediction.

---
## 4  Results Snapshot
| Model | Accuracy | AUC (ROC) | Notes |
|-------|----------|-----------|-------|
| Random Forest | **0.9419** | 0.973 | Highest overall performance |
| Voting Ensemble | 0.9232 | 0.959 | Combines 6 base learners |
| XGBoost | 0.8835 | 0.944 | Strong but slightly overfits |

Refer to the notebook for full confusion matrices, classification reports, ROC curves, and feature importance plots.

---
## 5  Reproducing the Study
1. Place additional data in `data/` (or edit the notebook path).
2. Adjust `SMOTE` or feature-selection settings in the preprocessing section.
3. Re-run model training cells or extend the grid-search block for deeper hyper-parameter tuning.

---
## 6  Contributing
Pull requests are welcome! Please open an issue first to discuss proposed changes or additional models.

---
## 7  Acknowledgements
- Dataset compiled from public CKD studies (see notebook for citations).
- Course supervision by **Dr Mohamed Elsayeh**.
- Guidance and inspiration from the open-source ML community.

---
## 8  License
This project is released under the MIT License — see `LICENSE` for details.

---
video drive 
https://drive.google.com/file/d/1f2S9_iYw4jDUqDLSkoGJdaJRvlWJxh60/view?usp=drive_link 
