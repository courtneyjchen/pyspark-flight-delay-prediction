# Distributed Flight Delay Prediction with PySpark

*Due to the scale of the datasets and distributed computing requirements, this project was originally developed in a collaborative Databricks environment. As a result, the repository primarily contains the final exported HTML report and supporting presentation materials rather than the underlying execution notebooks.*

## Project Overview
Commercial flight delays are inevitable due to factors such as extreme weather, mechanical issues, and logistical constraints, creating significant operational and financial challenges for airlines. Beyond increased costs and scheduling disruptions, delays can negatively impact customer satisfaction and brand reputation. In this study, we apply machine learning to predict U.S. domestic flight departure delays, with the goal of helping airlines mitigate operational risk and improve efficiency. More specifically, we investigate the extent to which flight characteristics, weather conditions, airport activity, and carrier operational patterns can predict departure delay severity. To balance predictive granularity with model stability, we frame the problem as a multi-class classification task with four delay thresholds informed by federal (BTS, DOT, and FAA) regulations:

- No delay (<15 minutes)
- Minor delays (15–60 minutes)
- Major delays (60–240 minutes)
- Severe delays (240+ minutes)

To support this analysis, we developed a distributed machine learning pipeline in PySpark and Databricks capable of processing large-scale aviation and weather datasets. Leveraging over 31 million commercial flight records alongside NOAA weather data, the system integrated custom distributed joins, scalable preprocessing workflows, and time-aware feature engineering to enable end-to-end model training across multi-year data. We evaluated multiple machine learning architectures, including Logistic Regression, Random Forests, Gradient Boosted Trees, and Multilayer Perceptrons (MLPs), while incorporating temporal and airport connectivity features to improve predictive performance. Extensive experimentation, hyperparameter tuning, and leakage-aware validation strategies were used to optimize model robustness and minority class prediction performance within a high-volume distributed computing environment.

## Results
While the MLP achieved the highest overall accuracy on the held-out test set (0.81), XGBoost produced the strongest balanced performance across delay severity classes, achieving the highest Macro F1 score (0.33) across both cross-validation and test evaluation. Weather-related variables emerged as some of the most influential predictors of delay severity, with hourly precipitation, bulb temperature, and visibility substantially impacting model predictions. Origin airport also ranked among the strongest predictive features, suggesting that persistent airport-level operational dynamics play a major role in departure delays. The divergence between accuracy and Macro F1 highlights the impact of class imbalance, as models achieving strong overall accuracy did not necessarily perform well across less frequent but operationally important severe delay categories.

## Project Materials
*Download the HTML report and open locally in a browser for the best viewing experience*

📄 [Download Final Report (HTML)](output/final_report.html)

📊 [View Final Presentation](output/final_presentation.pdf)

**Contributers:** Brian Corgiat, Theo Hui, Ryan Schaefer
