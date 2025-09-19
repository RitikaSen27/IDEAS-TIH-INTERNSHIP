# Breast Cancer Data Clustering Project

## 📌 Overview
This project explores the **Breast Cancer Wisconsin (Diagnostic) dataset** using machine learning techniques.  
The main objectives were:  
1. Perform **Exploratory Data Analysis (EDA)** to understand the dataset.  
2. Apply **dimensionality reduction (PCA)** to simplify the dataset into 2 dimensions.  
3. Use **K-Means clustering** to group the data into clusters.  
4. Visualize the results using **Matplotlib** (and OpenCV as an additional option).  

The project demonstrates how unsupervised learning methods like clustering can provide insights into high-dimensional medical data.

---

## 📊 Dataset
The dataset used is the **Breast Cancer Wisconsin (Diagnostic) dataset**, which contains 569 samples with 30 features describing characteristics of cell nuclei present in digitized images of breast masses.  

- **Target classes**: Malignant (cancerous) or Benign (non-cancerous)  
- **Number of features**: 30  

### Source:
- Scikit-learn built-in dataset: [scikit-learn breast cancer dataset](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_breast_cancer.html)  
- Original UCI source: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/breast+cancer+wisconsin+(diagnostic))  

---

## ⚙️ Methodology
### 1. Data Loading & EDA
- Loaded dataset using `sklearn.datasets.load_breast_cancer()`.  
- Performed **basic EDA**:  
  - Checked dataset shape, features, and target distribution.  
  - Plotted **correlation heatmap** to identify relationships between features.  
  - Visualized scatter plots of key features (e.g., mean radius, mean perimeter, mean area).  

### 2. Data Preprocessing
- Standardized features using `StandardScaler` to normalize the data.  

### 3. Dimensionality Reduction
- Applied **PCA (Principal Component Analysis)** to reduce the dataset from 30 dimensions to **2 dimensions** for easier visualization.  

### 4. Clustering
- Implemented **K-Means clustering** (with k=2 and k=3 for experimentation).  
- Evaluated clusters using **Silhouette Score**.  

### 5. Visualization
- Plotted clustering results in 2D using **Matplotlib**.  
- Optional visualization using **OpenCV** (scatter plot with colored clusters).  

---

## 📈 Results
- PCA successfully reduced 30 features into 2 dimensions while retaining most variance.  
- K-Means was able to cluster the dataset into groups that broadly align with the malignant vs benign classification.  
- **Silhouette Score** provided a measure of cluster quality.  
- Visualizations clearly showed separation between clusters.  

---

## 🛠️ How to Run
### Requirements
Install dependencies:
```bash
pip install numpy pandas matplotlib seaborn scikit-learn opencv-python
```

### Run the project
Open the notebook in **Google Colab** or run the Python script in **VS Code / Jupyter Notebook**:
```bash
python breast_cancer_clustering.py
```

---

## 📷 Sample Visualizations
- Correlation heatmap of features.  
- Scatter plot of PCA-reduced dimensions.  
- K-Means clusters with centroids marked.  

---

## 📌 Conclusion
This project demonstrates how **unsupervised learning** (K-Means clustering) combined with **dimensionality reduction (PCA)** can be applied to medical datasets for insights and pattern discovery.  

---

## 👩‍💻 Author
- Ritika Sen 
- Data Science Student | Exploring ML & AI
- Demo video of the project:https://drive.google.com/file/d/1kPo9dOBGVTe6it5lbWJmKtsXwO9t9a7v/view?usp=drive_link
