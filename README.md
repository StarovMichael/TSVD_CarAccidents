1. Project Objective.
- Analyze UK traffic accident data (2005–2014) by integrating accidents, vehicles, and casualties datasets.
- Tasks include data preprocessing, descriptive modeling (clustering/anomaly detection), and supervised classification.
- The goal: identify patterns, detect anomalies, and evaluate predictive models.

2. Workflow Overview
- Data Integration
	- Joined all three tables using Accident_Index
	- Sampled a stratified subset (~10%) to preserve class distribution
	- Split into train/test sets with ~60/40 ratio
- Preprocessing
	- Encoded nominal features → numeric; numeric → nominal where required
	- Calculated IG for nominal attributes
	- Computed basic stats (mean, std) for numeric features
	- Generated histograms for nominal variables
	- Imputed missing values (e.g. numeric mean, categorical mode)
- Descriptive Modeling – Clustering & Anomaly Detection 
	- Trained K‑means clustering model on cleaned data
	- Used cluster distance metrics to flag anomalies
- Supervised Classification. Built following classifiers via Spark MLlib:
	- Decision Tree
	- Linear SVM
	- Naive Bayes
	- Ensemble trees: Random Forest & Gradient‑Boosted Trees
 - Evaluation
   	- Trained models on training set and evaluated on test set
	- Metrics calculated: accuracy, precision, recall, F1-score, MCC, confusion matrix  ￼
	- Used MCC for balanced insight, especially on skewed class distributions
