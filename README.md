# Wine Classification with PCA and Logistic Regression <span style="color:#00f7ff">⎈</span>

<div style="
    background:#121a2b;
    color:#e0f2fe;
    padding:0.5rem;
    border-left:2px solid #00f7ff;
    font-family:'Segoe UI',sans-serif;
    font-size:0.85em;
    line-height:1.4;
    margin:0.2rem 0;
">

This project applies Principal Component Analysis (PCA) and Logistic Regression to classify wine cultivars using the Wine Dataset from the UCI Machine Learning Repository. The objective is to evaluate whether dimensionality reduction via PCA affects model performance and to compare results with and without PCA.
</div>

---

**Dataset Summary:**

- **Source:** `sklearn.datasets.load_wine()`
- **Samples:** 178 wine samples
- **Target:** 3 wine cultivars (target labels: 0, 1, 2)
- **Features:** 13 chemical properties of wine

---

**Preprocessing:**

1. Dropped weakly correlated features: `ash` and `color_intensity`
2. Created a new feature: `phenol_sum` (sum of `flavanoids`, `nonflavanoid_phenols`, and `total_phenols`)
3. Standardized features using `StandardScaler`
4. Applied PCA with `n_components=0.95` to retain 95% of variance

---

**Workflow:**

- Performed exploratory data analysis (EDA) and visualized correlations
- Engineered new feature `phenol_sum`
- Standardized features
- Applied PCA for dimensionality reduction
- Trained Logistic Regression on both PCA-transformed and raw scaled data
- Evaluated models using accuracy and F1-score

---

**Results:**

| Model                        | Accuracy | F1 Score |
|------------------------------|----------|----------|
| Logistic Regression (PCA)    | 1.00     | 1.00     |
| Logistic Regression (Raw)    | 1.00     | 1.00     |

- Both models achieved perfect classification on the test set
- PCA reduced feature dimensionality without affecting performance
- Stratified train-test split ensured balanced evaluation

---

<div style="
    display:grid;
    grid-template-columns:repeat(auto-fit, minmax(180px, 1fr));
    gap:0.7rem;
    margin:1rem 0;
    font-size:0.85em;
">

<div style="
    background:rgba(0,20,40,0.3);
    padding:0.4rem 0.7rem;
    border-radius:4px;
    border:1px solid rgba(0,231,255,0.2);
    max-width:200px;
">
<strong style="color:#0084ff;display:block;margin-bottom:0.2rem;">PCA + Logistic Regression</strong>
<ul style="margin:0 0 0 1em;padding:0;">
<li>Dimensionality reduction (95% variance)</li>
<li>Perfect accuracy and F1</li>
</ul>
</div>

<div style="
    background:rgba(0,20,40,0.3);
    padding:0.4rem 0.7rem;
    border-radius:4px;
    border:1px solid rgba(0,231,255,0.2);
    max-width:200px;
">
<strong style="color:#0084ff;display:block;margin-bottom:0.2rem;">Logistic Regression (Raw)</strong>
<ul style="margin:0 0 0 1em;padding:0;">
<li>All scaled features</li>
<li>Perfect accuracy and F1</li>
</ul>
</div>

</div>

---

**Conclusion:**  
PCA effectively reduced the feature space while maintaining classification accuracy. Logistic Regression was highly effective on this well-structured dataset. This project demonstrates a clean machine learning workflow incorporating feature engineering, scaling, dimensionality reduction, and model evaluation.
