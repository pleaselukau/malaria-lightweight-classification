# Lightweight Malaria Cell Classification Using Color Histogram Features and Random Forests

![Python](https://img.shields.io/badge/Python-3.11-blue)
![Status](https://img.shields.io/badge/Status-Research%20In%20Progress-success)
![License](https://img.shields.io/badge/License-MIT-green)

> A systematic investigation of lightweight color representations for malaria cell classification using classical machine learning.
---

## Overview

This repository contains the complete implementation and experimental results for my research on lightweight malaria cell classification using handcrafted color histogram features and Random Forests.

Unlike many recent approaches that rely on deep convolutional neural networks, this project investigates whether compact and interpretable color histogram representations can achieve competitive performance while remaining computationally efficient.

The project accompanies an IEEE-style research manuscript currently under preparation.

---

## Research Questions

This work investigates the following questions:

1. Do HSV color histograms outperform traditional RGB histograms?
2. Which HSV channel contributes most to malaria cell classification?
3. Which classical machine learning algorithm performs best?
4. How many histogram bins are actually necessary?
5. Can lightweight feature engineering provide high accuracy while remaining computationally efficient?

---

## Dataset

This project uses the **NIH Malaria Cell Images Dataset**, a publicly available collection of segmented red blood cell images.

Dataset summary:

- **27,558** segmented cell images
- **13,779 infected cells**
- **13,779 uninfected cells**
- Binary classification task
- Thin blood smear microscopy images

Dataset:

https://ceb.nlm.nih.gov/repositories/malaria-datasets/

---

## Methodology

The complete pipeline is shown below.

```
Malaria Cell Image
        │
        ▼
Image Preprocessing
(Resize to 64×64)
        │
        ▼
Color Histogram Extraction
(RGB or HSV)
        │
        ▼
Feature Vector
        │
        ▼
Classical Machine Learning
(Random Forest)
        │
        ▼
Evaluation
```

---

## Experiments

The notebook reproduces every experiment reported in the paper.

### Experiment 1

Comparison of classical machine learning classifiers

- Random Forest
- K-Nearest Neighbors
- Logistic Regression
- Support Vector Machine
- Gaussian Naive Bayes

---

### Experiment 2

RGB vs HSV color space comparison

---

### Experiment 3

HSV channel ablation

- Hue
- Saturation
- Value
- Complete HSV

---

### Experiment 4

Histogram resolution analysis

- 4 bins
- 8 bins
- 16 bins
- 32 bins

---

### Experiment 5

Computational efficiency

- Training time
- Inference time
- Feature storage
- Feature dimensionality

---

## Final Results

| Metric | Value |
|---------|-------|
| Dataset | NIH Malaria Cell Images |
| Classifier | Random Forest |
| Feature Representation | HSV Histogram |
| Histogram Bins | 8 |
| Feature Dimension | 24 |
| Accuracy | **96.10%** |
| AUC | **0.9897** |
| 5-Fold Cross Validation | **96.06 ± 0.28%** |
| Inference Time | **0.1857 ms/image** |
| Throughput | **≈ 5,385 images/second** |
| Storage Requirement | **2.52 MB** |

---

## Repository Contents

```
.
├── ArXiv_ML_Project_Organized.ipynb
├── figures/
├── outputs/
├── paper/
├── README.md
└── requirements.txt
```

---

## Notebook

The notebook is designed to be fully reproducible.

Running it from top to bottom reproduces:

- Dataset preprocessing
- Histogram feature extraction
- Feature caching
- Model training
- Performance evaluation
- Confusion matrix
- ROC curve
- AUC calculation
- Cross-validation
- Feature importance
- PCA visualization
- Saturation histogram analysis
- Final experimental results

No manual code modification is required.

---

## Requirements

Python 3.11+

Main libraries:

- NumPy
- OpenCV
- scikit-learn
- Matplotlib
- pandas
- tqdm

Install dependencies with:

```bash
pip install -r requirements.txt
```

---

## Reproducing the Paper

To reproduce the experimental results reported in the manuscript, use the following configuration:

```
FEATURE_TYPE = "HSV"
FEATURE_SET = "HSV"

USE_SMALL_DATASET = False
RECOMPUTE_FEATURES = False

NUM_BINS = 8

RANDOM_STATE = 42
N_ESTIMATORS = 200
```

Then simply run the notebook from beginning to end.

---

## Current Status

✅ NIH experiments completed

✅ Paper draft completed

✅ Notebook fully reproducible

🔄 External validation on the BBBC041 malaria dataset is currently in progress.

---

## Future Work

The following extensions are currently under investigation:

- External validation using BBBC041 (*Plasmodium vivax*)
- Robustness to staining variation
- Robustness to image quality degradation
- Texture-based feature integration
- Additional lightweight feature representations

---

## Citation

If you find this repository useful, please cite the accompanying paper once it becomes publicly available.

```
@article{lukau2026,
  author  = {Please Lukau},
  title   = {A Systematic Investigation of Lightweight Color Histogram Representations for Malaria Cell Classification},
  journal = {Under Review},
  year    = {2026}
}
```

---

## Author

**Please Lukau**

M.S. in Computer Science Student

University of Illinois Chicago

Chicago, Illinois, USA

Email: pluka@uic.edu

---

## Acknowledgments

This work uses the NIH Malaria Cell Images Dataset made publicly available by the U.S. National Library of Medicine. The author gratefully acknowledges the researchers who collected, annotated, and released this dataset, enabling reproducible research in automated malaria diagnosis.
