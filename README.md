# Palestine Demolitions Analysis (2004–2023)  
**Exploratory Data Analysis & Predictive Modeling of Structure Demolitions**  
in the West Bank and Gaza Strip  

![Python](https://img.shields.io/badge/python-3.8%2B-blue)  
![Pandas](https://img.shields.io/badge/pandas-2.0%2B-blue)  
![Scikit--learn](https://img.shields.io/badge/scikit--learn-orange)  
![Matplotlib/Seaborn](https://img.shields.io/badge/visualization-matplotlib%20%7C%20seaborn-green)

## Project Overview  

This repository contains a complete data analysis and machine learning project based on the **UN OCHA dataset** of structure demolitions in the occupied Palestinian territory (West Bank including East Jerusalem and Gaza Strip) from **January 2004 to August 2023**.

The goal is to:  
- Perform **Exploratory Data Analysis (EDA)** to understand patterns and impacts  
- Build a **binary classification model** to predict whether a demolished structure left people homeless (`demolished = 1` if `people_left_homeless > 0`)  
- Follow a clean, reproducible data science pipeline (data loading → preprocessing → visualization → modeling → evaluation)

## Dataset  

Source: United Nations Office for the Coordination of Humanitarian Affairs (OCHA)  
File: `demolitions_pse_isr_conflict_2004-01_to_2023-08.csv`  
- 9 columns including date, location, district, type of structure, reason for demolition, housing units destroyed, people and minors left homeless  
- Over 15,000 recorded demolition events

## Project Structure  

```
├── Palestine_Demolitions_Analysis.ipynb    ← Main Jupyter Notebook (complete analysis)
├── demolitions_pse_isr_conflict_2004-01_to_2023-08.csv   ← Original dataset
├── README.md                               ← This file
└── requirements.txt                        ← Python dependencies
```

## Key Sections in the Notebook  

1. **Data Loading & Initial Exploration**  
2. **Data Preprocessing**  
   - Handling missing values (median imputation)  
   - Feature scaling (`MinMaxScaler`)  
   - One-Hot Encoding of categorical variables  
3. **Exploratory Data Analysis (EDA)**  
   - Scatter plot: `housing_units` vs `people_left_homeless` (proxy for structure size)  
   - Demolitions by district, structure type, and reason  
   - Temporal analysis (yearly & monthly trends)  
   - Correlation heatmap  
4. **Predictive Modeling**  
   - Target variable: `demolished = 1` if `people_left_homeless > 0`  
   - Train/test split (80–20)  
   - Logistic Regression baseline model  
   - Evaluation using **AUC-ROC** and **Accuracy**

## Main Findings (Highlights)  

- Strong positive correlation between destroyed housing units and people left homeless  
- Hebron, East Jerusalem, and Jenin are the most affected districts  
- Peaks in demolition activity during specific years (e.g., 2016, 2021–2023)  
- Residential structures are far more likely to cause displacement  
- The classification model achieves **AUC > 0.92** on test data (strong predictive performance)

## How to Run  

1. Clone the repository  
   ```bash
   git clone https://github.com/your-username/palestine-demolitions-analysis.git
   cd palestine-demolitions-analysis
   ```

2. (Recommended) Create a virtual environment  
   ```bash
   python -m venv venv
   source venv/bin/activate    # Linux/Mac
   venv\Scripts\activate       # Windows
   ```

3. Install dependencies  
   ```bash
   pip install -r requirements.txt
   ```

4. Launch Jupyter Notebook  
   ```bash
   jupyter notebook
   ```

5. Open `Palestine_Demolitions_Analysis.ipynb` and run all cells

## Requirements (requirements.txt)  

```txt
pandas
numpy
matplotlib
seaborn
scikit-learn
jupyter
```

## Author  

Mariem Mansour – Student  
Feel free to use, modify, and share this project (educational & research purposes).

## Disclaimer  

This project is for **educational and analytical purposes only**.  


---
**Data Source**: United Nations OCHA oPt – [Data on Demolitions](https://www.ochaopt.org/)
```
