Case File-2:

Key Results
Best Model: Lasso (MSE: 6.6521, R²: -0.0045)

Why It Performed Best:
The Lasso model was the top performer among the models under test—Linear Regression, Ridge, and Lasso—measured by its Mean Squared Error (MSE) of 6.6521 and R² measure of -0.0045. Although the R² is negative in direction, suggesting that the model predicts a very small percentage of variance over a simple mean prediction, the MSE offers more straightforward measurement of prediction error. Lasso obtained the lowest MSE of the models and thus indicates that it made the smallest average squared errors in the test data.

The better performance of Lasso would most likely be due to its intrinsic feature selection and regularization capabilities. Lasso implements an L1 penalty, which not only reduces the smaller feature coefficients towards zero but can even set them to zero, thereby reducing model complexity and mitigating overfitting. Here in this dataset, which consists of a combination of categorical (e.g., Gender, JobRole), numerical (e.g., Age, WorkHoursPerWeek), and interaction variables (e.g., Stress_WorkHours, Sleep_Stress), Lasso would have picked and stressed the most significant predictors while removing noise. This tradeoff of meeting the training data and generalizing to new data probably accounts for its superiority over Linear Regression (MSE: 6.6939, R²: -0.0108) and Ridge (MSE: 6.6939, R²: -0.0108), which either overfit or did not adequately regularize the model. The small MSE improvement indicates that Lasso successfully adapted itself to the structure of the dataset, making it the optimal option in these circumstances.
