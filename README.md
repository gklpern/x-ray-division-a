# Grand X-Ray Slam Division A – Medical Image Classification

This repository contains code and experiments for the **Grand X-Ray Slam: Division A** competition.  
The goal is to build a multi-label classification model for chest X-ray images.

---

## Project Overview

- **Task:** Predict multiple pathologies from chest X-rays  
- **Approach:**
  - Swin Transformer backbone combined with residual CNN blocks
  - Mixture of Experts (MoE) layers for specialized feature extraction
  - Trained with Patient Group K-Fold cross validation
- **Evaluation metric:** Multi-label ROC AUC  

---

## Dataset and Analysis

- Total images: 107,374  
- Missing values: 14,766 in `Sex` and `Age` columns  
- Average positive labels per image: ~3.5  
- Most frequent label: Lung Opacity (48,626 cases)  
- Strong imbalance across labels (e.g. Pleural Other: 7,061 cases)  
- Distribution: frontal views dominate over lateral views  
- Age distribution peaks between 55–65 years  
- Image sizes vary widely, clustering around 2000×2000 pixels  

---

## Model Architecture

- **Backbone:** Swin Transformer (tiny/base variants)  
- **Extensions:** Residual CNN blocks for stronger feature extraction  
- **Mixture of Experts:** Expert layers specialized for subsets of labels  
- **Loss function:** BCEWithLogitsLoss  
- **Optimizer:** AdamW with weight decay  
- **Learning rate schedule:** Cosine Annealing  

---

## Repository Structure

