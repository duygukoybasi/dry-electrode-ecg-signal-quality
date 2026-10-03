# ECG Signal Quality Classification for Dry-Electrode Thigh ECG

Automatic classification of ECG segment quality (**good vs. poor**) recorded with polymeric dry electrodes on the thighs, a setup intended for unobtrusive monitoring (e.g. an instrumented toilet seat).

## Overview

| | |
|---|---|
| **Data** | PhysioNet TOLIET dataset: single-lead thigh-based ECG with polymeric dry electrodes |
| **Signal processing** | Butterworth band-pass and notch filtering, R-peak detection, signal-to-noise ratio (SNR) estimation, segmentation and feature extraction |
| **Models** | Logistic Regression, Random Forest, SVM, XGBoost, 1D-CNN |
| **Evaluation** | Subject-grouped cross-validation (GroupKFold), class weighting for the strong imbalance (~1:10 good to poor) |
| **Tools** | Python, NumPy, SciPy, pandas, scikit-learn, XGBoost, TensorFlow / Keras |

## Results

| Model | Accuracy | Balanced accuracy | F1 (good class) |
|---|---|---|---|
| Logistic Regression | 92.9% | 96.1% | 0.72 |
| SVM | 92.8% | 95.8% | 0.71 |
| Random Forest | 94.4% | 87.6% | 0.72 |
| 1D-CNN (raw segments) | 91.0% | 89.8% | 0.66 |

Because good-quality segments are rare, balanced accuracy and recall for the good class are more meaningful than plain accuracy. The feature-based linear models detect almost all good segments (recall ≈ 99–100%).

## How to run

Download the TOLIET dataset from PhysioNet, place the zip file in Google Drive, update `ZIP_PATH` in the notebook, and run it in Google Colab.

```
pip install -r requirements.txt
```
