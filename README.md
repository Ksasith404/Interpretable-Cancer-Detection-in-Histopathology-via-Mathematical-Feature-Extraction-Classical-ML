# Interpretable-Cancer-Detection-in-Histopathology-via-Mathematical-Feature-Extraction-Classical-ML
This repository contains the complete implementation of an interpretable histopathological cancer detection framework using mathematical feature extraction and classical machine learning. It includes preprocessing, 117-dimensional feature extraction, SVM, Random Forest, XGBoost models, external validation, datasets, and reproducible experiments.

The framework is designed to provide a transparent and computationally efficient alternative to deep learning approaches while maintaining high classification performance.

---

## Features

* Image preprocessing and grayscale conversion
* Haralick GLCM texture feature extraction (13 features)
* FFT spectral feature extraction (32 radial + 4 global features)
* Fractal dimension analysis (1 global + 64 local features)
* Grayscale intensity statistics (3 features)
* Construction of a 117-dimensional feature vector
* Support Vector Machine (SVM) classifier
* Random Forest (RF) classifier
* XGBoost classifier
* ROC-AUC analysis and confusion matrices
* 5-fold cross-validation experiments
* External validation on independent datasets

---

## Datasets

The experiments were conducted using publicly available histopathological image datasets containing:

* Lung Adenocarcinoma (Lung ACA)
* Colon Adenocarcinoma (Colon ACA)
* Corresponding non-cancerous tissue images

Dataset Source:

https://www.kaggle.com/datasets/andrewmvd/lung-and-colon-cancer-histopathological-images

---

## Feature Vector Composition

| Feature Group                       | Dimensions |
| ----------------------------------- | ---------- |
| Haralick Texture Features           | 13         |
| Global Fractal Dimension            | 1          |
| Local Fractal Dimensions (8×8 Grid) | 64         |
| FFT Radial Features                 | 32         |
| FFT Global Statistics               | 4          |
| Grayscale Statistics                | 3          |
| **Total**                           | **117**    |

---

## Experimental Results

| Dataset                 | RF     | XGBoost | SVM    |
| ----------------------- | ------ | ------- | ------ |
| Lung ACA (2000 Images)  | 95.00% | 94.25%  | 96.00% |
| Lung ACA (4000 Images)  | 95.88% | 96.38%  | 97.00% |
| Colon ACA (4000 Images) | 96.38% | 97.38%  | 98.00% |

External validation on an independent 2000-image lung dataset achieved:

* Accuracy: 96.25%
* TN = 976
* FP = 24
* FN = 51
* TP = 949

---

## Repository Structure

```text
├── datasets/
├── notebooks/
├── feature_extraction/
├── svm/
├── random_forest/
├── xgboost/
├── external_validation/
├── results/
├── figures/
└── README.md
```

---

## Requirements

* Python 3.x
* NumPy
* Pandas
* OpenCV
* Scikit-Learn
* XGBoost
* Mahotas
* PyWavelets
* Matplotlib
* Seaborn
* Scikit-Image

Install dependencies using:

```bash
pip install -r requirements.txt
```

---

## Running the Project

1. Download the dataset.
2. Extract the dataset into the dataset directory.
3. Run the feature extraction pipeline.
4. Train the desired classifier (SVM, RF, or XGBoost).
5. Evaluate the model using the provided scripts.
6. Perform external validation on unseen datasets.

---

## Reproducibility

All code, datasets, model configurations, and evaluation scripts are included to ensure full reproducibility of the results reported in the associated research paper.

---

## Citation

If you use this repository in your research, please cite:

> Interpretable Histopathological Cancer Detection Using Mathematical Features and Classical Machine Learning.

---

## License

This project is released for academic and research purposes.
