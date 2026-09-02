# Predictive Maintenance: Machine Learning Anomaly Detection for Maritime Supply Chain Ship Operations



> **Identifying anomalous ship engine behaviour via Isolation Forest and OCSVM to enable timely maintenance and reduce operational downtime.**



[![Current Project Status](https://img.shields.io/badge/Status-Actively_Refactoring-orange.svg)](#)



![Image showing the anomalies detected across the different methods: IQR, OCSVM, and Isolation Forest. Plots are displayed on the PC1-PC2 axes, which account for around 40% of variance. IQR method finds records with more than two features falling outside the IQR, relating to an anomaly rate ~1-5%. OCSVM and Isolation Forest methods are tuned to give a similar and comparable anomaly rate.](assets/anom_method_comparison.png)



## ✦ Overview

- **Problem Statement:** A poorly maintained ship engine accelerates wear and tear, risking catastrophic failure, supply chain inefficiencies, safety hazards, and revenue loss.
- **Objective:** Detection of anomalous engine conditions at a target rate of 1-5% via baseline statistical methods and machine learning models to facilitate early intervention.
- **Impact:** Identifying anomalous behaviour enables timely maintenance which eases short-term engine load, limits fuel consumption, and ensures customer satisfaction through timely deliveries.



## ✦ Tech Stack

**Python**, **pandas**, **seaborn**, **matplotlib**, **scikit-learn**



## ✦ Data

- **Source(s):** IEEE Dataport dataset by D. Mohakul (2022).
- **Size:** 19,535 records across 6 continuous features.
- **Notable Characteristics:** The data is continuous and multidimensional without significant pair-wise correlations, requiring dimensionality reduction (PCA) to visualise effectively.



## ✦ Methodology

- **Preprocessing:** Features were scaled to have a mean of 0 and standard deviation of 1, satisfying the distance-based requirements of OCSVM and PCA.
- **Feature Engineering:** PCA was applied to project the high dimensional data onto a 2D plane to enable visualisation.
- **Modelling:** Isolation Forest was selected as the optimal model due to its computational efficiency in finding anomalies paired with superior explainability compared to OCSVM. The baseline Inter-Quartile Range (IQR) approach categorises a record as anomalous when more than two records fall outside the IQR of its respective feature distribution. This was rejected as it treats all anomalies equally without weighting severity or pair-wise interactions.
- **Evaluation:** Models were tuned to an expected anomaly rate of 1-5% to ensure revenue is not capped by excessive maintenance whilst preserving adequate signals of anomalous behaviour to prevent catastrophic failure.



## ✦ Key Results and Outputs

- PCA revealed anomalies are intertwined with the normal data across PC1 and PC2, so anomalies are driven by localised, low-variance, or non-linear relationships which require lower-variance PCs or more advanced techniques for effective detection.
 - A reproducible Python pipeline was developed, capable of comparing statistical (IQR) and machine learning (OCSVM, Isolation Forest) anomaly detection techniques.



## ✦ Roadmap and Limitations

• The current models do not account for the temporal nature of ship data, treating each record as an independent event rather than sequential.
 • Future work should incorporate temporal reasoning and derivatives to understand the rate of change of variables as they tend towards anomaly boundaries.

- **Limitation:** The current models do not account for the temporal nature of ship data, treating each record as an independent event rather than sequential and correlated with one another.
- **Future Work:** Temporal reasoning and derivative based operators should be implemented to understand the rate of change of variables as they tend towards anomaly boundaries for more effective predictions.