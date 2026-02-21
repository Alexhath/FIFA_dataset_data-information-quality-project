# ⚽ FIFA Dataset - Data & Information Quality Project 

🏆 **Final Grade: 4/4 (Maximum Score)**

This repository contains the project developed for the **Data and Information Quality** course (A.Y. 2025/2026) at **Politecnico di Milano**.

## 📖 Project Description
The goal of this project is to design and implement a comprehensive **Data Preparation and Analysis pipeline**. We started with a "dirty" dataset containing the attributes of approximately 19,000 football players from **FIFA**, which is widely recognized as the world's leading and most iconic football video game series.

The project demonstrates how data quality affects machine learning outcomes by comparing results between the original "messy" data and our final "cleaned" version.

## 👥 Authors
* **Mattia Brianti**
* **Alex Hathaway**

---

## 🛠️ The Pipeline

### 1. Data Preparation (The "Cleaning" Phase)
We transformed the raw dataset through several rigorous steps to ensure high information quality:
* 📊 **Data Profiling**: Initial assessment of data distributions and types using `ydata-profiling`.
* 🔄 **Standardization**: 
    * Expanded over 20 abbreviated columns (e.g., `OVA` → `Overall`, `POT` → `Potential`) for clarity.
    * Converted star-ratings (★) and currency strings (e.g., €100M) into numerical formats.
    * Fixed inconsistent date formats and handled player contract/loan status.
* 🔍 **Error Detection & Correction**:
    * **Outliers**: Identified and managed anomalous values using the **Local Outlier Factor (LOF)** algorithm.
    * **Missing Values**: Handled null values using context-aware imputation.
* 👯 **Data Deduplication**: Performed **Record Linkage** to identify potential duplicates, using Jaro-Winkler distance for names and club similarity.

### 2. Data Analysis (The "Validation" Phase)
To prove the value of our cleaning process, we performed a **Regression Task**:
* **Objective**: Predict a player's **Overall Rating** based on their physical and technical skills.
* **Model**: **K-Nearest Neighbors (KNN) Regressor**.
* **Preprocessing**: Applied **RobustScaler** to mitigate the impact of any remaining extreme values.
* **Comparison**: We compared the **RMSE (Root Mean Squared Error)** of the model trained on the dirty data versus the cleaned data, proving that data quality significantly improves predictive reliability.

---

## 💻 Tech Stack
* **Language**: Python 🐍
* **Environment**: Google Colab / Jupyter Notebook
* **Libraries**: `Pandas`, `NumPy`, `Scikit-Learn`, `RecordLinkage`, `Ydata-profiling`, `Matplotlib`, `Seaborn`.

---

## 📂 Repository Structure
```text
📦 FIFA_dataset_data-information-quality-project
 ┣ 📂 Dataset
 ┃ ┣ 📜 fifa.csv              # The original "dirty" dataset
 ┃ ┗ 📜 FIFA_CLEANED.csv      # The final high-quality dataset
 ┣ 📂 Report
 ┃ ┗ 📜 Report.pdf            # Detailed documentation of all choices and results
 ┣ 📜 FIFA_Project_code.ipynb # Full Python implementation (Colab compatible)
 ┗ 📜 README.md               # Project documentation
