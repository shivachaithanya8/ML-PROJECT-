# Plant Disease Detection using Machine Learning

## Overview

This project detects plant diseases from leaf images using classical machine learning techniques. The model is trained on a subset of the PlantVillage dataset and focuses on selected plant categories.

## Objective

* Detect plant diseases from leaf images
* Compare multiple machine learning models
* Select the best-performing model (SVM)
* Build a prediction pipeline

## Dataset

* Source: PlantVillage Dataset
* Only selected plant classes are used
* Images resized to 64 × 64

## Methodology

### Image Preprocessing

* Resize images to 64 × 64
* Normalize pixel values
* Flatten image into vector

```
64 × 64 × 3 = 12288 features
```

### Label Encoding

* Convert class labels into numeric form

### Train-Test Split

* 80% training
* 20% testing
* Stratified sampling

### PCA (Dimensionality Reduction)

* Reduce features:

```
12288 → 250
```

### Models Used

* Logistic Regression
* K-Nearest Neighbors (KNN)
* Support Vector Machine (SVM)

## Final Model

**SVM (RBF Kernel)** is selected based on best performance.

## Evaluation Metrics

* Accuracy
* Precision
* Recall
* F1 Score
* Confusion Matrix

## Prediction Pipeline

```
Image → Resize → Normalize → Flatten → Scaler → PCA → SVM → Output
```

## Important Notes

**Preprocessing Consistency**
Training and prediction must follow the exact same steps.

**Generalization Limitation**
Model performs well on dataset images but struggles with real-world images.

## Why Not Linear / Multilinear Regression?

* These are used for continuous outputs
* This problem is classification
* Output is categorical (disease name)

## Limitations

* Uses raw pixel features
* PCA reduces information
* Limited real-world performance

## Future Improvements

* Use CNN (deep learning)
* Use better feature extraction (HOG)
* Improve dataset diversity

## How to Run

### Install dependencies

```
pip install numpy opencv-python scikit-learn joblib matplotlib seaborn
```

### Steps

1. Run the notebook
2. Train the model
3. Run prediction on test image

## Output

The model predicts the disease class of the given image.

## Author

Your Name
