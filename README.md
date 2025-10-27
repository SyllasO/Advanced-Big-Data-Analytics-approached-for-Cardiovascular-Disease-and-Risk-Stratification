# Advanced-Big-Data-Analytics-approached-for-Cardiovascular-Disease-and-Risk-Stratification
This project uses Apache Spark to accelerate cardiovascular disease (CVD) risk prediction through distributed data processing and machine learning. Using the Framingham Heart Study dataset, it demonstrates how Spark’s cluster computing enhances efficiency, scalability, and model accuracy across VMs.
Dataset Information
Source: Framingham Heart Study Dataset (Kaggle)
Records: ~4,000 × 15 features
Target Variable: TenYearCHD (0 = No CHD, 1 = CHD)
Features: Age, Sex, Cholesterol, Blood Pressure, Glucose, BMI, Smoking, etc.
 Methodology
Each participant used the same dataset but applied different preprocessing and machine learning pipelines across VMs.
Preprocessing Method	ML Model	VMs Used	Purpose
KNN Imputation	Logistic Regression	1–2	Handle missing data
Z-Score Outlier Removal	Random Forest	3–4	Improve robustness
Min–Max Normalization	Gradient Boosting	5–6	Scale features
Chi-Square Feature Selection	SVM (RBF)	7–8	Enhance discriminative features
PCA Dimensionality Reduction	Neural Network (MLP)	9–10	Capture hidden patterns
 Performance Evaluation
Model	Accuracy (%)	ROC-AUC
Logistic Regression	84.67	0.525
Random Forest	84.59	0.518
Gradient Boosting	84.59	0.543
SVM (RBF)	85.06	0.512
Neural Network (MLP)	78.38	0.553
 Challenges
Synchronization and port-access issues between VMs
Frequent browser (Firefox) lags causing VM shutdowns
Difficulty connecting all 10 VMs simultaneously
Memory constraints during large Spark jobs
Tuning convergence for MLP and SVM models
 Performance Comparison
Running the program on a single VM took the longest since all computation occurred on one system with limited resources.
As additional VMs were connected, Spark distributed data and tasks across machines, leading to faster execution — especially during preprocessing and model training.
However, the speed improvement plateaued after several VMs due to network coordination overhead.
Even with partial cluster use, distributed Spark processing clearly outperformed single-node execution, confirming the scalability benefits of parallelized computation.

 Conclusion
This distributed system integrates Big Data Engineering and Machine Learning to enhance cardiovascular-risk prediction using Apache Spark.
By leveraging Spark’s in-memory cluster architecture, model execution achieved nearly 5× faster performance compared to single-node setups.
The project demonstrates that distributed analytics can drive real-time, scalable, and interpretable Clinical Decision Support Systems (CDSS) for preventive cardiovascular healthcare.
 Tools & Technologies
Apache Spark (Cluster Mode)
Python / PySpark
HDFS
SSH / SCP / VMRC
Virtual Machines (vCenter – Michigan Tech VPN)
