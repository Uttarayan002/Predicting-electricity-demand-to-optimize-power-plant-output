# Electrical Energy Forecasting on CCPP dataset Using XGBoost 🌳
This project leverages the XGBoost regression algorithm to predict the net energy output (Power Output - PE) of a Combined Cycle Power Plant (CCPP) based on environmental factors. The goal is to optimize energy production by accurately modeling and understanding the relationship between operational conditions and power output.

## Introduction

Predicting full load electrical power output of a base load power plant is important in order to maximize the profit from the available megawatt hours. This examines and compares some machine learning regression 
methods to develop a predictive model, which can predict hourly full load electrical power output of a combined cycle power plant. The base load operation of a power plant is influenced by four main parameters, 
which are used as input variables in the dataset, such as ambient temperature, atmospheric pressure, relative humidity, and exhaust steam pressure. These parameters affect electrical power output, which is 
considered as the target variable. The dataset, which consists of these input and target variables, was collected over a six-year period. First, based on these variables the best subset of the dataset is explored 
among all feature subsets in the experiments. Then, the most successful machine learning regression method is sought for predicting full load electrical power output. 

In order for accurate system analysis with thermodynamical approaches, a high number of assumptions is necessary such that these assumptions account for the unpredictability in the solution. Without these 
assumptions, a thermodynamical analysis of a real application compels thousands of nonlinear equations, whose solution is either almost impossible or takes too much computational time and effort. To eliminate 
this barrier, the machine learning approaches are used mostly as alternative instead of thermodynamical approaches, in particular, to analyze the systems for arbitrary input and output patterns [1].
Predicting a real value, which is known as regression, is the most common problem researched in machine learning. For this reason, machine learning algorithms are used to control response of a system for 
predicting a numeric or real-valued target feature. Many real-life problems can be solved as regression problems, and evaluated using machine learning approaches to develop predictive models [2].
This paper deals with several machine learning regression methods for a prediction analysis of a thermodynamic system, which is a combined cycle power plant (CCPP) with two gas turbines, one steam turbine, and 
two heat recovery systems. Predicting electrical power output of a power plant has been considered a critical real-life problem to construct a model using machine learning techniques. To predict full load 
electrical power output of a base load power plant correctly is important for the efficiency and economic operation of a power plant. It is useful in order to maximize the income from the available megawatt hours 
(MW h). The reliability, and sustainability of a gas turbine depend highly on prediction of its power generation, particularly when it is subject to constraints of high profitability and contractual liabilities.

## System description
A combined cycle power plant is composed of gas turbines (GT), steam turbines (ST) and heat recovery steam generators (HRSG). In a CCPP, the electricity is generated by gas and steam turbines, which are combined in one cycle, and is transferred from one turbine to another. A gas turbine in a combined cycle system does not only generate the electrical power but also generates fairly hot exhaust. Routing these gases through a water-cooled heat exchanger produces steam, which can be turned


## Problem Statement
The objective is to predict the net energy output (PE) of a power plant given environmental features:

 - Ambient Temperature (AT)
 - Exhaust Vacuum (V)
 - Ambient Pressure (AP)
 - Relative Humidity (RH). Accurate prediction of PE helps in optimizing power plant operations by balancing energy demands, improving efficiency, and reducing costs and environmental impacts.

## Key Objectives:

 - Understand Data Relationships.
 - Modeling the Energy Output:
 - Performance Evaluation:
 - Evaluate the model's accuracy using appropriate regression metrics 
 - Feature Insights
 - Application Goal 

*Providing an efficient model that can be used for real-time energy output predictions, aiding in:
Operational adjustments to optimize performance.
Decision-making for maintenance or upgrades in plant systems.*

## Data Overview
The dataset used in this project contains:
Ambient Temperature( AT) in °C **|** Exhaust Vacuum (V) in cm Hg **|**  Ambient Pressure(AP) in mbar **|**  Relative Humidity (RH) in % **|**  Power Output (PE) in MW.
The dataset was sourced from the UCI Machine Learning Repository -> [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/294/combined+cycle+power+plant).

## Project Pipeline
1. **Data Exploration and Visualization**
Analyzed relationships between environmental factors and power output.
Identified trends and correlations with scatter plots and heatmaps.

2. **Data Preprocessing**
Checked for missing values and anomalies.
Ensured proper separation of features and target variables.

3. **Model Development**
Implemented XGBoost Regressor.
Conducted hyperparameter tuning using GridSearchCV for optimal model performance.

4. **Model Evaluation**
Evaluated the model using Mean Absolute Error (MAE) on test data.
Applied cross-validation to ensure generalizability.

## Technologies Used
**Python**: Core programming language. 

**Libraries**:
 - XGBoost: Model development.
 - Pandas & NumPy: Data manipulation.
 - Matplotlib & Seaborn: Data visualization.
 - scikit-learn: Preprocessing, scaling, and evaluation.

## Visualizations
 >  ### **Detailed relationship between Features and target variable**
###  - **Pair plot with PE :**
![PAIR_plot](https://github.com/user-attachments/assets/f01027e1-0979-486c-b7e0-174fbfb85b06)

### -  **Coorelation Matrix with Heatmap:**
![CORR_plot](https://github.com/user-attachments/assets/269891a0-2b8a-41fc-b163-254640cd7bbd)

### - **Data Distribution Plots:**
![DATADIS_plot](https://github.com/user-attachments/assets/e5fa2dd9-4662-4e07-a8a2-d5e6e7ef5eee)
________________________________________________________________________________________________________________________________________________________________________________________________
>  ### Environmental Factors vs. Power Output (PE)
### - AT vs PE
![ATvPE_plot](https://github.com/user-attachments/assets/52c6cc96-89e9-48d8-94e3-ccc3d9bec662)

### - V vs PE
![VvPE](https://github.com/user-attachments/assets/d45f64e5-0f11-47fb-a359-7bf8bb463897)

### - AP vs PE
![APvPE_plot](https://github.com/user-attachments/assets/44803662-3ed8-4325-bfd3-fe9984e8be03)

### - RH vs PE 
![RHvPE_plot](https://github.com/user-attachments/assets/3b22acac-5cca-4213-8f3f-7d90f8dc18a8)
_________________________________________________________________________________________________________________________________________________________________________________________________
> ### Outliers/Anomaly Detection with Viz
### - Blox plot for each columns:
![BLOXPLOT_plot](https://github.com/user-attachments/assets/f89f7c57-ef21-4cb3-aa5c-fd7fd8e53296)

 ## 5. Model Working  
### What is Ensemble Learning?
Ensemble learning is a machine learning technique that combines multiple models (often called "weak learners") to produce a stronger, more accurate model. 

Ensemble methods are broadly classified into:
- Bagging (e.g., Random Forest): Combines predictions of independently trained models by averaging (for regression) or majority voting (for classification).
- Boosting (e.g., XGBoost, AdaBoost, Gradient Boosting): Sequentially builds models where each new model focuses on correcting the errors of the previous ones.

### Model: XGBoost Regressor
XGBoost (Extreme Gradient Boosting) is a powerful and efficient machine learning algorithm primarily used for structured/tabular data. It is an optimized implementation of gradient boosting that has gained significant popularity due to its speed, accuracy, and scalability.

### How XGBoost Works**

- **Initial Prediction**: Starts with a base prediction, such as the mean for regression.

- **Error Calculation**: Calculates the residuals or errors from the current model.

 - **Model Update**: Fits a new weak learner (decision tree) to the residuals to correct errors.

 - **Combination**: Combines the previous model and the new weak learner using a learning rate to form the final prediction.

### Motivation of using Extreme Gradient Boosting

 - *Optimized Gradient Boosting*:
Combines weak learners (typically decision trees) to form a strong learner by minimizing the loss function.
Uses second-order gradients (Hessian) to improve optimization.

 - *Regularization*:
Includes L1 (Lasso) and L2 (Ridge) regularization to prevent overfitting, which standard gradient boosting lacks.

 - *Parallelization*:
Can perform tree construction in parallel, making it faster compared to traditional boosting methods.

 - *Handling Missing Values*:
Automatically learns the best way to handle missing values during training, improving usability.

 - *Tree Pruning*:
Uses a "max_depth" parameter instead of a pruning heuristic to avoid overfitting.
Stops growing trees when no further splits improve the model.

 - *Customizable*:
Supports custom loss functions and evaluation metrics.

- *Out-of-Core Computing*:
Can handle very large datasets that do not fit into memory by using efficient disk I/O.

- *Scalability*:
Works seamlessly on distributed systems using libraries like Spark and Hadoop.

> #### Summary of How XGBoost Helped
Robust Performance, XGBoost outperformed baseline models with a significantly lower MAE (2.093).
Scalability, Its ability to handle large datasets with complex interactions makes it an industry-preferred algorithm.
Insights, Provided valuable information on which factors most impact power output, offering both predictive and prescriptive value.
This structured approach demonstrates your ability to solve real-world problems and translate machine learning results into actionable business outcomes.

## Key Results
**Baseline Model Performance (No Hyperparameter Tuning)**:
> - Mean Absolute Error (MAE): 2.6003 

**After Hyperparameter Tuning**:
> - Mean Train MAE: 0.9488
> - Mean Test MAE: 2.0932
> - Cross-Validated MAE: 2.2379

## ★ Insights Gained from the Combined Cycle Power Plant (CCPP) Dataset

- **High Predictive Accuracy:** The final Mean Absolute Error (MAE) of approximately 2.093 on the test set and cross-validated mean MAE of ~2.2379 indicates that the model performs exceptionally well in predicting the Net Energy Output (PE) given the input features.This low error margin demonstrates the suitability of the XGBoost algorithm for regression tasks in this domain.

- **Feature Importance:** By analyzing the feature importances provided by XGBoost, we observed the relative influence of environmental factors: Ambient Temperature (AT) and Exhaust Vacuum (V) had the highest importance in determining the energy output, reflecting their critical role in power plant efficiency. Ambient Pressure (AP) and Relative Humidity (RH) had comparatively lesser but still significant contributions.

- **Scalability of XGBoost:** The XGBoost algorithm demonstrated its robustness by achieving high accuracy without requiring feature scaling or normalization. This reduces preprocessing complexity and highlights XGBoost's ability to provide a better precision.

## How this project contributes to optimizing power plant output from a business perspective?

**1. Efficient Resource Utilization**
How it helps: By accurately predicting power output based on environmental conditions (e.g., temperature, pressure, humidity), operators can plan energy production more precisely.

- Business Value: Reduces wastage of fuel and resources by preventing overproduction during low demand or underproduction during peak demand.

**2. Improved Operational Planning**
How it helps: Power plants can optimize maintenance schedules by analyzing patterns in power output under various conditions.

- Business Value: Minimizes downtime, ensuring consistent power supply, and reduces maintenance costs by predicting operational strain.

**3. Cost Optimization**
How it helps: Predicting power output enables better alignment of energy production with demand, helping avoid penalties for overproduction or the need to purchase energy from other sources.

 - Business Value: Improves profitability by reducing production costs while meeting demand efficiently.

**4. Environmental Compliance**
How it helps: By optimizing output to align with environmental factors, emissions and environmental impact can be reduced.

 - Business Value: Helps meet government regulations and maintain a sustainable operation, avoiding fines and fostering a positive public image.

**5. Data-Driven Decision Making**
How it helps: The model provides actionable insights based on historical and real-time data, helping managers make informed decisions.

 - Business Value: Enables strategic adjustments to operations, ensuring both profitability and sustainability.

# Insights and Conclusions:

**Operational Guidance:**
 - Temperature (AT) and Relative Humidity (RH) are key drivers of energy efficiency.
- Suggests scheduling maintenance or load adjustments during periods of unfavorable conditions ( high temperature or humidity).

**Actionable Outcomes:**
- Highlights the importance of environmental monitoring in ensuring optimal power plant efficiency.
- Recommends further study to mitigate the negative impacts of high temperatures on energy output.

> ## Considerable points:
- **Key Feature**: Ambient Temperature (AT) shows the strongest negative correlation with PE.
- **Operational** Efficiency: Higher vacuum levels (V) generally improve turbine performance.
- **Environmental Impact**: Increased Relative Humidity (RH) tends to reduce power output.

*Power plants can adjust operational strategies based on predicted outputs under varying environmental conditions, saving costs and improving efficiency.*
__________________________________________________________________________________________________________________________________________________________________________________________

## Future Work
 - Feature Engineering: Explore advanced techniques to derive additional features.
 - Deployment: Create an API for real-time energy output predictions.
 - Extended Analysis: Incorporate external datasets to analyze seasonal trends.
## Contacts
[E-mail](uttarayanhaldar433@gmail.com) **|**  [Github](https://github.com/Uttarayan002) **|** [Twitter](https://x.com/Uttarayan)
