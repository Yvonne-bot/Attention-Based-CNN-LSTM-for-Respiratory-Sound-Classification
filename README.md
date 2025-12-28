# Attention-Based CNN-LSTM for Respiratory Sound Classification

## Project Overview

Respiratory sound analysis plays a critical role in the early detection of conditions such as asthma, pneumonia, and chronic obstructive pulmonary disease (COPD). Despite advances in deep learning, many automated respiratory sound classification systems struggle with real-world challenges including environmental noise, class imbalance, and limited interpretability. These limitations reduce clinical trust and hinder adoption, particularly in low-resource healthcare settings.

This project develops and evaluates an **attention-based CNN-LSTM hybrid model** for respiratory sound classification. The solution targets three practical requirements for clinical-ready machine learning: **strong classification performance**, **robustness to noise**, and **transparent explanations** using explainable AI techniques.

This repository contains the implementation associated with my MSc Data Science final project at Coventry University.

---

## Research Aim

To enhance the accuracy, robustness, and interpretability of respiratory sound classification systems by implementing and evaluating an attention-based CNN-LSTM model, supported by targeted data augmentation and LIME explainability, for classifying respiratory cycles as **normal**, **crackle**, **wheeze**, or **both**.

---

## Dataset

- **Dataset:** ICBHI 2017 Respiratory Sound Database  
- **Recordings:** 920 audio files from 126 subjects  
- **Extracted segments:** 6,898 respiratory cycles  
- **Classes:** Normal, Crackle, Wheeze, Both (crackle and wheeze)

### Dataset Notes

- Clinically annotated respiratory cycles  
- Significant class imbalance, particularly for the combined class  
- Controlled recording conditions; robustness evaluated using noise augmentation  

---

## Methodology Summary

### Preprocessing
- Matched audio files with annotation files  
- Segmented recordings into individual respiratory cycles  
- Resampled audio to a consistent sampling rate and standardised segments to fixed length  

### Feature Extraction
- **MFCCs** for baseline model (MLP)  
- **Log-Mel spectrograms** for CNN, CNN-LSTM, and CNN-LSTM-Attention models  

### Models Implemented
- Baseline MLP (MFCC input)  
- CNN (spectrogram input)  
- CNN-LSTM (spectrogram input)  
- CNN-LSTM with Attention (final proposed model)  

### Imbalance Handling and Robustness
- Class weighting to improve minority-class learning  
- Spectrogram-based noise injection to simulate real-world acoustic variability  

### Explainability
- LIME used to generate local explanations highlighting influential time–frequency regions behind predictions  

---

## Evaluation

Models were evaluated using:
- Accuracy  
- Precision, Recall, and Macro F1-score  
- Confusion matrices (per class)  
- ROC and AUC  

---

## Key Findings

- CNN-LSTM models outperformed the baseline MLP and CNN-only architectures  
- The attention mechanism improved focus on diagnostically relevant spectrogram regions  
- Noise augmentation increased robustness to acoustic variability  
- LIME provided interpretable explanations supporting transparency and clinical trust  

---

## How to Run the Project

## How to Run the Project

1. Open the notebooks using **Google Colaboratory** (recommended) or **Jupyter Notebook**.

2. Run the notebooks in the following order:
   - `Final_project_Yvonne_ICBHI_2017_EDA.ipynb`  
     (Dataset exploration, segmentation checks, and visual analysis)
   - `Final_Project_Yvonne_ICBHI_2017_Respiratory_Sound_Classification.ipynb`  
     (Main modelling pipeline)
   - `Final_Project_Yvonne_ICBHI_2017_Respiratory_Sound_Classification (1).ipynb`  
     (Additional experiments and final model evaluation)

> **Note:**  
> The ICBHI 2017 dataset is not included in this repository due to licensing restrictions.  
> Please download it from the official source and update file paths in the notebooks accordingly.

---

## Repository Structure

Final_project_ICBHI-2017_Yvonne
│── Final_project_Yvonne_ICBHI_2017_EDA.ipynb
│── Final_Project_Yvonne_ICBHI_2017_Respiratory_Sound_Classification.ipynb
│── Final_Project_Yvonne_ICBHI_2017_Respiratory_Sound_Classification (1).ipynb
│── README.md

## Project Report

The full MSc project report is included in this repository and provides
a detailed academic discussion of the background, methodology, experiments,
results, ethical considerations, and conclusions of this work.

- `Final_Project__Yvonne_Musinguzi.pdf`

## Author

**Yvonne Musinguzi**  
MSc Data Science  
Coventry University  

Supervisor: Dr. Daniyal Haider
