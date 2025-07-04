# 🎧 Formative 1 - Sound Clustering

This project demonstrates the application of **unsupervised machine learning** techniques to an unlabeled dataset of audio recordings representing spoken digits (0–9). The goal is to explore the data through **feature extraction**, **dimensionality reduction**, and **clustering**, and to evaluate how well algorithms like **K-Means** and **DBSCAN** can discover structure in the data.

---

## 📂 Dataset Overview

The dataset consists of `.wav` files of digit pronunciations stored in a ZIP archive (`unlabelled_sounds.zip`). It is assumed that these audio files correspond to digits from 0 to 9, although labels are not provided.

---

## 🔍 Project Objectives

1. **Extract features** from raw audio using Mel Spectrograms.
2. **Visualize** raw and reduced-dimensional features.
3. Apply **dimensionality reduction** techniques (PCA and t-SNE).
4. Perform **clustering** using K-Means and DBSCAN.
5. **Evaluate** clustering performance using silhouette score and Davies-Bouldin index.
6. Compare the clustering results visually in reduced dimensions.

---

## 📌 Key Techniques Used

| Task | Tool / Technique |
|------|------------------|
| Audio Feature Extraction | `librosa` (Mel Spectrogram, Power dB) |
| Feature Scaling | `StandardScaler` |
| Visualization | `matplotlib`, `seaborn`, `pairplot`, `3D scatter` |
| Dimensionality Reduction | PCA, t-SNE |
| Clustering | K-Means, DBSCAN |
| Evaluation | Silhouette Score, Davies-Bouldin Index |

---

## 🛠️ How It Works

1. **Import Libraries**  
   Libraries for audio processing, machine learning, and visualization are imported.

2. **Load & Extract Audio Data**  
   The ZIP file is extracted and `.wav` files are loaded. Each file is converted into a **Mel Spectrogram**, reduced by averaging over time.

3. **Feature Normalization & Visualization**  
   Features are scaled and visualized using a pairplot to explore high-dimensional data without reduction.

4. **Dimensionality Reduction**  
   - **PCA** is applied to project the data linearly into 3D space.  
   - **t-SNE** is applied to capture non-linear patterns for better visualization.

5. **Clustering**  
   - **K-Means** is run for `k=2` to `k=14`. Optimal `k` is selected using the **silhouette score**.
   - **DBSCAN** is applied with default parameters for density-based clustering.

6. **Evaluation**  
   Both clustering methods are evaluated using:
   - Silhouette Score (cluster compactness)
   - Davies-Bouldin Index (cluster separation)
   - 2D t-SNE visualizations to inspect visual cluster separation

---

## 📊 Results Summary

- **t-SNE** provided clearer cluster separability than PCA, revealing patterns that are not linearly separable.
- **K-Means** consistently outperformed **DBSCAN** in this dataset based on both **silhouette score** and **visual coherence** of clusters.
- **DBSCAN** struggled with detecting consistent density due to varying speech patterns in the recordings.

---

## 📁 Files Included

| File | Description |
|------|-------------|
| `sound_clustering.ipynb` | Jupyter notebook with complete code, comments, and markdown analysis |
| `sound_clustering.pdf`   | Exported PDF version of the notebook |
| `README.md`              | This file |
| `data\unlabelled_sounds.zip`  | The original dataset|

---

## 📌 Requirements

To run this notebook locally or in Google Colab, you will need:

- Python 3.7+
- `librosa`
- `scikit-learn`
- `numpy`, `pandas`, `matplotlib`, `seaborn`

---

## 📬 Author & Notes

This project was completed as part of **Formative Assignment 1** for the Unsupervised Learning unit.  
The dataset is unlabeled but assumed to represent **spoken digits (0–9)**.

If labels were available, further evaluation using external metrics (e.g., adjusted rand index, purity) could be conducted.

---
