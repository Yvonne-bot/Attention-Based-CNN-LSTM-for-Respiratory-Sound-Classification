# Attention-Based CNN-LSTM for Respiratory Sound Classification

## Project Overview

Respiratory sound analysis plays a critical role in the early detection of conditions such as asthma, pneumonia, and chronic obstructive pulmonary disease (COPD). Despite advances in deep learning, many automated respiratory sound classification systems struggle with real-world challenges including environmental noise, class imbalance, and limited interpretability. These limitations reduce clinical trust and hinder adoption, particularly in low-resource healthcare settings.

This project develops and evaluates an **attention-based CNN-LSTM hybrid model** for respiratory sound classification. The solution targets three practical requirements for clinical-ready ML: **strong classification performance**, **robustness to noise**, and **transparent explanations** using explainable AI techniques.

This repository contains the implementation associated with my MSc Data Science final project at Coventry University. :contentReference[oaicite:1]{index=1}

---

## Research Aim

To enhance the accuracy, robustness, and interpretability of respiratory sound classification systems by implementing and evaluating an attention-based CNN-LSTM model, supported by targeted data augmentation and LIME explainability, for classifying respiratory cycles as **normal**, **crackle**, **wheeze**, or **both**. :contentReference[oaicite:2]{index=2}

---

## Dataset

- **Dataset:** ICBHI 2017 Respiratory Sound Database  
- **Recordings:** 920 audio files from 126 subjects  
- **Extracted segments:** 6,898 respiratory cycles  
- **Classes:** Normal, Crackle, Wheeze, Both (crackle+wheeze) :contentReference[oaicite:3]{index=3}

### Dataset Notes

- Clinically annotated respiratory cycles  
- Significant class imbalance (especially the “Both” class)  
- Controlled recording conditions; robustness tested through noise augmentation :contentReference[oaicite:4]{index=4}

---

## Methodology Summary

### Preprocessing
- Matched audio files with annotation files
- Segmented recordings into respiratory cycles
- Resampled audio to a consistent sampling rate and standardised segments to fixed length for model input :contentReference[oaicite:5]{index=5}

### Feature Extraction
- **MFCCs** for baseline model (MLP)
- **Log-Mel spectrograms** for CNN / CNN-LSTM / CNN-LSTM-Attention models :contentReference[oaicite:6]{index=6}

### Models Implemented
- Baseline MLP (MFCC input)
- CNN (spectrogram input)
- CNN-LSTM (spectrogram input)
- CNN-LSTM with Attention (final proposed model) :contentReference[oaicite:7]{index=7}

### Imbalance Handling and Robustness
- Class weighting to improve minority-class learning
- Spectrogram-based noise injection to simulate real-world acoustic variability :contentReference[oaicite:8]{index=8}

### Explainability
- LIME used to generate local, per-sample explanations highlighting the most influential time–frequency regions behind predictions :contentReference[oaicite:9]{index=9}

---

## Evaluation

Models were evaluated using:
- Accuracy
- Precision, Recall, Macro F1-score
- Confusion matrices (per class)
- ROC and AUC :contentReference[oaicite:10]{index=10}

---

## Key Findings

- CNN-LSTM models outperformed the baseline MLP and the CNN-only architecture
- Attention improved the model’s focus on diagnostically relevant regions in the spectrogram
- Noise augmentation improved robustness to acoustic variability
- LIME provided interpretable explanations to support transparency and clinical trust :contentReference[oaicite:11]{index=11}

---
## How to Run the Project

1. Clone the repository:
   ```bash
   git clone https://github.com/Yvonne-bot/Final_project_ICBHI-2017_Yvonne.git
   cd Final_project_ICBHI-2017_Yvonne
Open the notebooks using Google Colaboratory (recommended) or Jupyter Notebook.

Run the notebooks in the following order:

Final_project_Yvonne_ICBHI_2017_EDA.ipynb
(Dataset exploration, segmentation checks, and visual analysis)

Final_Project_Yvonne_ICBHI_2017_Respiratory_Sound_Classification.ipynb
(Main modelling pipeline)

Final_Project_Yvonne_ICBHI_2017_Respiratory_Sound_Classification (1).ipynb
(Additional experiments and final model evaluation)

Note:
The ICBHI 2017 dataset is not included in this repository due to licensing restrictions.
Please download it from the official source and update file paths in the notebooks accordingly.

Repository Structure
scss
Copy code
Final_project_ICBHI-2017_Yvonne
│── Final_project_Yvonne_ICBHI_2017_EDA.ipynb
│── Final_Project_Yvonne_ICBHI_2017_Respiratory_Sound_Classification.ipynb
│── Final_Project_Yvonne_ICBHI_2017_Respiratory_Sound_Classification (1).ipynb
│── README.md
Author
Yvonne Musinguzi
MSc Data Science
Coventry University

Supervisor: Dr. Daniyal Haider
