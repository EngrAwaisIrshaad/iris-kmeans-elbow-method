# Iris Flower Clustering with K-Means

An educational machine-learning project that applies **K-Means clustering** to the Iris dataset. The notebook covers exploratory analysis, feature standardisation, cluster-count selection, visualisation, centroid-distance analysis, and post-hoc comparison with known species.

## Project objectives

- Inspect the Iris dataset and its four numeric features.
- Understand why standardisation matters for distance-based algorithms.
- Use the elbow method to examine inertia across candidate values of `K`.
- Compare silhouette scores for `K = 2` through `K = 6`.
- Fit a K-Means model with `K = 3` and visualise the clusters.
- Measure each observation's distance from its assigned centroid.
- Compare discovered clusters with actual species labels after fitting.

## Dataset

The notebook loads the Iris dataset directly from `scikit-learn`; no separate CSV file is required. It contains 150 flowers and four features: sepal length, sepal width, petal length, and petal width (all in cm). The known species are Setosa, Versicolor, and Virginica.

## Repository contents

```text
.
├── Iris_KMeans_Elbow_Method.ipynb
├── README.md
└── requirements.txt
```

## Run the notebook

### Google Colab

1. Download `Iris_KMeans_Elbow_Method.ipynb` from this repository.
2. Open [Google Colab](https://colab.research.google.com/).
3. Choose **File → Upload notebook** and select the notebook.
4. Run the cells from top to bottom.

### Local Python environment

Python 3.10 or newer is recommended.

```bash
python -m venv .venv
```

Activate the environment:
- macOS/Linux: `source .venv/bin/activate`
- Windows: `.venv\\Scripts\\activate`

Install dependencies and launch Jupyter:

```bash
python -m pip install -r requirements.txt
jupyter notebook
```

Open `Iris_KMeans_Elbow_Method.ipynb` and run all cells.

## Methodology

1. Inspect dataset shape, feature names, summary statistics, and missing values.
2. Explore petal length against petal width.
3. Standardise features using `StandardScaler` so distance calculations are not dominated by their original scales.
4. Apply the elbow method for `K = 1` through `K = 10` and plot inertia.
5. Compare silhouette scores for `K = 2` through `K = 6`.
6. Fit K-Means with `K = 3` for an exploratory comparison with the three known species.
7. Calculate each flower's Euclidean distance to its assigned centroid and summarise distances by cluster.
8. Compare cluster membership with species labels using a crosstab and bar chart.

## Interpretation

K-Means is **unsupervised**: actual species labels should not be passed to `KMeans.fit` or `fit_predict`; they are used only after clustering to interpret the output. Cluster IDs are arbitrary and do not correspond directly to species IDs. The elbow method and silhouette score assess different properties and may suggest different values of K. Re-run the notebook to reproduce metrics in your environment; exact results can vary with library versions and random initialisation.

## Dependencies

See [`requirements.txt`](requirements.txt).

## References

- [Scikit-learn: Iris dataset example](https://scikit-learn.org/stable/auto_examples/datasets/plot_iris_dataset.html)
- [Scikit-learn: Clustering documentation](https://scikit-learn.org/stable/modules/clustering.html#k-means)
