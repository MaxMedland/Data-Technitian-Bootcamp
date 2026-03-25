# 🔬 Blood Cell Anomaly Detection & Classification (2025)

## 📌 Project Overview
This project provides an end-to-end data science pipeline—from raw data auditing to machine learning deployment—focused on the **‘Blood Cell Anomaly Detection 2025’** dataset. The study analyzes **5,880 clinical records** across 19 different cell types to bridge the gap between manual clinical observations and automated AI diagnostics.

**Key Objective:** To evaluate the structural differences between normal and abnormal cells, validate the reliability of AI classifiers against human expert judgment, and develop high-performance predictive models o accurately automate the detection of cellular anomalies and cell types.

---

## 🛠️ Tech Stack & Tools
| Phase | Tools |
| :--- | :--- |
| **Data Auditing** | ![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=flat&logo=microsoft-excel&logoColor=white) |
| **Visual Analytics** | ![Tableau](https://img.shields.io/badge/Tableau-E97627?style=flat&logo=Tableau&logoColor=white) ![PowerBI](https://img.shields.io/badge/Power_BI-F2C811?style=flat&logo=microsoft-power-bi&logoColor=black) |
| **Development** | ![Google Colab](https://img.shields.io/badge/Google_Colab-F9AB00?style=flat&logo=google-colab&logoColor=white) ![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white) |
| **Libraries** |![Matplotlib](https://img.shields.io/badge/Matplotlib-ffffff?style=flat&logo=Matplotlib&logoColor=black) ![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white) ![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white) ![Scikit-Learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white) ![Seaborn](https://img.shields.io/badge/Seaborn-4479A1?style=flat&logo=python&logoColor=white)|

---

## 📈 Methodology & Insights

### 1. Data Auditing & Cleaning (Excel)
* **Integrity Check:** Verified 5,880 unique records with zero duplicates.
* **Feature Engineering:** Created new diagnostic columns, including clinical ratios (e.g., **Nucleus-to-Cytoplasm ratio**), **R-G-B Intensity Percentages**, and **Confidence Score Differences**, to provide deeper layers for visualization.
* **Baseline Profiling:** established that the dataset contains a majority of **Normal cells (4,000)** vs. **Anormal cells (1,880)**.

### 1. Data Auditing & Feature Engineering (Excel)
* **Integrity Check:** Conducted duplicate checking and conditional formatting to ensure data quality.
* **Advanced Formulas:** Used `XLOOKUP` and `INDEX/MATCH` to manage clinical parameters.
* **Feature Engineering:** Created new diagnostic columns, including **R-G-B Intensity Percentages** and **Confidence Score Differences**, to provide deeper layers for visualization.


### 2. Demographic Trend Exploration (Tableau)
* Developed an interactive dashboard to visualize abnormality rates across age groups:
    * **Adults:** 3,276 cells
    * **Elderly:** 1,455 cells
    * **Pediatric:** 1,149 cells
* **Key Finding:** Identified specific proportions of normal vs. anormal cells, determining which cell types are most prevalent within certain demographic filters (Age Group and Sex).


### 3. Classification Confidence Study (Power BI)
* Assessed the "Trust Gap" by plotting scores from human experts against the CytoDiffusion classifier.
* **Insight:** Utilized a scatter plot with a trend line to show a strong positive correlation, supported by a negligible average confidence difference of **0.08**.
* **Interactivity:** Integrated slicers to filter potential confounding variables like **Image Resolution** and **Microscope Model**.


### 4. Machine Learning Pipeline (Python/Colab)
* **EDA:** Utilized `Seaborn` pairplots and heatmaps to identify **Multicollinearity**, informing the choice of regularized models.
* **Modeling:** Compared three classification approaches to identify the most robust solution for binary anomaly detection:
    * **Logistic Regression:** Accuracy: **0.841**
    * **Ridge Regression:** Accuracy: **0.828**
    * **Lasso Regression:** Accuracy: **0.841**
* **Evaluation:** While the project models achieved high accuracy, the results highlighted that the classifier was more effective at identifying normal cells due to the inherent class imbalance (4,000 normal vs. 1,880 anormal).

---

## 📂 Repository Structure
```text
├── README.md                          # Project documentation
├── blood_anomaly_project.ipynb        # Google Colab Python script (ML Pipeline)
├── blood_cell_anomaly_detection.csv   # Raw dataset (5,880 records)
├── blood_cell_anomaly_sheet.xlsx      # Excel Worksheet (Preliminary analysis)
├── classification_analysis.pbix       # Power BI Report (AI vs. Human Confidence)
└── demographic_summaries.twb          # Tableau Workbook (Cohort Analysis)
```

---

### 💡 Key Results

* **AI-Human Diagnostic Alignment:** The analysis revealed a strong positive correlation between human experts and the CytoDiffusion classifier. The average confidence variance was a negligible **0.08**, suggesting that the automated system is highly reliable for clinical decision support.
* **Critical Structural Predictors:** Feature importance analysis identified **Nucleus Area Percentage**, **Granularity Score**, and the **Nucleus-to-Cytoplasm Ratio** as the most significant biological markers for identifying cellular anomalies.
* **Predictive Performance:** While the inspiration model reached an accuracy of 0.99, the custom **Ridge Regression** model developed in this project proved most effective at handling feature multicollinearity, providing a robust F1-score for anomaly detection.
* **Demographic Insights:** Data visualization confirmed that while anomaly rates are consistent across sexes, specific cell types such as **Blast Cells** and **Schistocytes** are 100% indicative of an anormal classification regardless of patient age group (Pediatric, Adult, or Elderly).

---

### 🔗 Resources

* **Primary Dataset:** [Blood Cell Anomaly Detection 2025 (Kaggle)](https://www.kaggle.com/datasets/alitaqishah/blood-cell-anomaly-detection-2025/data)
* **Academic Inspiration:** [Deltadahl et al. (2025). Deep generative classification of blood cell morphology](https://www.nature.com/articles/s42256-025-01122-7).
