# Analysis of Housing Data in Ames, Iowa 📈

The housing market is always fluctuating and it is paramount to have a reliable model to depend on. During this presentation we will be looking at the data regarding sale prices for housing in Ames, Iowa. The goal is create a supervised machine learning model that can accurately predict the sales price for a property. The original data included 80 independent variables that could be used to create our model and predict the dependent variable, sales prices.

**Four supervised machine learning models will be utilized: Linear Regression, Polynomial Regression, Ridge Regression, and LASSO Regression**. Linear regression assumes a linear relationship between the independent variables and target variable with the goal of finding the best-fitting line that minimizes difference between actual and predicted values. Polynomial regression is an extension of the linear regression model but allows for non-linear relationships that involves fitting a polynomial equation to the data instead of a straight line (quadratic, cubic) with the goal for more complex models to be modeled. Ridge regression is used in linear regression to address multicollinearity (high correlation) in the independent variables, adding a penalty term, L2, regularization term, to the objective function, shrinking the coefficients towards zero to help reduce overfitting from the highly correlated variables. LASS regression is similar to ridge regression, where it adds a penalty term, L1 regularization, that shrinks coefficients to zero and performs feature selection (reduces noises)

In order to identify whether the model is a success or not, we will be evaluating their respective R2 scores, where the closer the score is to 1, the more successful the model will be with its performance. A higher R2 score indicates that a large proportion of the variance in the dependent variable is explained by the independent variable

# Modeling
- **Linear Regression Model:** 
    - Utilized histograms, heatmap, and pairplots to determine which independent variables to use for my model. LINE assumptions plot exhibited homoskedastic variance meaning, the residuals have a constant variance and assumptions of linear regression are met
    - Independent variables: ```'overall_qual', 'exter_qual', 'gr_liv_area', 'kitchen_qual',
       'garage_area', 'total_bsmt_sf', '1st_flr_sf', 'bsmt_qual', 'year_built',
       'garage_finish', 'year_remod/add', 'full_bath', 'foundation_PConc',
       'totrms_abvgrd', 'mas_vnr_area', 'saleprice', 'overall_qual_exter_qual',
       'gr_liv_area_garage_area', 'total_bsmt_sf_1st_flr_sf',
       'bsmt_qual_garage_finish', 'year_built_year_remod/add'```
    - Train R2 score: 0.878
    - Test R2 score: 0.840
    - *Interpretation:* 84% of the variation in Sale Price can be explained by the independent variables for testing data
- **Polynomial Regression Model:**
    - Same independent variables utilized
    - Training R2: 0.941
    - Testing R2: 0.244
    - *Interpretation:* The training R2 shows that the polynomial regression explains ~94% of the variance in Sale Price, while the testing R2 shows that the polynomial regression explains ~24% of the variance in unseen data, which is poor. Polynomial Regression model is overfitting the training data, overly complex
- **Ridge Regression Model:** 
    - Same independent variables utilized
    - Train ridge R2 score: 0.895
    - Test ridge R2 score: 0.858
    - *Interpretation:* Train R2 score explains ~89.5% of the variance in the sale price while test R2 score explains ~85.8% of the variance in the sale price. The Ridge Regression Model is not overfitting and is robust and reliable in making predictions
- **LASSO Regression Model:**
    - Same independent variables utilized
    - Train lasso R2 score: 0.886
    - Test lasso R2 score: 0.857
    - *Interpretation:* Train R2 score explains ~88.5% of the variance in the sale price while test R2 score explains ~85.7% of the variance in the sale price. Lasso Regression Model is not overfitting and is robust and reliable in making predictions
    
# Visualizations
- Chose the 4 variables with the highest coefficients to make plots on while taking a look at the neighborhoods these properties reside in
    - Variables chosen: 
        - overall_qual .15
        - gr_liv_area .12
        - year_built 3.2
        - year_remod/add 2.1
    
# Data Dictionary
https://jse.amstat.org/v19n3/decock/DataDocumentation.txt
- Dummy data contains the prefix of the variable used that is provided in the link for the data dictionary

# Executive Summary
The goal was to create a supervised machine learning model that accurately predicted the sale price of properties sold in Ames, Iowa with our success indicator being the R2 score for our models. 

**The R2 score with the highest score suggests that Ridge Regression is best at predicting sale price** with Lasso regression being next (.001), Linear regression after then, and Polynomial regression being last.

# Recommendations
- For corporations wanting to list houses onto the market, I would be best to utilize Ridge Regression Models for accurately predicting the Sale Price of a home
- For sellers, it is best to consider the overall quality and remodel date to get the most bang for your buck
- For buyers wanting a house or an investment, it is best to look into the year_built along with the location of the property. The northern part of Ames is developing and prices increase as the years go by in the more developing parts of the city
- Model could be generalized universally but more recent data from Ames would be needed, perhaps another major city like Des Moines would make the model even more robust with better accuracy
