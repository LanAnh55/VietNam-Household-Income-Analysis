# VietNam-Household-Income-Analysis

Factors Affecting Household Income in the Northern Midlands and Mountains in Vietnam

**Overview**
This project analyzes the factors influencing household income in the Northern Midlands and Mountains of Vietnam. Using a dataset of 7,417 households across 14 provinces, I apply Ordinary Least Squares (OLS) regression in Stata to assess the impact of key socioeconomic factors.

***Key Variables***:
Explanatory: Age, education, gender, marital status, ethnicity, household size, land types, urban/rural classification.

Dependent: Household income per capita (log-transformed).

**Goal of this notebook**

1. Analyze the proportional income differences among groups
2. Compare income differences between provinces
3. Assess how different types of land (annual cropland, perennial cropland, forestland, garden land) affect household income
4. Use standardized coefficients to compare the relative influence of each independent variable on income
5. Test the alternative hypothesis that the effect of education on income
6. Analyze the quadratic relationship between age and income
   
**Methodology: Ordinary Least Squares (OLS) Regression**
The model is defined as: 
![image](https://github.com/user-attachments/assets/fd918d89-a6f1-4e36-9b14-3ccc3f1da604)

**OLS Assumptions and Tests**
Linearity in Parameters: Our model satisfied this assumption.

Random Sampling: The data is a random sample drawn from the population. It means that every member of the population has an equal chance of being selected for the sample.

No Perfect Multicollinearity: All VIF values below 10 as a rule of thumb, indicating that the regression model has no perfect multicollinearity and the coefficient estimates are considered reliable.

![image](https://github.com/user-attachments/assets/2670676d-03c9-4012-8882-4030195e2668)


Zero Conditional Mean: To detect whether our model is violating variable omission errors, we conducted the Ramsey reset test.
![image](https://github.com/user-attachments/assets/92b5a657-b315-446e-8158-6575bcb68017)


p-value of 0.0000 means that the result is statistically significant -> Reject H0

Homoscedasticity: The homogeneity of variance (homoscedasticity) assumption in the regression model's error terms is tested using the Breusch-Pagan/Cook-Weisberg test.
The model meets Heteroscedasticity. After that, I used Log transformation to adjust for heteroskedasticity in this model.

![image](https://github.com/user-attachments/assets/988f4d0d-050e-48c9-a7c8-dd2ab4815e4f)


p-value = 0.4758 > 0.05 -> do not reject H0

The new model does not violate the assumption of heteroscedasticity, indicating that the model has more precisely and successfully addressed the issue.

Normality: Residuals should follow a normal distribution with zero mean and constant standard deviation. I used Q-Q plots to test the model.
![image](https://github.com/user-attachments/assets/2d004adb-c275-4eb7-a018-8d924ea78f39)


The plot shows that the model satisfies the above assumption.

Key Findings
The proportional income differences among groups: Kinh households in urban areas earn the most, with income levels 55% higher than ethnic minority households in rural areas. These results underline how both ethnicity and location together affect income, suggesting that specific policies are needed to reduce these income differences.
Compare income differences between provinces: The results show a clear differentiation in household Income in the Northern Midlands and Mountains in Vietnam. This may reflect the disparity in economic development and living conditions between regions.
Controlling for other factors, there are differences in income when comparing households living in Ha Giang (base group) with households living in other provinces.

Higher than Ha Giang: Tuyen Quang (6.41%), Lao Cai (6.86%), Bac Giang (20.2%)
Lower than Ha Giang: Cao Bang (20.4%), Bac Kan (14.09%), Dien Bien (15.82%), Son La (19.1%), Phu Tho (9.85%)
Different types of land (annual cropland, perennial cropland, forestland, garden land) affect household income
Annual cropland: A 1% increase reduces income by 3.43%.
Perennial cropland: A 1% increase raises income by 0.2%.
Forestland: A 1% increase decreases income by 0.3%.
Garden land: A 1% increase raises income by 0.01%.
The relative influence of each independent variable on income: Education and ethnicity are the primary drivers of income, while higher dependency ratios reduce earnings potential.

The effect of education on income: Education increases income by more than 5%.

Analyze the quadratic relationship between age and income: Income increases with age, peaking at 60 years, then declines.

THE END.
