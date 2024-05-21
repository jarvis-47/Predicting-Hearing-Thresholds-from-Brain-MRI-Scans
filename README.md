# Predicting Hearing Thresholds from Brain MRI Scans

## Overview
This repository contains the comprehensive work on predicting hearing thresholds using advanced data mining techniques applied to Brain MRI scans. The project explores the integration of Convolutional Neural Networks (CNNs), Support Vector Regression (SVR) combined with Principal Component Analysis (PCA), and eXtreme Gradient Boosting (XGBoost) to create predictive models. This effort underscores the potential of leveraging machine learning for non-invasive medical diagnostics.

## Project Details

### Team Members
- Charanjit Singh
- Parampreet Singh
- Tejashree Challagundla

### Abstract
Hearing loss significantly affects the quality of life, particularly among older adults. Advances in medical imaging and machine learning offer novel approaches for early detection and intervention. This project employs brain MRI scans to predict hearing thresholds, utilizing machine learning models such as Convolutional Neural Networks (CNNs), Support Vector Regression (SVR), and eXtreme Gradient Boosting (XGBoost).

### Problem Statement
Traditional methods of diagnosing hearing loss are predominantly reactive rather than proactive. There is a critical need for innovative approaches that can identify the onset of hearing impairment earlier and more accurately. Our project leverages brain MRI scans for detailed visualization of brain structures, to address this need. This project explores the potential of these scans, combined with advanced data mining techniques, to predict hearing thresholds.

## Data Preparation
The dataset consists of 171 subjects' gray matter images stored in .nii file format, focusing on regions crucial for auditory processing. Each MRI scan is paired with hearing thresholds at pure tone frequencies of 500 Hz and 4000 Hz. Data preprocessing steps include:
- **Conversion**: MRI scans converted to structured NumPy arrays using NiBabel.
- **Segmentation**: Selecting relevant brain regions indicative of auditory processing.
- **Normalization**: Standardizing image data to a range [0, 1].
- **Augmentation**: Doubling the dataset to enhance model robustness.

## Machine Learning Approaches

### 1. Convolutional Neural Networks (CNNs)
CNNs are designed for processing grid-like data structures, making them ideal for image analysis. Our CNN model architecture includes:
- **Input Layer**: Single-channel 3D image (113x40x113x1).
- **Convolutional Layers**: Three layers with filters (64, 128, 256) using 3x3x3 kernels.
- **Dense Layers**: Two fully connected layers (256, 128 nodes) with dropout and regularization.
- **Output**: Predicts hearing thresholds at 500 Hz and 4000 Hz.

### 2. PCA + Support Vector Regression (SVR)
Combining PCA and SVR provides an efficient approach for handling high-dimensional MRI data:
- **PCA**: Reduces dimensionality to the most significant components.
- **SVR**: Trained on PCA-reduced data to predict hearing thresholds.
- **Pipeline**: Efficient feature extraction and prediction using RBF kernel.

### 3. XGBoost
XGBoost is an advanced gradient boosting framework suited for structured data:
- **Feature Selection**: Using SelectKBest with f_regression to pinpoint top features.
- **Model Training**: MultiOutputRegressor to handle multiple regression outputs.
- **Hyperparameter Tuning**: GridSearchCV for optimal model parameters.

## Results and Evaluation
Models were evaluated using Mean Absolute Error (MAE) and Mean Squared Error (MSE):
- **CNN**: MAE: 11.14, MSE: 221.04
- **PCA + SVR**: MAE: 12.45, MSE: 244.48
- **XGBoost**: MAE: 14.38, MSE: 338.40

### Conclusion
The CNN model outperformed SVR and XGBoost, demonstrating superior capability in handling the spatial complexity of MRI data. The project highlights the potential of integrating machine learning techniques into healthcare diagnostics, paving the way for early and accurate detection of hearing impairment.
