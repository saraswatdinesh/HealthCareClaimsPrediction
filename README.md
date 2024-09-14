# HealthCareClaimsPrediction
Predicting Claims based on the existing preconditions and their categories for the patients of a certain age and previous year claims amounts.

# Goal  - 
As the name suggests, this project aims to build a model that could predict the claims amount for the upcoming year for the patients whose historical data was available with the healthcare company. This would enable healthcare companies to position the insurance premiums based on the amount of the expected claim to better offset the margins and help reduce the amount of the claim by targeting the patients who are high risk.

# Approach -
Load the training data and do the exploratory analysis to understand the importance of certain features such as Age, Preconditions, Preconditions categories, previous year claims, and Sex to the Total Claims amount for each patient ID. 

Post EDA it can be attributed that Preconditions count as well as people with more than one preconditions of level 4 have mean average claims much higher than the rest of the people. 

Also, age data has to be scaled so it does not influence the prediction outcome significantly. 

Looking at the categorical columns and numerical columns such as claims, and age. LGBMRegressor seemed a very good choice to predict the prices. 

Created a study to identify the best parameters based on the minimum RMSE on validation data and then trained the model on the full data before predicting the claims on the unseen data. 

# Outcome

We were able to predict the outcome with the RMSE of **952** approx which means that the amount of the claims can be predicted with the accuracy of around **$1000** on average provided the data is not far from the data on which it has been trained on. 

# Next Steps -

Further feature engineer the variables that impact the claims amount especially the previous year's claims as certain people are new to the healthcare systems and the claims amount was 0 for such patients, which I believe will be an outlier and impact its performance. 
