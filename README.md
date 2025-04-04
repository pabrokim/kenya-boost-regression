
**Kenya Boost Regression Project**
This project investigates how well estimated and revised budgets can predict actual execution in Kenyan government ministries. By using government-published data from 2006-2018, the project aim to build a regression model that explores the relationship between budget estimates, revisions, and the actual expenditure. The analysis also aims to understand the impact of different ministries on budget execution patterns.

**Research Question**
The primary research question guiding this project is: How well do estimated and revised budgets predict actual execution? 

**Handling Missing Data**
Handling missing data effectively is crucial to ensure the accuracy of our model. Rows with missing Estimates are dropped from the dataset, as execution cannot be predicted without an initial estimate. Ror the Revised budget, missing values are filled with 0, as some projects may not undergo revisions. This also reflects a situation where no change to the original estimate occurred. For missing Executed values, which could indicate that the project is still ongoing or unexecuted, missing values are replaced with 0 to keep those rows in the analysis. This practice retains valuable information about incomplete or ongoing projects.

**Feature Engineering**
It is hypothesize that the Ministry responsible for the budget could have an impact on the execution, therefore, it is included as feature in the model. To prepare the Ministry column for analysis, any numeric prefixes (e.g., "110 Ministry of Agriculture" becomes "Ministry of Agriculture") are removed. Then, the column is converted into a categorical variable, using  one-hot encoding.

**Modeling Approach**
For the regression analysis, Estimates, Revised, and Ministry are used as features. The primary model selected is Linear Regression, as it provides a straightforward approach to understand the relationship between the variables. Additionally, regularized versions of linear regression, such as Ridge Regression and Lasso Regression help prevent overfitting and improve model generalization. These models unlocks the predictive power of the budget estimates and revisions and potential impacts of different ministries on actual budget execution.

**Evaluation Metrics**
The models are evaluated using R-squared (R²), which provide variance in execution as explained by the estimates and revisions and Mean Absolute Error (MAE) average error between predicted and actual execution.

**Expected Outcomes**
We expect that if Estimates alone can predict execution well, it would suggest that ministries generally adhere to their initial projections, regardless of revisions. If Revised budgets improve predictions, this would suggest that budget adjustments align expectations with actual outcomes. Finally, if the Ministry feature has a significant impact on the model, it would imply that certain ministries have more effective budget execution strategies than others.

**Results**
LinearRegression, Ridge, and Lasso regression were used to balance interpretability and performance. The models showed strong performance: the baseline mean absolute error (MAE) was ~79 million, but all trained models reduced this error to around ~13.7 million on the test set, with R² scores exceeding 0.95. These results suggest that both the initial estimates and revised budgets are strong predictors of final execution amounts. Moreover, Ridge and Lasso regularization had minimal impact which implied low multicollinearity and a robust signal in the predictors. This analysis highlights the reliability of government budget estimates while revealing opportunities for enhancing predictability through consistent mid-year revisions
