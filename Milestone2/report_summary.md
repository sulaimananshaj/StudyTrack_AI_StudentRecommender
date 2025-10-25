# Milestone 2 – Clustering and Pattern Detection

## Objective
The objective of Milestone 2 is to perform behavior clustering and pattern detection on student study habits. The goal is to identify groups of students with similar study behavior and academic performance, which can later be used to provide personalized recommendations.

## Dataset Source
- The dataset used in this milestone is the merged and cleaned dataset prepared in Milestone 1.  
- It was created by merging:  
  - Students table:`students.csv` (contains student demographic and academic data)  
  - Study logs table: `study_logs.csv` (contains study hours, attendance, and related metrics)  
- Both tables were merged using the common key `student_id` to form a consolidated dataset (`merged_student_data.csv`) which is clean, with missing values handled and duplicates removed.  

## Steps Followed

### 1. Data Preparation
- Loaded the cleaned and merged dataset from Milestone 1 (`merged_student_data.csv`).  
- Verified that all numeric columns (`studytime`, `absences`, `G1`, `G2`, `G3`) were ready for clustering.  

### 2. Feature Selection
- Selected relevant numerical features for clustering:
  - `studytime`, `absences`, `G1`, `G2`, `G3`  

### 3. Standardization
- Standardized the selected features using `StandardScaler` to bring them onto the same scale (mean = 0, std = 1).  

### 4. Dimensionality Reduction
- Applied PCA (Principal Component Analysis) to reduce dimensions to 2 for visualization.  

### 5. Clustering
- Implemented K-Means clustering with 4 clusters   
- Determined cluster labels and added them to the dataset as a new column `Cluster`.  
- Calculated cluster summary statistics (mean values per cluster).  

### 6. Visualization
- Scatter Plot (PCA 2D): Visualized clusters in 2D space using different colors.  
- Bar Plot: Showed average `studytime`, `absences`, and grades per cluster.  
- Pair Plot / Box Plot: Compared distributions of numeric variables across clusters.  
- Cluster Size Distribution: Count plot showing number of students in each cluster.  

### 7. Interpretation & Insights
Based on the clustering results (4 clusters):

- Cluster 0: Top performers
  - Studytime: 0.42 (moderate-high), Absences: 0.06 (very low), Grades: ~0.79–0.83  
  - Insight: These students study regularly, have very few absences, and achieve consistently high grades.  

- Cluster 1: Hardworking but moderate performers
  - Studytime: 0.77 (highest), Absences: 0.09 (low), Grades: ~0.61–0.64  
  - Insight: Spend a lot of time studying and attend classes regularly, but grades are moderate.  

- Cluster 2: Average performers with low study commitment
  - Studytime: 0.19 (low), Absences: 0.13 (moderate), Grades: ~0.61–0.64  
  - Insight: Study very little, have moderate absences, maintain moderate grades.  

- Cluster 3: Students needing improvement
  - Studytime: 0.18 (low), Absences: 0.14 (highest), Grades: ~0.44–0.45  
  - Insight: Study very little, have the most absences, and achieve the lowest grades.  

## Tools Used
- Python 3 (Google Colaboratory)  
- Pandas, NumPy for data handling  
- Matplotlib, Seaborn for visualizations  
- Scikit-learn for PCA, StandardScaler, and K-Means clustering  

## Key Insights
- Students can be grouped into 4 clusters based on study habits and performance.  
- Top-performing students (Cluster 0) have moderate-high study hours, very low absences, and high grades.  
- Cluster 1 shows that high studytime does not always guarantee the highest grades.  
- Students in Cluster 3 require intervention to improve study habits and attendance.  
- These insights can be used to design personalized study recommendations for different groups.
