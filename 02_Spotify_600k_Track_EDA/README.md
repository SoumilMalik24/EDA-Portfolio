# Spotify 600k Tracks Analysis and Popularity Classification

This project presents a complete data science workflow applied to the **Spotify Tracks Dataset (1921–2020)** containing more than **586,000 songs**.  
The notebook explores audio feature patterns, engineers meaningful musical features, performs clustering and PCA, and builds a machine learning model to classify a track's popularity category.

This repository is ideal for learners, researchers, and practitioners interested in:
- Music analytics  
- Audio feature engineering  
- End-to-end machine learning pipelines  
- Exploratory data analysis  
- Clustering and dimensionality reduction  

---

## Dataset

**Source:** Kaggle – Spotify Dataset 1921–2020 (600k+ Tracks)  
**Author:** Yamac Eren Ay  
**Link:** https://www.kaggle.com/datasets/yamaerenay/spotify-dataset-19212020-600k-tracks

---

## Objectives

- Clean and preprocess the dataset for analysis  
- Examine audio feature distributions and relationships  
- Engineer features that capture musical and temporal properties  
- Analyze multivariate relationships using PCA and pairplots  
- Explore natural structure using clustering  
- Build a popularity classification model using engineered features  
- Identify the most influential factors driving popularity

---

## Project Workflow

### 1. Data Loading and Inspection
- Overview of dataset structure  
- Identification of missing values and inconsistent formats

### 2. Data Cleaning
- Parsing date fields  
- Converting stringified lists into Python lists  
- Extracting main artist  
- Fixing missing values and removing duplicates  

### 3. Exploratory Data Analysis (EDA)
- Univariate and bivariate visualizations  
- Distribution study of audio features  
- Relationships between musical qualities and popularity  

### 4. Outlier and Skewness Handling
- IQR-based clipping  
- Log-transformations for heavily skewed features  
- Validation of improved statistical behavior  

### 5. Feature Engineering
Engineered features include:
- Track age  
- Decade grouping  
- Tempo categories  
- Mood classification (based on valence)  
- Energy level  
- Speechiness and vocal/instrumental classes  
- Artist productivity  
- Collaboration count  
- Popularity category (target variable)

### 6. Multivariate Analysis
- Correlation heatmaps  
- Pairwise relationships  
- PCA explained variance  
- 2D PCA projection  

### 7. Clustering
- KMeans clustering  
- Visualization of clusters in PCA space  
- Interpretation of cluster characteristics  
- Popularity distribution across clusters  

### 8. Popularity Classification Model
Models evaluated:
- Logistic Regression  
- Decision Tree  
- Random Forest  
- Gradient Boosting Classifier  

Evaluation metrics:
- Accuracy  
- Precision, recall, F1-score  
- Confusion matrix  

Feature importance extracted from tree-based models to identify impactful features.

---

## Key Insights

- Energy and loudness correlate moderately with popularity.  
- Mood (valence) does not strongly affect popularity.  
- Clustering reveals meaningful musical groupings such as energetic tracks, acoustic clusters, and instrumental clusters.  
- Engineered features such as track age, energy level, and artist track count significantly improve predictive performance.  

---

## Technologies Used

- Python  
- Pandas, NumPy  
- Matplotlib, Seaborn  
- Scikit-learn  
- Jupyter Notebook  

---

## How to Use

1. Download the dataset from Kaggle and place the CSV file in the project directory.  
2. Open the notebook in Jupyter.  
3. Run all cells sequentially to reproduce the analysis and models.  

---

## Future Improvements

- Add genre prediction using unsupervised learning  
- Build a track recommendation system using cosine similarity  
- Fine-tune models using GridSearchCV or Optuna  
- Deploy the popularity classifier as an API or web app  

---

## Author

**Soumil Malik**  
Machine Learning & Data Science Enthusiast  
For questions or suggestions, feel free to reach out or open an issue.

---

## License

This project is open-sourced under the MIT License.
