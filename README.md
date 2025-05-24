# Face Recognition and Classification using PCA and LDA

## 📌 Overview
This project implements a complete face recognition system using **Principal Component Analysis (PCA)** and **Linear Discriminant Analysis (LDA)** on the ORL face dataset. Additionally, it includes a binary classification task to distinguish **face vs. non-face** images. The system uses dimensionality reduction and K-Nearest Neighbor (KNN) for classification.

---

## 🧠 Objectives

- Apply PCA and LDA for dimensionality reduction.
- Evaluate classification performance across multiple K values using KNN.
- Compare PCA vs. LDA in terms of:
  - Accuracy
  - Dimensionality
  - Computational efficiency
- Perform face vs. non-face classification using LDA.

---

## 📁 Dataset

### ORL Face Dataset:
- 400 grayscale images
- 40 subjects, 10 images per subject
- Image size: 92x112 (10,304 features)

### Non-Face Dataset:
- 400 grayscale turtle images (resized to 92x112)
- Used for face vs. non-face binary classification

---

## 🛠️ Project Structure

├── data/
│ ├── faces/ # ORL face images
│ ├── non_faces/ # Resized turtle images
├── src/
│ ├── pca_utils.py # PCA implementation
│ ├── lda_utils.py # LDA implementation
│ ├── knn_classifier.py # KNN logic
│ ├── preprocessing.py # Normalization & image loading
│ ├── evaluation.py # Accuracy & confusion matrix
│ └── main.py # Main pipeline for experiments
├── report/
│ └── Face_Recognition_Report.pdf
├── README.md

yaml
Copy
Edit

---

## 🔍 Methods

### ✅ PCA:
- Unsupervised dimensionality reduction
- Eigen decomposition of the covariance matrix
- Tested with α = 0.8, 0.85, 0.9, 0.95

### ✅ LDA:
- Supervised dimensionality reduction
- Uses between-class and within-class scatter matrices
- Retains at most `n_classes - 1` components

### ✅ KNN Classifier:
- Used for both PCA and LDA projections
- Evaluated with K = 1, 3, 5, 7, 9
- Weighted distance metric

---

## 📊 Results Summary

| Method | Dim. | K=1 | K=3 | K=5 | K=7 | K=9 |
|--------|------|-----|-----|-----|-----|-----|
| PCA (α=0.80) | 156 | 94% | 90.5% | 89.5% | 88% | 83.5% |
| LDA         | 39  | 95% | 95%   | 95%   | 95% | 95%   |

**LDA consistently outperforms PCA in both accuracy and dimensional efficiency.**

---

## 👤 Face vs. Non-Face Classification

- Dataset: 400 face + 400 non-face images
- Method: LDA + 1-NN
- Result: Accuracy varies with the number of non-face images
- Evaluation: Confusion matrix, accuracy analysis, limitations

---

## 🧪 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/face-recognition-pca-lda.git
   cd face-recognition-pca-lda
Install dependencies:

bash
Copy
Edit
pip install -r requirements.txt
Run the main script:

bash
Copy
Edit
python src/main.py
✅ Recommendations
Use LDA when class labels are available.

Use PCA for exploratory analysis or when data is unlabeled.

K = 1 provides best results for both PCA and LDA.

Use PCA first to reduce high-dimensional images before LDA if performance is an issue.

🧠 Authors
Mostafa Khalid – 2305256

Moataz Ahmed Samir – 2305223

Yousef Ashraf – 2305370

📌 Future Work
Use SVM and CNN for classification

Combine PCA + LDA features

Use larger or real-time datasets

Extend to multi-face detection and emotion recognition

📄 License
This project is for educational purposes and course evaluation. Not intended for commercial use.