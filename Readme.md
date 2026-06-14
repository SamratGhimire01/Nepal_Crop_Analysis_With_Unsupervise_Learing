
# 🌾 Nepal Crop Analysis with Unsupervised Machine Learning

<p align="center">
  <b>Unsupervised Machine Learning project uncovering hidden agricultural patterns across Nepal's districts</b><br>
  Clustering • Feature Engineering • PCA • Agricultural Analytics
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10+-blue?style=for-the-badge&logo=python">
  <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas">
  <img src="https://img.shields.io/badge/NumPy-Numerical%20Computing-013243?style=for-the-badge&logo=numpy">
  <img src="https://img.shields.io/badge/Scikit--Learn-Unsupervised%20ML-orange?style=for-the-badge&logo=scikit-learn">
  <img src="https://img.shields.io/badge/PCA-Dimensionality%20Reduction-success?style=for-the-badge">
  <img src="https://img.shields.io/badge/K--Means%20%26%20DBSCAN-Clustering-brightgreen?style=for-the-badge">
  <img src="https://img.shields.io/badge/Matplotlib-Visualization-11557C?style=for-the-badge">
  <img src="https://img.shields.io/badge/Status-Completed-success?style=for-the-badge">
</p>

---

## 🚀 Overview

Can machine learning rediscover Nepal's geography using only crop production data?

This project builds a complete **unsupervised machine learning pipeline** using district-level agricultural data from Nepal. Historical production statistics for four major crops were transformed into meaningful features and used to identify hidden patterns among districts.

The most fascinating result?

> The model received **zero geographic information**—no GPS coordinates, no province labels, and no elevation data—yet it successfully reconstructed Nepal's agricultural geography.

---

## ✨ Features

- ✅ Full unsupervised ML pipeline built from scratch
- ✅ Historical feature engineering using crop production data
- ✅ Comparison between K-Means and DBSCAN clustering algorithms
- ✅ Evaluation using Silhouette, Davies-Bouldin, and Calinski-Harabasz metrics
- ✅ PCA-based dimensionality reduction and visualization
- ✅ Critical analysis beyond metrics using domain knowledge
- ✅ Real-world debugging and Git workflow problem solving

---

## 📊 Dataset & Feature Engineering

The project used Nepal's district-level crop production records to engineer four historical mean features:

| Feature |
|----------|
| `Paddy_mean` |
| `Maize_mean` |
| `Millet_mean` |
| `Wheat_mean` |

These features served as the only inputs to the clustering algorithms.

No location-based features were included.

---

## 🤖 Models Compared

### K-Means Clustering
- Number of clusters: **k = 3**
- Selected after combining mathematical evaluation with domain expertise.

### DBSCAN
- Density-based clustering approach.
- Automatically detects outliers and noise points.

---

## 📈 Model Evaluation

| Metric | K-Means | DBSCAN |
|----------|----------|----------|
| Silhouette Score | 0.4553 | **0.5048** |
| Davies-Bouldin Index | 0.7869 | **0.7031** |
| Calinski-Harabasz Score | **74.57** | 60.52 |

### The Twist

DBSCAN won **2 out of 3 mathematical metrics**.

However, visualization revealed that DBSCAN had grouped nearly **80% of Nepal into one giant cluster** while labeling scattered districts as noise.

Although its scores looked stronger, the resulting clusters lacked practical meaning.

K-Means produced clusters that aligned closely with Nepal's real agricultural landscapes.

---

## 🗺️ Cluster Insights

### Cluster 1 — The Terai Belt (Grain Basket)

| Crop | Mean Production |
|--------|----------------|
| Paddy | 134,198 |
| Wheat | 34,400 |
| Millet | 617 |

Representative districts:

Jhapa, Morang, Sunsari, Saptari, Bara, Rautahat...

---

### Cluster 0 — The Mid-Hills (Maize Engine)

| Crop | Mean Production |
|--------|----------------|
| Maize | 30,800 |
| Paddy | 27,277 |
| Millet | 6,717 |

Representative districts:

Panchthar, Ilam, Bhojpur, Dhankuta, Okhaldhunga...

---

### Cluster 2 — Mountain + Urban Valley

| Crop | Mean Production |
|--------|----------------|
| Paddy | 10,169 |
| Maize | 10,224 |

Representative districts:

Solukhumbu, Manang, Kathmandu, Bhaktapur...

---

## 💡 Key Insight

The model only observed four numbers:

- Paddy production
- Maize production
- Millet production
- Wheat production

Yet it independently discovered patterns that mirrored:

- The Terai plains,
- The Mid-Hills,
- Mountain regions and urban centers.

> This is what unsupervised learning actually looks like: finding structure where no labels exist.

---

## ⚠️ Challenges Solved

### Silhouette Score Bug

Initially, the silhouette score was mistakenly computed using unscaled data.

The evaluation pipeline was corrected to use:

```python
silhouette_score(X_scaled, labels)
````

ensuring fair model comparison.

---

### GitHub Large File Issue

The original dataset exceeded GitHub's file limit.

```
climate_data.csv → 102 MB
GitHub limit → 100 MB
```

Resolved using:

* `git reset`
* `.gitignore`
* Clean commit history reconstruction

---

### Metrics vs Domain Knowledge

Although k=2 produced stronger numerical scores, k=3 generated clusters that were more interpretable from an agricultural perspective.

This project reinforced an important lesson:

> Better metrics do not always mean better models.

---

## 🛠️ Tech Stack

* Python
* Pandas
* NumPy
* Scikit-learn
* PCA
* K-Means
* DBSCAN
* Matplotlib

---

## 👨‍💻 Author

**Samrat Ghimire**

🔗 GitHub: https://github.com/SamratGhimire01

🔗 LinkedIn: https://www.linkedin.com/in/samratghimire01/

🌐 Portfolio: https://samratghimire01.com.np/

---

<p align="center">
  ⭐ If you found this project interesting, consider giving it a star!
</p>
```
