# Attention-Based CNN-LSTM for Respiratory Sound Classification

## Project Overview

Respiratory sound analysis plays a critical role in the early detection of conditions such as asthma, pneumonia, and chronic obstructive pulmonary disease (COPD). Despite advances in deep learning, many automated respiratory sound classification systems struggle with real-world challenges including environmental noise, class imbalance, and limited model interpretability. These limitations reduce clinical trust and hinder adoption, particularly in low-resource healthcare settings.

This project addresses these challenges by developing and evaluating an **attention-based CNN-LSTM hybrid model** for respiratory sound classification. The model is designed to improve **classification accuracy**, **robustness to noise**, and **model interpretability**, using targeted data augmentation and explainable AI techniques.

This repository contains the implementation associated with my MSc Data Science final project at Coventry University :contentReference[oaicite:0]{index=0}.

---

## Research Aim

To enhance the accuracy, robustness, and interpretability of respiratory sound classification systems by implementing and evaluating an attention-based CNN-LSTM model, supported by data augmentation and LIME explainability, for classifying respiratory cycles as **normal**, **crackle**, **wheeze**, or **both**.

---

## Key Objectives

- Preprocess and segment respiratory sound recordings at the respiratory cycle level  
- Extract MFCC features for baseline models and log-Mel spectrograms for deep learning models  
- Implement and compare multiple model architectures, from baseline MLPs to CNN-LSTM-Attention models  
- Address class imbalance using class weighting and targeted noise-based data augmentation  
- Evaluate model performance using accuracy, macro-F1 score, ROC-AUC, and confusion matrices  
- Apply LIME to improve transparency and interpretability of model predictions  

---

## Dataset

- **Dataset:** ICBHI 2017 Respiratory Sound Database  
- **Recordings:** 920 audio files from 126 subjects  
- **Extracted segments:** 6,898 respiratory cycles  
- **Classes:**  
  - Normal  
  - Crackle  
  - Wheeze  
  - Both (crackle and wheeze)

### Dataset Characteristics

- Clinically annotated respiratory cycles  
- Significant class imbalance, with wheeze and combined classes underrepresented  
- Controlled recording environment with limited background noise  

These characteristics informed the use of augmentation and class weighting strategies.

---

## Methodology

### Data Preprocessing

- Segmentation of full audio recordings into individual respiratory cycles  
- Resampling to 16 kHz and standardisation to fixed-length segments  
- Exploratory data analysis of duration, class distribution, and acoustic patterns  

### Feature Extraction

- **MFCCs** for baseline Multilayer Perceptron (MLP) model  
- **Log-Mel spectrograms** for CNN, CNN-LSTM, and CNN-LSTM-Attention models  

### Model Architectures

- Baseline MLP (MFCC input)  
- Convolutional Neural Network (CNN)  
- CNN-LSTM hybrid model  
- Attention-based CNN-LSTM model (final proposed architecture)  

### Data Augmentation and Imbalance Handling

- Class weighting during training  
- Spectrogram-based noise injection to simulate real-world acoustic variability  

### Explainability

- Local Interpretable Model-agnostic Explanations (LIME) applied to the final model  
- Visual explanations generated to highlight time–frequency regions influencing predictions  

---

## Evaluation Metrics

Models were evaluated using:

- Accuracy  
- Precision, Recall, and Macro F1-score  
- Confusion matrices (per class)  
- ROC and AUC  

Evaluation focused on both overall performance and minority-class sensitivity.

---

## Key Findings

- CNN-LSTM models outperformed baseline MLP and CNN-only architectures  
- The attention mechanism improved the model’s ability to focus on diagnostically relevant regions  
- Noise-based data augmentation increased robustness to acoustic variability  
- LIME explanations provided meaningful insights into model decision-making, supporting clinical interpretability  

Overall, the attention-based CNN-LSTM model achieved the best balance between **performance**, **robustness**, and **explainability**.

---

## Ethical Considerations

- The dataset is publicly available, anonymised, and ethically approved  
- Ethical approval for this project was granted by Coventry University  
- Models are intended as decision-support tools and not as replacements for clinical judgement  
- Interpretability and fairness were prioritised in line with emerging medical AI regulations  

---

## Tools and Technologies

- Python  
- TensorFlow / Keras  
- Librosa  
- NumPy, Pandas  
- Scikit-learn  
- Matplotlib, Seaborn  
- LIME  
- Google Colaboratory (GPU-enabled)  

---

## Repository Structure

```
Respiratory-Sound-Classification
│── notebooks / scripts (model training and evaluation)
│── data (ICBHI 2017 dataset – not included due to licensing)
│── figures (spectrograms, confusion matrices, ROC curves)
│── README.md
```

---

## Author

**Yvonne Musinguzi**  
MSc Data Science  
Coventry University  

Supervisor: Dr. Daniyal Haider
