# Deep-Lesion Scan: A Soft Attention-Enhanced ResNet Model for Skin Lesion Classification

## Introduction
**Deep-Lesion Scan** is a deep learning project focused on early skin cancer detection by classifying dermoscopic images. It enhances the traditional ResNet50 model with a lightweight Soft Attention mechanism that helps the network focus on diagnostically critical regions. This design addresses key limitations of traditional CNNs, such as uniform feature processing and lack of interpretability. Using the HAM10000 dataset, the model demonstrates improved accuracy, better sensitivity for minority classes, and offers visual interpretability through attention maps — making it suitable for clinical applications.

---

## Project Metadata

### Authors
- **Team Members:** Danya Imran, Norah Alhusaini, Shaima Alwahas
- **Supervisor:** Dr. Muzammil Behzad
- **Institution:** King Fahd University of Petroleum and Minerals (KFUPM)

### Project Documents
- [📑 Project Report](/Deep-Lesion Scan - Final Version .pdf)
- [🎥 Project Presentation](/Deep-Lesion_Scan_Project_Slides.pptx)

### References
- **Research Paper:** [Esteva et al., 2017 - Dermatologist-level classification of skin cancer with deep neural networks]([Soft-Attention Improves Skin Cancer Classification Performance])(https://arxiv.org/pdf/2105.03358)
- **Dataset:** [HAM10000 Dataset on Kaggle](https://www.kaggle.com/datasets/kmader/skin-cancer-mnist-ham10000)

---

## Project Technical Details

### Terminologies
- **Skin Lesion:** Abnormal skin growth, can be benign or malignant.
- **Dermoscopy:** Imaging technique revealing sub-surface structures of skin lesions.
- **ResNet50:** A deep convolutional network with residual connections.
- **Soft Attention:** Mechanism to highlight important spatial features in images.
- **Label Smoothing:** Regularization method to prevent overconfident predictions.
- **Attention Maps:** Visualizations of the model’s focus regions during prediction.
- **ROC-AUC:** Metric evaluating model's ability to distinguish between classes.

---

## Problem Statement
- **Uniform Feature Treatment:** Standard CNNs treat all regions equally, missing key lesion features.
- **Imbalanced Dataset:** Common lesion classes dominate, hurting sensitivity for rare types.
- **Lack of Interpretability:** "Black-box" behavior of CNNs limits trust in clinical practice.

---

## Research Gaps
- **Bias Toward Common Lesions:** Most models favor common types (e.g., nevi).
- **Poor Localization:** CNNs do not emphasize diagnostic lesion regions.
- **Trust Barriers:** No clear explanations of model decisions for clinicians.

---

## Proposed Solution
- **Enhanced Model:** Integrate a Soft Attention module into ResNet50 after the final convolutional block.
- **Efficient Training:** Apply class-wise augmentation, weighted losses, label smoothing, and two-stage fine-tuning.
- **Interpretability:** Generate attention heatmaps showing the model’s diagnostic focus points.
- **Performance:** Achieve high accuracy while maintaining model efficiency.

---

## Key Components
- `model.py`: Defines ResNet50 with Soft Attention integration.
- `train.py`: Implements data loading, model training, validation, and callbacks.
- `utils.py`: Contains preprocessing, augmentation, and visualization tools.
- `inference.py`: Used for making predictions and generating attention maps.

---

## Model Workflow

1. **Input:** Dermoscopic image (224x224) → Normalized.
2. **Feature Extraction:** ResNet50 backbone processes the image.
3. **Attention Mechanism:** Soft Attention module enhances critical lesion features.
4. **Classification:** Fully connected layers and softmax produce class probabilities.
5. **Output:** Predicted lesion type + Attention Heatmap.

---

### Let's Detect Cancer Earlier. Let's Save Lives.
