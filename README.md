# Combining structured and unstructured data as features for deep learning in healthcare predictions    

## Overview

The intent of this project is to demonstrate meaningful way to combine both structured and unstructured data as features to build a deep learning model. I have taken a known problem in healthcare that is readmission into hospital after discharge. In this tutorial, we will learn how to build a machine learning model to predict 30-day, 60-day and 90-day hospital readmissions using the MIMIC-IV dataset. While this is something that everyone would want to try, here is the novelty of my approach: **Using the free text field as features in addition to the existing numerical features**. While hospital readmissions within 30 days of discharge are a critical healthcare quality metric, my goal is to encourage the combined use of numerical features and text features(converted to embedding using BioBert).

## Learning Objectives

The intent of this tutorial is to satisfy the requirements of the high risk project. This tutorial is expected to showcase:

- **Understanding of MIMIC-IV** large-scale electronic health record dataset  
- **Motivating a heathcare related issue** Establish a healthcare problem that can be addressed using the MIMIC-IV dataset
- **Design, Build and evaluate** Machine learning models for the stated problem using this modern approach.  
- **Creating reproducible code** with detailed documentation   
- **How can we further this space** by providing more suggestions.      

## Hypothesis   

Language models are good representation learners. They can represent unstructured corpus of text into vectors, otherwise known as embeddings. These embeddings are high dimensional vectors that preserves the semantic of an otherwise unstructured data which would be difficult to be used in machine learning algorithms.  

For this particular tutorial, readmission to hosiptal within 30, 60 and 90 days is assumed to be a function of patient demographics, the reason for admission and other admission related variables, previous admissions, length of stay for the current visit, combined length of stay for all previous visits, ICD_CODEs, the medication history and most importantly, the diagnostic notes during a perticular visit. It is likely that a lot of these covariates are endogenetic in nature. However, our goal for this is ML/DL more so than an econometric analysis. In fact, deep learning frameworks could thrive on such data analysis set up.     


## Project Structure

```
aihc_highrisk_project/
├── README.md                         # This file
├── requirements.txt                  # Python dependencies
├── data/                             # Data storage (not included in repo)
│   ├── raw/                          # Raw MIMIC-IV data
│   └── processed/                    # Processed datasets
├── notebooks/                        # Jupyter notebooks
│   ├── 01_data_exploration.ipynb     # Initial data analysis
│   ├── 02_feature_engineering.ipynb  # Feature creation
│   ├── 03_model_development.ipynb    # Model training and evaluation
│   └── 04_end_to_end.ipynb           # Complete reproducible solution

```

## Prerequisites

### Data Access
- **MIMIC-IV Access**: To be able to replicate this tutorial, you will need to complete the required training and apply for access to MIMIC-IV at [PhysioNet](https://physionet.org/content/mimiciv/2.2/). As part of the first homework in this class, it is fair to assume that you may already have access.   

- **Database Setup**: There are mutiple ways to handle the data. The easiest way would be to download the data and store them as local files. Use them as the need may be. However, a more robust way would be to set up a local(or cloud) instance of a PostgreSQL database with MIMIC-IV data loaded with all the relevant relations based on the official documentation. 

### Software Requirements
- Python 3.12+
- Jupyter Notebook
- Required packages (see `requirements.txt`)

## Project Workflow   

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

### 4. End-to-End Solution (`notebooks/04_end_to_end.ipynb`)
- **Complete reproducible solution** combining all previous work
- Automated data loading, processing, and feature engineering
- BioBERT embedding generation for diagnosis text
- Training of all three models (30d, 60d, 90d readmission prediction)
- Comprehensive evaluation and results summary
- **Run this single notebook to reproduce all results**



The first three notebooks walk you through the thought process of my analysis, while the fourth notebook will enable you to run the project end to end.

## Quick Start

To reproduce all results with a single notebook:

1. **Clone this repository**:
   ```bash
   git clone https://github.com/amannars/aihc_highrisk_project.git
   cd aihc_highrisk_project
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Obtain MIMIC-IV data** (requires PhysioNet access):
   - Download the following files from MIMIC-IV:
     - `patients.csv.gz`
     - `admissions.csv.gz` 
     - `diagnoses_icd.csv.gz`
     - `d_icd_diagnoses.csv.gz`
   - Place these files in the `data/raw/` directory

4. **Run the project**:
   - **Option A - Complete end-to-end**: Run `notebooks/04_end_to_end.ipynb`
   - **Option B - Step by step**: Run notebooks 01 → 02 → 03 → 04 in sequence

The end-to-end notebook will:
- Load and process all raw data
- Create balanced patient cohorts
- Generate BioBERT embeddings
- Train all three prediction models
- Produce comprehensive results and visualizations

**Estimated runtime**: 2-4 hours (depending on hardware and embedding generation)

## Data Notice
⚠️ **Important**: This repository contains code only. MIMIC-IV data is not included due to data use agreements. Users must obtain their own access through [PhysioNet](https://physionet.org/content/mimiciv/2.2/).   

## Acknowledgments

- MIMIC-IV database and PhysioNet for providing the dataset   
- AI 394D - Deep Learning at UTA - Notes and Code   
- Python Foundation   
- All open source libraries supporting the analysis    
- Course instructors    
- GitHub Copilot     


**Note**: This project assumes that you have completed the required training and have access to the MIMIC-IV dataset. Please ensure you comply with all data use agreements and privacy requirements. While I will not provide the data, all you will need to reproduce the project will be to simply place the data in the project/data/raw directory.   