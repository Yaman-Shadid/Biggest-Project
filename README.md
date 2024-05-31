# Hospital Readmissions Prediction Project

## Project Overview
This project aims to develop a predictive analytics model to identify patients at high risk of readmission within 30 days of discharge from a hospital. The goal is to leverage machine learning techniques to reduce readmission rates, improve patient outcomes, and optimize hospital resources.

## Dataset
The dataset used in this project includes information about hospital readmissions, patient demographics, clinical data, and previous readmission records. Key features include:
- `Facility Name`
- `Facility ID`
- `State`
- `Measure Name`
- `Number of Discharges`
- `Excess Readmission Ratio`
- `Predicted Readmission Rate`
- `Expected Readmission Rate`
- `Number of Readmissions`
- `Start Date`
- `End Date`

## Data Cleaning
The dataset was cleaned by handling missing values and ensuring data consistency. We used the following steps:
- Imputed missing values using the median strategy.
- Ensured consistency in categorical variables like diagnosis codes and treatment categories.

## Feature Engineering
New features were created to enhance the predictive power of the model:
- `Length of Stay`: Calculated as the difference between `End Date` and `Start Date`.
- One-hot encoding was applied to categorical variables.

## Exploratory Data Analysis (EDA)
I performed EDA to gain insights into the data distribution and relationships between variables. Key visualizations include:

### Histograms of Numerical Variables
![Histograms of Numerical Variables](https://github.com/Yaman-Shadid/Predictive-Analytics-for-Hospital-Readmissions/blob/main/Visualizations/EDA/Histograms%20of%20numerical%20Variables.png)

- **Number of Discharges**: Shows distribution across facilities, revealing most have moderate discharges with some outliers.
- **Excess Readmission Ratio**: Displays the spread of readmission ratios, highlighting most facilities cluster around a central value with some outliers.
- **Predicted Readmission Rate**: Highlights predicted readmission rates, showing a reasonable distribution, suggesting the model captures variability well.
- **Expected Readmission Rate**: Shows expected rates based on benchmarks, aligning with predicted rates and supporting model accuracy.
- **Number of Readmissions**: Distribution of readmissions, indicating variability in patient management effectiveness across facilities.
- **Length of Stay**: Represents hospital stay lengths, showing most patients have short stays, useful for understanding readmission risks.

### Correlation Heatmap of Selected Features
![Correlation Heatmap of Selected Features](https://github.com/Yaman-Shadid/Predictive-Analytics-for-Hospital-Readmissions/blob/main/Visualizations/EDA/Correlation%20Heatmap%20of%20Selected%20Features.png)

- **Correlation Heatmap**: Identifies strong correlations between features like Length of Stay and Number of Readmissions, guiding feature selection for modeling.

## Modeling
Two regression models were built to predict the `Excess Readmission Ratio`:
- Random Forest Regressor
- Gradient Boosting Regressor

### Model Performance Comparison
The models were evaluated using Mean Absolute Error (MAE), Mean Squared Error (MSE), and R-squared (R²).

![Model Performance Comparison](https://github.com/Yaman-Shadid/Predictive-Analytics-for-Hospital-Readmissions/blob/main/Visualizations/End%20visualizations/Model%20Performance%20Comparison.png)

- **Model Performance Comparison**: Compares Random Forest and Gradient Boosting models, showing Random Forest outperforms with an R² of 0.99.

### Feature Importance
The importance of different features was analyzed using the Random Forest Regressor.

![Feature Importances - Random Forest Regressor](https://github.com/Yaman-Shadid/Predictive-Analytics-for-Hospital-Readmissions/blob/main/Visualizations/End%20visualizations/Feature%20Importances%20-%20Random%20Forest%20Regressor.png)

- **Feature Importance (Random Forest Regressor)**: Highlights key predictors like Predicted and Expected Readmission Rates, indicating their critical role in predictions.

### Actual vs. Predicted Values
The scatter plot shows the relationship between the actual and predicted readmission rates for the best-performing model.

![Actual vs. Predicted Excess Readmission Ratio - Random Forest Regressor](https://github.com/Yaman-Shadid/Predictive-Analytics-for-Hospital-Readmissions/blob/main/Visualizations/End%20visualizations/Actual%20vs.%20Predicted%20Excess%20Readmission%20Ratio%20-%20Random%20Forest%20Regressor.png)

- **Actual vs. Predicted Values**: Visualizes the accuracy of Random Forest predictions, showing strong alignment with actual readmission rates.

## Recommendations
Based on the analysis, I recommend the following:
1. **Focus on Key Predictors**: Monitor `Predicted Readmission Rate` and `Expected Readmission Rate` closely to identify high-risk patients.
2. **Interventions for High-Risk Patients**: Implement targeted interventions such as follow-up appointments, patient education, and home visits for patients with high predicted readmission rates.
3. **Policy Changes**: Develop policies to improve patient management and care transitions, aiming to lower the predicted and expected readmission rates.
4. **Continuous Monitoring**: Use the model to continuously monitor patient readmission risks and adjust care plans accordingly.

## Conclusion
This project successfully developed a predictive model for hospital readmissions using comprehensive data analysis and advanced machine-learning techniques. The Random Forest Regressor performed exceptionally well, identifying key predictors like Predicted and Expected Readmission Rates. The insights gained from exploratory data analysis and feature engineering highlight the factors influencing readmission rates. These findings can help healthcare providers implement targeted interventions and policy changes, ultimately reducing readmission rates, improving patient outcomes, and optimizing resource allocation.

## Additional Information Regarding Dataset

In October 2012, CMS began reducing Medicare payments for subsection(d) hospitals with excess readmissions under the Hospital Readmissions Reduction Program (HRRP).

Excess readmissions are measured by a ratio, calculated by dividing a hospital's predicted rate of readmissions for heart attack (AMI), heart failure (HF), pneumonia, chronic obstructive pulmonary disease (COPD), hip/knee replacement (THA/TKA), and coronary artery bypass graft surgery (CABG) by the expected rate of readmissions, based on an average hospital with similar patients.

**Source:** [CMS Hospital Readmissions Reduction Program](https://data.cms.gov/provider-data/dataset/9n3s-kdb3#data-table)

**About this resource:**

- Rows: 18774
- Columns: 12
- File Size: 2 MB

Additional information:
- **Modified:** January 8, 2024
- **Released:** April 24, 2024
- **Issued:** December 10, 2020
- **Publisher:** Centers for Medicare & Medicaid Services (CMS)
- **Identifier:** 9n3s-kdb3
- **Contact:** Hospital Compare
- **Contact URL:** [CMS Quality Support](https://cmsqualitysupport.servicenowservices.com/qnet_qa)
- **Public Access Level:** public
- **Homepage URL:** [CMS Data](https://data.cms.gov/provider-data/dataset/9n3s-kdb3)
