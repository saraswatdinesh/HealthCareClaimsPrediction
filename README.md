# HealthCare Claims Prediction: Data-Driven Insights for Smarter Insurance Premiums

![Healthcare Claims image](https://github.com/user-attachments/assets/5e270d27-0b2b-47bd-ad13-d42ccf319d0a)

## Project Overview

Healthcare is increasingly data-driven, and predictive analytics play a crucial role in helping organizations make informed decisions. In this project, we set out to develop a predictive model that estimates healthcare claims for the upcoming year. By leveraging historical patient data, including preconditions, age, and prior claims amounts, we aim to help healthcare companies better align their insurance premiums and mitigate risks associated with high claim amounts.

## Key Objective

The central goal of this initiative is to build a reliable model that accurately predicts the claims amount for patients based on their pre-existing conditions and historical data. This would enable healthcare providers to adjust insurance premiums dynamically, balancing their financial risks while offering more targeted interventions for high-risk patients.

## Analytical Approach

**1. Data Loading and Exploration**
We began by loading the dataset containing patient information, such as:

Age
Number of preconditions
Categories of preconditions
Total claims from the previous year
Gender (Sex)
Before diving into predictive modeling, we conducted an **Exploratory Data Analysis (EDA)** to identify patterns, correlations, and trends in the data.

**2. Feature Importance Insights**
Through EDA, several key insights emerged:

**Preconditions Matter:** Patients with preconditions at level 4 and beyond show higher mean claims amount wrt to lower levels.

![Screenshot 2024-09-14 at 7 20 22 PM](https://github.com/user-attachments/assets/ac74ee6d-0913-4f82-ae63-095e42108432)

patients with a higher number of existing preconditions have higher mean claims amounts.

![Screenshot 2024-09-14 at 7 18 44 PM](https://github.com/user-attachments/assets/f32b452f-05ca-4e8d-adbd-cee52fbb8ab8)

**Critical Preconditions Matter:** Patients with more than one high-level precondition (Level 4) had significantly higher average claims than others.

![Screenshot 2024-09-14 at 7 19 38 PM](https://github.com/user-attachments/assets/0cdc86c4-feb3-4d2c-b7fe-68de7c02b561)


**Age Needs Scaling:** Age had a wide range of values, and we scaled this variable to avoid it disproportionately influencing the model’s predictions.
**Claims History:** Unsurprisingly, previous claims amounts played a vital role in predicting future claims. Patients with higher claims in the past were more likely to generate larger claims in the upcoming year.

**3. Choosing the Right Model**
Given the mix of **categorical** and **numerical** features (e.g., precondition categories, claims history, age), we opted for the **LGBMRegressor**. This choice was driven by its effectiveness in handling complex datasets with a combination of feature types.

We also performed **hyperparameter optimization** using a study to find the best model parameters, minimizing the **Root Mean Square Error (RMSE)** on validation data.

**4. Training and Validation**
After selecting the optimal parameters, we trained the model on the full dataset and tested its performance on unseen data. The results were promising.

## Model Performance: Results at a Glance

The model achieved an **RMSE of 952**, meaning the predicted claims were on average within **$1000** of the actual amounts. While not perfect, this level of accuracy provides a strong baseline for healthcare companies to make more informed decisions on premiums and interventions.

Given that the claims data closely resembled the training data, the model demonstrated reliable performance, but further improvements could enhance its robustness.

# Next Steps: Enhancing Predictive Power

**1. Addressing Outliers and New Patients**
One key challenge was dealing with patients who were new to the healthcare system, resulting in 0 claims from the previous year. These entries were likely outliers and impacted the model’s performance. Moving forward, we plan to engineer more sophisticated features to handle such cases better, ensuring that our model can accommodate new patients or those with limited historical data.

**2. Feature Engineering for Claims History**
We also aim to develop more granular features around the previous year’s claims. For instance, clustering patients based on their claims trajectory or creating interaction terms between preconditions and age could further refine predictions.

**3. Expanding the Model to Additional Patient Segments**
While this iteration of the model focused on a specific subset of patients, we see potential in expanding it to broader segments. Incorporating external factors like geographic location, lifestyle data, and socioeconomic variables could enhance prediction accuracy even more.

## Conclusion

By predicting claims with a high level of accuracy, we are empowering healthcare companies to make smarter, data-backed decisions. With continuous refinement, this model can evolve into a critical tool for managing premiums, identifying high-risk patients early, and optimizing healthcare interventions.

The journey doesn't stop here. With further improvements and the incorporation of advanced features, the predictive model has the potential to transform how healthcare companies balance risk and reward in their insurance products, making healthcare more sustainable for all stakeholders.
