# ADL Recognition Using Unsupervised Learning

This project applies **unsupervised machine learning** to recognize *Activities of Daily Living (ADLs)* in smart home environments using binary sensor data. We use clustering methods to group behavioral patterns without activity labels and evaluate their alignment with ground-truth ADL annotations.

## 📊 Project Overview

- **Dataset**: Binary sensor events from 2 users over 35 days.
- **Goal**: Identify daily activity patterns without supervision.
- **Techniques**:
  - Feature Engineering from raw sensor logs
  - Dimensionality Reduction: PCA, t-SNE
  - Clustering: K-Means, Agglomerative, GMM
  - Evaluation: ARI, NMI, V-Measure

## 📁 Dataset Description

We used the *"Activities of Daily Living Using Binary Sensors"* dataset, which includes:
- **Sensor Description**: sensor ID, location, type
- **Sensor Events**: timestamps, sensor activation/deactivation
- **Activity Labels**: annotated ground-truth ADLs (e.g., Sleeping, Toileting)

> Sensor events were grouped into fixed 10-minute windows, forming the basis for clustering.

## 🧠 Feature Engineering

Features extracted include:
- Event count per sensor
- Location transitions
- Time-of-day encoding
- Location entropy
- Event duration statistics (mean, std)

## 🔧 Methods Used

### 1. **Dimensionality Reduction**
- **PCA**: For initial variance capture
- **t-SNE**: For 2D visualizations of clusters

### 2. **Clustering Algorithms**
| Algorithm        | Description |
|------------------|-------------|
| **K-Means**       | Centroid-based, efficient |
| **Agglomerative** | Hierarchical merging with Ward's linkage |
| **GMM**           | Probabilistic soft assignment |

## 📈 Evaluation Metrics

| Metric  | Description |
|---------|-------------|
| **ARI** | Measures similarity to true labels adjusted for chance |
| **NMI** | Captures mutual information between clusters and labels |
| **V-Measure** | Harmonic mean of homogeneity and completeness |

> Ground-truth labels were used **only for evaluation**, not during training.

## 🏆 Results Summary

| Algorithm        | ARI    | NMI    | V-Measure |
|------------------|--------|--------|-----------|
| **K-Means**       | 0.2280 | 0.3757 | 0.3757    |
| **Agglomerative** | **0.2541** | **0.4012** | **0.4016** |
| **GMM**           | 0.1938 | 0.3410 | 0.3410    |

- **Best Performance**: Agglomerative Clustering
- Visualizations via t-SNE showed better-separated clusters with Agglomerative method.

## 📌 Key Insights

- Entropy, location transitions, and time-of-day were the most impactful features.
- 10-minute window size gave the best temporal resolution.
- Unsupervised learning was effective for behavioral clustering despite sensor noise.

## 🧰 Tech Stack

- Python 3.x
- Pandas, NumPy
- Scikit-learn
- Matplotlib, Seaborn

## 🚀 Getting Started

1. Clone this repository
2. Install dependencies:

```bash
pip install -r requirements.txt
```
3. Run the notebook:
```bash
   jupyter notebook Project_2_unsupervised.ipynb
```

---
## 👥 Authors
- Mounika Seelam 
- Bhanu Prasad Dharavathu
- Prajwal Devaraj

---
## 📜 License
This project is for academic/research use only.



