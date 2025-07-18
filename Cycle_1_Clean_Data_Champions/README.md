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
