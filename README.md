### Bearings Prediction Project - Final Report

**Author** : Jaidev Prabhu

#### Executive summary
This project aims to develop a predictive model for the failure of IoT-enabled rotating machinery using accelerometer sensor dataset and machine learning techniques. The model will leverage data from NASA's Prognostics Center of Excellence Data Set Repository. The goal is to enable accurate, real-time failure prognostication on edge devices, reducing downtime, optimizing maintenance schedules, and improving cost-effectiveness of the machinery and the facility's operation. 

#### Rationale

Predictive maintenance of industrial machinery, especially in remote or harsh environments, is a critical challenge. Unexpected failures lead to costly downtime, production losses, and potential safety hazards. This project addresses this challenge by developing a machine learning model for real-time failure prediction on edge devices. This approach reduces reliance on cloud connectivity, improves data privacy, and enables timely maintenance interventions, resulting in significant cost savings and increased operational efficiency. The focus on IoT-enabled rotating machinery ensures wide applicability across various industries, including manufacturing, energy, and transportation. 

#### Research Question
How can we accurately predict the failure of IoT-enabled rotating machinery, such as HVAC systems, turbines, engines, and motors, to prevent breakdowns and optimize maintenance schedules?

#### Data Sources

The model we develop will leverage data from NASA's Prognostics Center of Excellence Data Set Repository.
The [Experiment Definition](Experiment.md) give more details about the data, and the referenced [research paper](Bearing_Failure_Analysis.pdf) guides us on the use of the data and modelling to be used to predict Fault classes. 

#### Methodology

**Data Preprocessing:** 
- The data from the NASA collections archive was downloaded and evaluated. See the [EDA analysis](EDA_Analysis.md) document and the associated [notebook](coalased_adta_with_failure_marking.ipynb) for implementation details.

**Feature Engineering:**  
- We created new features from the existing data that can be used to model machine functionaility. Since each data point collected consists of ~20,000 values of the accelerometer sensor within a period of 1 second (data sampling was at 20KHz), we utilized statistical methods such as min, max, std, RMS (since this is a rotating machine), and advanced statistical techniques such as Skew, Kurtosis, and Shannon's Entropy - that were mentioned in the research paper to collect machine-specific signatures.

**Model Selection:** 
- Classification models such as Logistic Regression, Decision Trees, RandomForestClassifier and XGBoost were used to model the data and to develop a generic model applicable to various rotating machinery types.

**Model Evaluation:** Cross-validation and metrics like accuracy, precision, recall, and F1-score were used to evaluate the performance of the models across different types of machinery. We will display the results using the Confusion Matrix and RoC Curves.

#### Outline of project 

1. First we divided the data into Training and Test sets with a 70:30 ratio.
2. We used the following Classifier Algorithms to predict the Target Classes and evaluated the results.
3. To evaluate the results we used the classification report and the Confusion Matrix.
4. The 2 best performing models results are shown here.

#### Confusion Matrix - Random Forest Classifier

<center>
    <img src = images/rfc_initial_conf_matrix.png height = 66% width = 66% / >
</center>

#### Confusion Matrix - XGBoost Classifier

<center>
    <img src = images/xgb_initial_conf_matrix.png height = 66% width = 66% / >
</center>

5. We then proceed to fine tune these two models to get optimum parameters using `GridSearchCV`

We use the scoring to prioritize **Recall**, since we want to make sure all the positive classes are predicted optimally. Since we have an unbalanced dataset for samples in Positive classes, we use the `predict_proba` method and choose the best threshold to do the prediction. 

Since we have to use the final model on an edge device - we decide to use the XGBoost model - since it has a lower footprint in terms of size, and very closely mathes Random Forest in performance. 

We now present the final fine-tuned model's Results. 

### After fine tuning

#### Confusion Matrix - Random Forest Classifier
<center>
    <img src = images/rfc_fine_tuned_conf_matrix.png height = 66% width = 66% / >
</center>

#### Confusion Matrix - XGBoost Classifier

<center>
    <img src = images/xgb_fine_tuned_conf_matrix.png height = 66% width = 66% / >
</center>

#### Precision-Recall Curve - Random Forest Classifier

<center>
    <img src = images/P-R_Curve_RFC_fine_tuned_model.png   height = 66% width = 66% / >
</center>

## Next steps




### Notebooks

[EDA Analysis](./EDA_Analysis.md)

[Correlation Plots](./Correlation_plots.ipynb)

[Classifiers Model Training, Prediction, Scores Notebook](./Classification.ipynb)

[Fine Tuning Models](./Model_Fine_Tuning.ipynb)



##### Contact and Further Information
[mailto:jaidev@datasolve.ai](EMail)
