# Practical Application Assignment 17.1: Comparing Classifiers

This repository contains the project for **Practical Application Assignment 17.1: Comparing Classifiers**.  
The objective of this project is to analyze factors that influence clients' likelihood to subscribe to a term deposit, optimizing marketing campaigns using various machine learning models.

## Table of Contents
1. [Link to Notebook](https://github.com/stirelli/bank-marketing-model-comparison/blob/main/notebook.ipynb)
2. [Project Overview](#project-overview)
3. [Project Objectives](#project-objectives)
4. [Methodology](#methodology)
5. [Findings and Recommendations](#findings-and-recommendations)
   - [Key Findings](#key-findings)
   - [Recommendations](#recommendations)
6. [Next Steps](#next-steps)
7. [Repository Structure](#repository-structure)
8. [How to Run](#how-to-run)
9. [Conclusion](#conclusion)

## Project Overview

The goal of this project is to build and evaluate predictive models to determine the likelihood of clients subscribing to a term deposit. By identifying high-potential clients, the bank can enhance campaign efficiency, saving resources and improving conversion rates. The primary success metrics are accuracy and ROC-AUC, given the class imbalance in the dataset.

## Project Objectives
1. **Data Exploration**: Understand the dataset through summary statistics and visualizations, with a focus on identifying key features and potential relationships with the target variable.
2. **Baseline Model**: Establish a baseline performance to set a minimum performance benchmark.
3. **Model Building**: Implement four different classifiers (Logistic Regression, K-Nearest Neighbors, Decision Tree, and SVM) with default hyperparameters.
4. **Model Evaluation**: Compare models based on accuracy and ROC-AUC metrics using cross-validation.
5. **Model Improvement**: Refine models by exploring additional feature engineering, hyperparameter tuning, and adjusting evaluation metrics to enhance performance.
6. **Feature Analysis**: Identify key features contributing to subscription likelihood and provide actionable recommendations based on feature insights.

## Methodology
1. **Data Preprocessing**: Cleaned the dataset by handling missing values, encoding categorical variables, and scaling numerical features.
2. **Exploratory Data Analysis (EDA)**: Visualized feature distributions and calculated the correlation matrix to identify relationships between variables.
3. **Modeling**:
   - Created and evaluated a baseline model.
   - Built and compared four machine learning models: Logistic Regression, K-Nearest Neighbors, Decision Tree, and Support Vector Machine.
4. **Evaluation Metrics**:
   - **Accuracy**: To gauge general predictive power.
   - **ROC-AUC**: To handle the class imbalance effectively, highlighting the model’s capability to distinguish between positive and negative cases.

## Findings and Recommendations

### Key Findings
- **Top Features**: The most influential features in predicting subscription likelihood included:
   - **Employment Variation Rate**: Reflects economic stability, likely impacting clients' financial decision-making.
   - **Consumer Price Index**: Indicates inflation, potentially affecting clients' willingness to invest.
   - **Days Since Last Contact**: More recent client interactions increase conversion likelihood, as clients tend to respond more favorably when a campaign is recent.
   - **Euribor 3-month Rate**: Serves as a broad economic indicator, influencing client decisions based on overall financial conditions.
   - **Contact Method**: Certain methods, like telephone contact, may be more effective in engaging clients due to the personal connection it fosters.

- **Model Performance**:
   - **Support Vector Machine (SVM)**: The SVM model showed training accuracy of 0.6929 and test accuracy of 0.6964, with a ROC-AUC of 0.7670, indicating moderate effectiveness. However, it struggled with a high rate of False Positives, which could result in wasted resources on clients less likely to convert.
   - **Decision Tree**: This model achieved high accuracy (training: 0.9014, test: 0.9000) with a ROC-AUC of 0.8002. It excelled in identifying the negative class but had a significant number of False Negatives, which could lead to missed opportunities to target potential subscribers.
   - **K-Nearest Neighbors (KNN)**: KNN demonstrated strong accuracy (training: 0.9047, test: 0.8990) but with a lower ROC-AUC of 0.7682, reflecting moderate performance in distinguishing classes. The high False Negative rate suggests it may not be ideal for accurately identifying likely subscribers.
   - **Logistic Regression**: Logistic Regression achieved stable accuracy (training: 0.8990, test: 0.9009) and a ROC-AUC of 0.7974. Although it provided balanced classification results, a moderate rate of False Negatives indicates that additional tuning could further improve its ability to identify potential subscribers.

- **Baseline Comparison**: All models outperformed the baseline model, confirming predictive capability above random chance. This indicates that each model provides valuable insights, forming a foundation for further optimization to enhance the identification of likely subscribers.

### Recommendations
- **Targeting Strategy**: Focus campaigns on clients recently contacted, as they are more likely to respond positively to the campaign. Timing campaigns during economically favorable periods can also improve engagement and conversion.
- **Timing and Economic Indicators**: Leverage indicators like employment rates and consumer price indexes to optimize campaign timing, aligning efforts with periods of high economic stability to maximize conversion potential.
- **Personalization**: Offer personalized products to clients with uncertain economic indicators, as they may benefit from customized options that align with their current financial situation, potentially improving subscription rates.

## Next Steps
1. **Further Hyperparameter Tuning**: While initial hyperparameter tuning has been performed, additional exploration of the parameter space may yield further performance gains.
2. **Enhanced Feature Engineering**: Continue exploring additional interactions or transformations to better capture complex relationships in the data.
3. **Deployment and Monitoring**: Deploy the refined model and set up monitoring to track real-world performance over time, ensuring alignment with business objectives.

## Repository Structure

- `data/`: Contains the dataset (`bank-additional-full.csv`).
- `models/`: Contains model comparison metrics and model weights (`results.pkl`).
- `notebook.ipynb`: Jupyter Notebook with all analysis and modeling steps.
- `.gitignore`: Specifies files and directories to be ignored by Git.

## How to Run

1. Clone the repository:

   ```bash
   git clone https://github.com/stirelli/bank-marketing-model-comparison.git

2. Install the necessary packages:

   ```bash
   pip install -r requirements.txt

3. Run the Jupyter Notebook:

   ```bash
   jupyter notebook notebook.ipynb

## Conclusion

This project demonstrates the application of machine learning techniques to enhance marketing strategies by predicting client subscription likelihood. The models built provide actionable insights that can improve targeting strategies and align campaign timing with favorable economic conditions, maximizing conversion rates.
