# Distributed Flight Delay Prediction with PySpark

## Project Overview
Commercial flight delays are inevitable due to factors such as extreme weather, mechanical issues, and logistical constraints, creating significant operational and financial challenges for airlines. Beyond increased costs and scheduling disruptions, delays can negatively impact customer satisfaction and brand reputation. In this study, we apply machine learning to predict U.S. domestic flight departure delays, with the goal of helping airlines mitigate operational risk and improve efficiency. More specifically, we investigate the extent to which flight characteristics, weather conditions, airport activity, and carrier operational patterns can predict departure delay severity. To balance predictive granularity with model stability, we frame the problem as a multi-class classification task with four delay thresholds informed by federal (BTS, DOT, and FAA) regulations:

- No delay (<15 minutes)
- Slight inconveniences (15–60 minutes)
- Substantial delays (60–240 minutes)
- Significant delays (240+ minutes)

To support this analysis, we developed a distributed machine learning pipeline in PySpark and Databricks capable of processing large-scale aviation and weather datasets. Leveraging over 31 million commercial flight records alongside NOAA weather data, the system integrated custom distributed joins, scalable preprocessing workflows, and time-aware feature engineering to enable end-to-end model training across multi-year data. We evaluated multiple machine learning architectures, including Logistic Regression, Random Forests, Gradient Boosted Trees, and Multilayer Perceptrons (MLPs), while incorporating temporal and airport connectivity features to improve predictive performance. Extensive experimentation, hyperparameter tuning, and leakage-aware validation strategies were used to optimize model robustness and minority class prediction performance within a high-volume distributed computing environment.
