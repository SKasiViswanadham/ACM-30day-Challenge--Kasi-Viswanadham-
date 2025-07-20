# Main Problem
# Dirty dataset detective
# Cleaning Steps:
Data cleaning involves removing duplicate records to prevent bias, imputing missing numerical values with medians and categorical values with modes for consistency, standardizing text by converting to lowercase and mapping inconsistent labels, applying one-hot encoding to categorical variables while dropping the first category to avoid multicollinearity, and using logarithmic transformation on skewed targets like charges to stabilize variance and reduce outlier impact.

# Feature Selection Strategy: 
Mutual information (MI) regression is used to quantify feature-target dependencies, capturing linear and non-linear relationships. Features are ranked by MI scores to prioritize predictive relevance, reducing dimensionality and noise. This model-agnostic, non-parametric approach accommodates mixed data types, minimizing irrelevant variables to enhance model performance and reduce overfitting.

# Model Metrics (Before vs After Cleaning):
The R² score measures the proportion of target variance explained. Pre-cleaning data with duplicates or skewness may yield lower R² due to noise. Post-cleaning, with steps like imputation and transformation, Linear Regression achieves an R² of 0.8295, and RandomForestRegressor achieves 0.84312. Feature selection via MI (selecting all features) results in nearly identical R² scores (0.8295 for Linear Regression, 0.84315 for RandomForestRegressor), indicating minimal impact due to retained features.


# Case File-2:

# Key Results
Best Model: Lasso (MSE: 6.6521, R²: -0.0045)

Why It Performed Best:
The Lasso model was the top performer among the models under test—Linear Regression, Ridge, and Lasso—measured by its Mean Squared Error (MSE) of 6.6521 and R² measure of -0.0045. Although the R² is negative in direction, suggesting that the model predicts a very small percentage of variance over a simple mean prediction, the MSE offers more straightforward measurement of prediction error. Lasso obtained the lowest MSE of the models and thus indicates that it made the smallest average squared errors in the test data.

The better performance of Lasso would most likely be due to its intrinsic feature selection and regularization capabilities. Lasso implements an L1 penalty, which not only reduces the smaller feature coefficients towards zero but can even set them to zero, thereby reducing model complexity and mitigating overfitting. Here in this dataset, which consists of a combination of categorical (e.g., Gender, JobRole), numerical (e.g., Age, WorkHoursPerWeek), and interaction variables (e.g., Stress_WorkHours, Sleep_Stress), Lasso would have picked and stressed the most significant predictors while removing noise. This tradeoff of meeting the training data and generalizing to new data probably accounts for its superiority over Linear Regression (MSE: 6.6939, R²: -0.0108) and Ridge (MSE: 6.6939, R²: -0.0108), which either overfit or did not adequately regularize the model. The small MSE improvement indicates that Lasso successfully adapted itself to the structure of the dataset, making it the optimal option in these circumstances.



# Case File-3:
# Entire Code Explanation
- step1:Imported libraries required
- step2: use Onehot Encoding and StandardScaler to make the entire dataset look like numerical
- step3: Now divide the targeted column from the dataset and put in another variable(now there will be 2 variables X and y)
- step4: using Traintestsplit, split into two from both variables --> gets X_train_scaled, X_test_scaled, y_train, y_test
- step5: pick the models
- step6: Train the models with X_train_scaled and y_train, says that we will give the input as X_train_scaled and we are saying the model that output will be y_train
- step7: Train the model with unseen Data(X_test_scaled)
- step8: Accuracy Calculation, compare the results in between y_test and outputs from the model when the inputs are X_test_scaled
- Step9: Plot Heatmap for Confusion Matrix (Visualization)
- step10: plot ROC(Used chatgpt at this part)
# RESULTS #
- Accuracy: Logistic Regression with 98.4
- Confusion matrix: Logistic Regression, based on (F = fp + fn) F value from both 14 for Logistic and 40 for LDA.[less F --> better Performance]
- ROC Curve: Logistic Regression has a slightly better ROC-AUC score with 99.9
- overall LOGISTIC REGRESSION

# Case File-4:
# Model comparision
- Before Conditions: taking all columns into consideration while training and testing the data
- After Conditions: selecting the columns by feature selection which may affects the model efficiency and taking those columns for training and testing the model
# K-Nearest Neighbors (KNN)
- KNN relies on distance metrics (e.g., Euclidean), making it highly sensitive to irrelevant or noisy features that distort neighborhood structure.
- Feature selection reduces dimensionality and noise, leading to more accurate neighbor identification and improved predictive performance.
# Decision Tree
- Decision Trees perform intrinsic feature selection by choosing splits based on the most informative features (e.g., using Gini impurity or information gain).
- As a result, removing irrelevant features has minimal impact unless it affects important split variables.
# Random Forest
- Random Forests build multiple Decision Trees on bootstrapped data with random feature subsets, inherently reducing reliance on irrelevant features.
- Due to this ensemble strategy and internal feature sampling, external feature selection yields negligible performance gains.



