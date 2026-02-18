## R_Statistical-Modeling-of-Temperature-in-the-United-Kingdom-A-GAMLSS-Approach
This project performs statistical modeling and prediction of temperature patterns in the United Kingdom using atmospheric and environmental variables. The analysis identifies key temperature predictors and develops a robust predictive model using Generalized Additive Models for Location, Scale, and Shape (GAMLSS) framework.

### 📊 (a)	Perform a preliminary analysis on your data, this usually involves exploratory plots.

📝 A subset of data specific to the United Kingdom was extracted from the Wthr_data dataset.
The resulting dataset contains:

358 observations

18 variables

No missing values

The response variable is temperature (°F), ranging from 28.6°F to 91.0°F, indicating substantial variability in weather conditions. All explanatory variables are numeric.

Histogram Interpretation

The distribution shows a peak between 50°F and 55°F

Black line → Kernel density estimate (smoothed distribution)

Red dashed line → Normal distribution comparison

![Histrogram](https://github.com/Fahim0729/R_Statistical-Modeling-of-Temperature-in-the-United-Kingdom-A-GAMLSS-Approach/blob/e9e62b7fa22f008540f8cb41fdc3586119e32e1f/histogram.png)

### (b) Find an appropriate statistical model for the response variable in your data using the explanatory variables. This usually involves selecting: 
  1. an appropriate distribution for your response variable and 
  2. a selection of relevant explanatory variables to explain the response.

This section consists of two parts: first, the explanatory variables are selected based on their correlation with the response variable; then, the best model is identified to fit the data.

1️⃣ Correlation Analysis between Explanatory Variables and the Response Variable
The dataset contains 18 variables in total, of which 17 are considered explanatory variables. Initially, the correlation between each explanatory variable and the response variable (temperature) will be examined.
The dataset contains 17 explanatory variables.
To reduce overfitting:

Strongest correlations selected:

uv_index

air_quality_Ozone

humidity

Weak correlations included for comparison:

moon_illumination

cloud

Final modeling dataset:

5 explanatory variables

1 response variable (temperature)
The correlation between the response variable and all explanatory variables is shown in Figure-3.3.

![Correlation](https://github.com/Fahim0729/R_Statistical-Modeling-of-Temperature-in-the-United-Kingdom-A-GAMLSS-Approach/blob/885fdac2e490547adb080a5fff23949279277a54/Correlation.png)

2️⃣ Choosing appropriate distribution for the response variable

The following R libraries were used:

gamlss

gamlss.ggplot

pacman

The chooseDist() function identified 23 candidate distributions.
Based on AIC minimization, the best-fitting model was:

✅ Exponential Gaussian (exGAUS)

AIC: 2296.227

![Model_AIC](https://github.com/Fahim0729/R_Statistical-Modeling-of-Temperature-in-the-United-Kingdom-A-GAMLSS-Approach/blob/19381b7126905bda11fb008de64c607dfab7280b/Model_AIC.png)

### (c) Use diagnostics to check the assumptions of the model.
🧪 Model assumptions were evaluated using a worm plot.

Interpretation

Residuals lie mostly within the 95% confidence bands

No major deviations from normality

Indicates good model fit

![Worm_plot](https://github.com/Fahim0729/R_Statistical-Modeling-of-Temperature-in-the-United-Kingdom-A-GAMLSS-Approach/blob/810104434b5491457e24b75f2ad2739787521c14/Worm-Plot_exGAUS.png)


### (d) Use the model for prediction.
🔮 Prediction

A new dataset (newdt) containing 7 observations was created using the five selected predictors.

Steps:

Construct new input data

Apply predict() using the fitted GAMLSS model

Store predictions in predicted_temperature

![Create_nw_data](https://github.com/Fahim0729/R_Statistical-Modeling-of-Temperature-in-the-United-Kingdom-A-GAMLSS-Approach/blob/810104434b5491457e24b75f2ad2739787521c14/NewDataCreate.png)

![Pred|_nw_data](https://github.com/Fahim0729/R_Statistical-Modeling-of-Temperature-in-the-United-Kingdom-A-GAMLSS-Approach/blob/810104434b5491457e24b75f2ad2739787521c14/Pred_nw_data.png)




	

