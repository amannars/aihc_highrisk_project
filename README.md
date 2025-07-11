# Predicting 30-Day Hospital Readmissions with MIMIC-IV

## Overview

This tutorial demonstrates how to build a machine learning model to predict 30-day, 60-day and 90-day hospital readmissions using the MIMIC-IV dataset. Hospital readmissions within 30 days of discharge are a critical healthcare quality metric, contributing to an estimated $15–$20 billion in avoidable costs annually in the United States.

## Learning Objectives

The intent of this tutorial is to satisfy the requirements of the tutorial assignment. This tutorial is expected to showcase:

- **Understanding of MIMIC-IV** large-scale electronic health record dataset  
- **Motivating a heathcare related issue** Establish a healthcare problem that can be addressed using the MIMIC-IV dataset
- **Design, Build and evaluate** machine learning models for the stated problem
- **Interpreting the model results** and understand clinical implications
- **Creating reproducible code** with detailed documentation

## Project Structure

```
aihc_tutorial_project/
├── README.md                         # This file
├── requirements.txt                  # Python dependencies
├── data/                             # Data storage (not included in repo)
│   ├── raw/                          # Raw MIMIC-IV data
│   └── processed/                    # Processed datasets
├── notebooks/                        # Jupyter notebooks
│   ├── 01_data_exploration.ipynb     # Initial data analysis
│   ├── 02_feature_engineering.ipynb  # Feature creation
│   ├── 03_model_development.ipynb    # Model training and evaluation
│   └── 04_model_interpretation.ipynb # Model explanation
├── src/                              # Source code
│   ├── __init__.py
│   ├── data_processing.py            # Data loading and preprocessing
│   ├── feature_engineering.py        # Feature creation functions
│   ├── model_training.py             # Model training utilities
│   └── evaluation.py                 # Model evaluation metrics
├── slides/                           # Presentation materials
│   └── tutorial_presentation.pptx    # Step-by-step tutorial slides
└── results/                          # Model outputs and visualizations
    ├── models/                       # Trained model files
    └── figures/                      # Generated plots and charts
```

## Prerequisites

### Data Access
- **MIMIC-IV Access**: To be able to replicate this tutorial, you will need to complete the required training and apply for access to MIMIC-IV at [PhysioNet](https://physionet.org/content/mimiciv/2.2/). As part of the first homework in this class, it is fair to assume that you may already have access.   

- **Database Setup**: There are mutiple ways to handle the data. The easiest way would be to download the data and store them as local files. Use them as the need may be. However, a more robust way would be to set up a local(or cloud) instance of a PostgreSQL database with MIMIC-IV data loaded with all the relevant relations based on the official documentation. 

### Software Requirements
- Python 3.12+
- Jupyter Notebook
- Required packages (see `requirements.txt`)

## Installation

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd aihc_tutorial_project
   ```

2. **Create a virtual environment**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up MIMIC-IV database connection**:
   - Configure your database connection parameters
   - Update the connection settings in `src/data_processing.py`

## Tutorial Workflow   

### 1. Problem Statement: Motivation and Method   
- Predicting the probability of hospital readmission withing 30 days  
- 

### 1. Data Exploration (`notebooks/01_data_exploration.ipynb`)
- Understand MIMIC-IV data structure
- Explore patient demographics and clinical variables
- Analyze readmission patterns and rates
- Identify data quality issues

### 2. Feature Engineering (`notebooks/02_feature_engineering.ipynb`)
- Create patient-level features from clinical data
- Handle missing values and outliers
- Engineer temporal features from hospital stays
- Select relevant features for prediction

### 3. Model Development (`notebooks/03_model_development.ipynb`)
- Split data into training/validation/test sets
- Train multiple machine learning models
- Evaluate model performance using appropriate metrics
- Handle class imbalance in readmission prediction

### 4. Model Interpretation (`notebooks/04_model_interpretation.ipynb`)
- Analyze feature importance
- Generate SHAP explanations
- Interpret clinical implications
- Validate model predictions

## Key Concepts Covered

### Healthcare-Specific Challenges
- **Class Imbalance**: Readmissions are relatively rare events
- **Temporal Aspects**: Time-based features and censoring
- **Clinical Interpretability**: Model decisions must be explainable
- **Data Quality**: Missing values, outliers, and measurement errors

### Machine Learning Techniques
- **Feature Engineering**: Creating clinically relevant features
- **Model Selection**: Comparing different algorithms
- **Evaluation Metrics**: AUC-ROC, precision-recall, calibration
- **Interpretability**: SHAP values and feature importance

## Expected Outcomes

After completing this tutorial, you will have:
- A working machine learning model for readmission prediction
- Understanding of healthcare data preprocessing challenges
- Skills in model evaluation and interpretation
- Reproducible code that can be applied to other healthcare datasets

## Contributing

This tutorial is designed for educational purposes. If you find issues or have suggestions for improvements, please:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- MIMIC-IV database and PhysioNet for providing the dataset
- Python Foundation   
- All open source libraries supporting the analysis
- Course instructors


---

**Note**: This tutorial assumes you have completed the required training and have access to the MIMIC-IV dataset. Please ensure you comply with all data use agreements and privacy requirements. 