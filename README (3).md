# Mall Customer Segmentation: Clustering and Dimensionality Reduction

## Project Overview
This project explores customer segmentation using unsupervised machine learning. The goal is to identify groups of mall customers with similar characteristics and spending behaviour, then translate those groups into practical marketing recommendations.

The analysis is implemented in `M4Assignment_08_Clustering_and_Dimensionality_Reduction.ipynb`.

## Dataset
- **Dataset name:** Mall Customer Spend
- **File:** `mall_customer_spend.xlsx`
- **Source:** [Dataset file in this GitHub repository](https://raw.githubusercontent.com/karthi-95Entri/M4A8-Clustering-and-Dimensionality-Reduction/refs/heads/main/mall_customer_spend.xlsx)

The notebook works with customer attributes including customer ID, genre, age, annual income, and spending score. Confirm the exact column names and row count by running the notebook's initial exploration cells.

### Main fields
| Field | Description |
|---|---|
| `CustomerID` | Customer identifier; excluded from clustering features because it is an ID, not a behavioural measurement. |
| `Genre` | Customer genre/category, label-encoded in the notebook. |
| `Age` | Customer age. |
| `Annual Income (k$)` | Annual income, expressed in thousands of dollars. |
| `Spending Score (1-100)` | Spending score on a 1–100 scale. |

## Project Objectives
- Inspect the dataset's structure, data types, and missing values.
- Encode the categorical `Genre` column.
- Prepare numerical features and standardize them before distance-based clustering.
- Apply K-Means, hierarchical (agglomerative) clustering, and DBSCAN.
- Explore K-Means initialization sensitivity and use the Elbow Method.
- Compare clustering approaches and evaluate cluster quality where applicable.
- Use PCA and t-SNE to create two-dimensional representations of the data.
- Profile customer segments and suggest business actions based on the results.

## Workflow
1. **Data exploration and preprocessing** — inspect shape, columns, types, and missing values; encode `Genre`; select features and scale them.
2. **K-Means clustering** — fit clusters, inspect cluster sizes and centres, test random initializations, and examine inertia with the Elbow Method.
3. **Hierarchical clustering** — inspect a dendrogram and build an agglomerative clustering model.
4. **DBSCAN** — identify density-based clusters and noise points, then compare its output with the other methods.
5. **Dimensionality reduction** — apply PCA and t-SNE for two-dimensional visual exploration.
6. **Cluster analysis** — compare customer characteristics across clusters and develop segment-specific recommendations.

## Tools and Libraries
- Python
- pandas
- NumPy
- Matplotlib
- Seaborn
- scikit-learn
- SciPy
- Jupyter Notebook / Google Colab

## How to Run
### Option 1: Google Colab
1. Upload `M4Assignment_08_Clustering_and_Dimensionality_Reduction.ipynb` to Google Colab, or open it from your GitHub repository.
2. Run the cells in order from top to bottom.
3. Ensure the dataset URL is reachable, or upload the Excel file and update the loading path if needed.

### Option 2: Local Python environment
1. Clone or download the repository.
2. Install the required packages:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn scipy openpyxl jupyter
   ```
3. Start Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
4. Open the notebook and run all cells.

## Expected Outputs
The notebook generates exploratory summaries and visualizations, cluster labels and counts, K-Means inertia/Elbow analysis, a hierarchical dendrogram, DBSCAN cluster/noise results, PCA and t-SNE plots, cluster comparisons, and customer-segment recommendations.

## Business Use Case
Customer segmentation can help a retail business tailor campaigns to different spending patterns. For example, high-income/high-spending customers may respond to premium offers, while high-income/low-spending customers may benefit from targeted promotions. Recommendations should be based on the actual cluster profiles produced by the analysis rather than assumed labels alone.

## Important Notes
- Clustering is unsupervised: the dataset does not provide a target label for training.
- Scaling is important because distance-based methods are sensitive to feature magnitude.
- `CustomerID` should not be treated as a meaningful clustering feature.
- PCA and t-SNE are visualization techniques; visual separation alone does not prove that clusters are good.
- DBSCAN may label some observations as noise (`-1`), and its results depend on parameters such as `eps` and `min_samples`.
- Cluster labels are arbitrary numbers. Interpret clusters using their feature profiles, not their numeric IDs.
- This README describes the workflow in the notebook. Record final metrics, the chosen number of clusters, and any conclusions only after running and reviewing the notebook outputs.

## Author
**Karthikeyan P.**  
Aspiring Data Scientist
