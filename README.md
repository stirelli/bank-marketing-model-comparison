# Practical Application III: Comparing Classifiers

This repository contains the project for predicting client subscription likelihood to term deposits after a marketing campaign, allowing banks to optimize their campaign efficiency and target high-potential clients.

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
2. **Baseline Model**: Establish a baseline performance using a `DummyClassifier` to set a minimum performance benchmark.
3. **Model Building**: Implement four different classifiers (Logistic Regression, K-Nearest Neighbors, Decision Tree, and SVM) with default hyperparameters.
4. **Model Evaluation**: Compare models based on accuracy and ROC-AUC metrics using cross-validation.
5. **Feature Analysis**: Identify key features contributing to subscription likelihood and provide actionable recommendations based on feature insights.

## Methodology
1. **Data Preprocessing**: Cleaned the dataset by handling missing values, encoding categorical variables, and scaling numerical features.
2. **Exploratory Data Analysis (EDA)**: Visualized feature distributions and calculated the correlation matrix to identify relationships between variables.
3. **Modeling**:
   - Created and evaluated a baseline model using a stratified `DummyClassifier`.
   - Built and compared four machine learning models: Logistic Regression, K-Nearest Neighbors, Decision Tree, and Support Vector Machine.
4. **Evaluation Metrics**:
   - **Accuracy**: To gauge general predictive power.
   - **ROC-AUC**: To handle the class imbalance effectively, highlighting the model’s capability to distinguish between positive and negative cases.

## Findings and Recommendations
### Key Findings
- **Top Features**: Employment variation rate, consumer price index, days since last contact, Euribor 3-month rate, and contact method emerged as influential factors.
- **Model Performance**: SVM demonstrated the best balance between accuracy and ROC-AUC, making it a top candidate for further optimization.
- **Baseline Comparison**: All models outperformed the baseline, confirming predictive capability above random chance.

### Recommendations
- **Targeting Strategy**: Focus campaigns on clients recently contacted, especially during economically favorable periods.
- **Timing and Economic Indicators**: Leverage indicators like employment rates and consumer price indexes to align campaign timing with high conversion potential.
- **Personalization**: Offer personalized products to clients with uncertain economic indicators to improve subscription rates.

## Next Steps
1. **Hyperparameter Tuning**: Fine-tune models to potentially improve performance.
2. **Feature Engineering**: Explore additional interactions or transformations to capture complex relationships in the data.
3. **Deployment and Monitoring**: Deploy the chosen model and set up a system to monitor performance over time, ensuring it continues to meet business goals.

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

## Link to Notebook

You can view the detailed analysis and results in the [notebook](https://github.com/stirelli/bank-marketing-model-comparison/blob/main/notebook.ipynb).
