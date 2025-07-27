# 

# Accuracy:
~0.79 (79% correct predictions).
# Confusion Matrix: 
- Heatmap showing:
  -  True Negatives/Positives (correct predictions).
  -  False Negatives/Positives (misclassifications).
  -  Example (approximate):
  -  Negative: ~113,500 correct, ~45,994 misclassified as Positive.
  -  Positive: ~129,000 correct, ~30,506 misclassified as Negative.
# Write-Up:
# Model Choice:
Logistic Regression chosen for simplicity, efficiency, and good performance with sparse text data.
# TF-IDF Role: 
Converts text to numbers, emphasizes important words, reduces noise by limiting vocabulary.
# Challenges and Solutions:
- Large dataset: Limited TF-IDF to 5,000 features to manage memory.
- No Neutral labels: Adapted by mapping only Negative/Positive.
  Noisy text: Cleaned with regex to remove URLs, mentions, etc.
- Model convergence: Set max_iter=1000 for Logistic Regression.
- Balanced simplicity/performance: Chose Logistic Regression over complex models like XGBoost.


# Phase-2
### EXPLANATION
- step 1: import libraries
- step 2: load dataset
- step 3: Data Preprocessing and seperating target from the dataset
- step 4: Scaling is essential for models that use distances, gradients, or feature variance. Without it, models may become slow, unstable, or inaccurate
  - SVM rely on Distance
  - ex. If one feature has a large scale (e.g., "income in thousands"), it will dominate the distance calculation and affect model performance.
  - Without scaling, PCA gives more importance to high-scale features, leading to biased components.
- step 5: These two principal components together explain only about 12.1% of the total information (variance) present in your original dataset.
- step 6: traintestsplit and train the model

### UNDERSTANDINGS
- Since, the logistic Regression accuracy is:
  - If accuracy is high, the data may be linearly separable.
  - If accuracy is low, the data may need a non-linear model.
- According to our data it is 0.9991573235277963. So, it is linearly separable.
- This is the reason both kernels have same accuracy.
- rbf also works well but the work will complete at the linear kernel itself.

### Meanings
- Linear Kernel: Assumes data is linearly separable and finds a straight line (or hyperplane) to separate the classes.
- RBF (Radial Basis Function) Kernel: Maps data into infinite dimensions to handle non-linear relationships using Gaussian functions.
- Polynomial Kernel: Models complex non-linear patterns by fitting polynomial decision boundaries of specified degree.
- PCA (Principal Component Analysis): Reduces dimensionality by projecting data onto directions (components) that capture the most variance.


# Phase-3
### Explanation
- Fig plots, are made by using combinations, each by choosing one element at x axis and another at y axis
- to plot the data on the graph we used pca becuse we cant project the the multifeature data on the 3d axis
- And using elbow method we found out the number of clusters required
- Same with Hierarchical Clustering, but clusters are choosen based on the distance

- Gene Seperation,coustmer Segregation, AD recomendation, plant classification etc


