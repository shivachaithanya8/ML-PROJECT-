Plant Disease Detection using Machine Learning
Overview

This project focuses on detecting plant diseases from leaf images using classical machine learning techniques. The model is trained on a subset of the PlantVillage dataset and is designed to classify diseases for selected plant categories.

The approach uses image preprocessing, dimensionality reduction, and classification models such as Support Vector Machine (SVM), K-Nearest Neighbors (KNN), and Logistic Regression.

Objective
Identify plant diseases from leaf images
Compare multiple machine learning models
Select the best-performing model (SVM in this case)
Build a working prediction pipeline
Dataset
Source: PlantVillage Dataset
Only selected plant classes are used (not the full dataset)
Images are resized and normalized before training
Methodology
1. Image Preprocessing
Resize images to 64×64
Normalize pixel values
Flatten image into a 1D feature vector
2. Label Encoding
Convert class names into numeric labels
3. Train-Test Split
80% training, 20% testing
Stratified split to maintain class balance
4. Feature Reduction
Applied PCA (Principal Component Analysis)
Reduced features from 12288 → 250
5. Models Used
Logistic Regression
K-Nearest Neighbors (KNN)
Support Vector Machine (SVM) ← Final Model
Final Model
SVM with RBF kernel
Selected based on best accuracy among tested models
Evaluation Metrics
Accuracy
Precision
Recall
F1 Score
Confusion Matrix
Prediction Pipeline

The prediction follows the exact same steps as training:

Resize image
Normalize
Flatten
Apply scaler
Apply PCA
Predict using trained SVM
Decode label
Important Notes
1. Consistent Preprocessing

Training and prediction preprocessing must be identical. Any mismatch will lead to incorrect results.

2. Limited Generalization

The model performs well on dataset images but may struggle with:

Real-world images
Complex backgrounds
Different lighting conditions
Why Not Linear or Multilinear Regression?

Linear and Multilinear Regression are not suitable for this problem because:

They are designed for continuous output, not classification
This project requires multi-class classification
Plant disease detection involves categorical labels, not numerical prediction

Hence, classification algorithms like SVM, KNN, and Logistic Regression are used instead.

Limitations
Uses raw pixel features (no deep learning)
PCA reduces dimensionality but loses some information
Performance drops on unseen real-world images
Future Improvements
Use Convolutional Neural Networks (CNN)
Apply better feature extraction (e.g., HOG)
Improve dataset diversity for better generalization
How to Run

Install dependencies:

pip install numpy opencv-python scikit-learn joblib matplotlib seaborn
Run the notebook step-by-step
Train the model
Use the prediction script with a test image
Output

The model predicts the disease name of the input leaf image.
