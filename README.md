Loaded the cirrhosis dataset containing 418 patients, 17 clinical features, survival outcomes, and metadata columns such as ID and follow-up days.

Performed exploratory data analysis and identified that nine clinical features had 106 simultaneous missing entries from rows 313–418, indicating systematic missingness.

Removed the 106 affected rows, reducing the dataset to 312 complete and reliable records.

Handled remaining missing values by converting Age to years, applying mean or median imputation to numeric features based on distribution, and mode imputation to categorical features.

Split the cleaned dataset into a stratified training set (80%) and test set (20%) to preserve class proportions.

Identified feature types, separating continuous clinical measurements and categorical attributes such as Drug, Sex, Ascites, Hepatomegaly, and Spiders.

Encoded all categorical variables, using binary encoding for Sex and one-hot encoding for the others, resulting in 24 total features.

Standardized continuous variables using z-score normalization to ensure comparability across algorithms.

Checked target distribution and observed severe class imbalance, particularly the low frequency of the transplant class.

Trained three machine learning models—Logistic Regression, Random Forest, and SVM—using stratified 5-fold cross-validation with macro F1-score as the evaluation metric.

Identified model behavior before tuning, noting Random Forest overfitted, SVM underfitted, and Logistic Regression showed the best generalization.

Applied hyperparameter tuning via GridSearchCV to optimize C, penalty type, tree depth, number of estimators, and SVM kernel parameters.

Addressed class imbalance by comparing SMOTE, SMOTEENN, and ADASYN, with SMOTEENN producing the best performance when paired with Logistic Regression.

Selected the final model, Logistic Regression with SMOTEENN, achieving macro F1-score of 0.598 and accuracy of 0.73 on the test set.

Analyzed feature importance, where Age and Bilirubin consistently emerged as the top predictors across linear and nonlinear models.
