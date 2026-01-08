# FIFA_dataset_data-information-quality-project
Data and Information Quality Project: FIFA Dataset Preparation
This repository contains the Data and Information Quality (DIQ) project developed by Alex Hathaway and Mattia Brianti. The goal of this project is to design and implement a complete Data Preparation Pipeline for a "dirty" FIFA dataset, ensuring it reaches a high standard of quality for potential downstream data science tasks.


👥 Contributors
Alex Hathaway

Mattia Brianti

📖 Project Overview
The project follows a structured pipeline to transform a raw, inconsistent dataset containing approximately 18,979 players and 77 attributes into a clean, standardized format.


The Data Preparation Pipeline

Data Profiling & Exploration: Preliminary analysis of data types, shapes, and column meanings.


Data Quality Assessment: Checking for data quality dimensions, specifically focusing on Duplication (identifying redundant records) and Completeness (standardizing and quantifying missing values like pd.NA).


Data Transformation & Standardization:


Column Renaming: Expanding technical abbreviations (e.g., OVA to Overall, POT to Potential) to improve interpretability for non-technical users.

String Cleaning: Removing leading white spaces and special characters from columns like Club.

Feature Engineering: Converting star-rated columns (e.g., Weak Foot ★) into pure integer formats.


Temporal Standardization: Parsing and merging complex Contract and Loan Date End information into standardized Contract Start, Contract End, and Player Status columns.


Data Deduplication: Identifying and handling non-exact duplicates to ensure unique player records.

🛠️ Technologies & Libraries
The project is implemented in Python within a Google Colab environment, utilizing the following stack:

Pandas & NumPy: For data manipulation and numerical operations.

Ydata-profiling: For automated generation of detailed data profile reports.

Scikit-Learn: Used for outlier detection (Local Outlier Factor) and data scaling (RobustScaler).

Record Linkage: For deduplication and record matching tasks.

Matplotlib & Seaborn: For data visualization.

📂 Project Structure
DIQ_Project.ipynb: The main Jupyter Notebook containing the full execution of the pipeline.

Dataset/: Contains the original fifa.csv and the final cleaned version.

Reports/: (If applicable) Contains the HTML profiling reports generated during the assessment phase.

🚀 How to Run
Clone the repository:

Bash

git clone https://github.com/Alexhath/FIFA_dataset_data-information-quality-project.git
Open the DIQ_Project.ipynb file in Google Colab or a local Jupyter environment.

Ensure all dependencies are installed:

Python

pip install pandas numpy recordlinkage ydata-profiling scikit-learn
Run the cells sequentially to observe the transformation from a dirty dataset to a cleaned one.

📊 Results Summary

Initial Completeness: ~98.6% across the entire dataset, with specific gaps identified in loan dates and "hits".


Duplicate Status: Verified no exact row-wise duplicates exist, allowing for deeper deduplication analysis based on player attributes.


Standardization: Successfully expanded 20+ columns for better readability and handled multiple inconsistent date formats.
