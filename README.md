# Linear Regression on Fifa Dataset


## Getting Started

Pandas, Numpy, Sklearn, Seaborn, Scipy and Matplotlib are essentials


## Summary

Based on [Sklearn](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html) documentation **Linear Regression** fits a linear model with coefficients w = (w1, …, wp) to minimize the residual sum of squares between the observed targets in the dataset, and the targets predicted by the linear approximation. Hence the project tries to predict **Overall** rating of football players in video game Fifa19 and import independent features while predicting our dependent variable

After importing and cleaning data (excluding Goalkeepers as they have different skills, handling dtypes and NaNs), the workbook starts with some visualization based on nationatilities count of players (first 80 countries) there we can see England, Germany, Spain, Argetina and France are top 5 countries of players.The workbook then shows the players with highest values across whole columns.

The **heatmap** shows us the correlated the columns and we check lineplot of Overall with Value and Wage. As you can imagine especially Value and Wage are not normally distributed and similary to whole income indicators they are **right skewed** (Positive Skewness and +3 Kurtosis). In preprocessing part these columns were applied [**log transformation**](https://medium.com/@kyawsawhtoon/log-transformation-purpose-and-interpretation-9444b4b049c9#:~:text=Log%20transformation%20is%20a%20data,on%20the%20natural%20log%20transformation.)

After the transformation of Value and Wage the aim was to diminish the **multicollinearity** thereby the columns which were highly correlated with each other and also correlated(>0.60) with Overall has been dropped and **pairplot** has been applied. The difference between two describe of the dataframes were clear.

In modelling part firstly only numerical independent variables have been added in modelling and 20% of the data has been splitted for testing purposes. Our first R-square was 0.88 and after **Recursive Feature Elimination** has been applied, the model demonstrated that Age,Potential and Stamina are 3 important features for Overall. **Residuals Plot**, **Regression Plot** and **Barplot for Feature Importance** handled the visualization part of the model.

In modelling vol.2 categorical variables have been added as well. First categorical variable was the **positions** of the players and they have been simplified as defender,defensive midfielder, midfielder, attacking midfielder and striker. Second variable was the **preffered foot** of the players. **OneHotEncoder** have been applied in order to place them in the model. After adding categorical variables R-square was 0.88 and with **RFE** it has been revealed that instead of Stamina being Striker has more importance in Overall Rating. The first 3 important features were Age, Potential and x0_ST.


Last part the whole modelling, codes were being merged with a function. Comments inside of the function are vital and need to be read before running.

def linreg(y,ylabel="Overall",df=fifa,corr=0.60,categorical=False,rfe=False):

- y: choose the dependent variable in your fifa dataset
- ylabel: choose how you are going to name your dependent variable
- df: This is default **fifa** dataset
- categorical: True if you want to add categorical variables (Preferred Foot and Positions)
- rfe: True if you want to apply backward elimination. Number of features are 3


##### To do(s)
- adding also data cleaning part inside of a function thereby choosing a different dependent variable would be an option
- wrangling data run for logistic regression


###### Contact

[LinkedIn](https://www.linkedin.com/in/caner-bulut-48a0784a/)