# Insurance_policy_prediction_python
## Project Description
The objective of this project is to use historical policy data to develop a multiclass predictive model that predicts the likelihood of property insurance policy cancellations. Specifically, the goal is to identify which policies are most likely to be canceled, those that can be persuaded to renew, and those most likely to be renewed.
## Data
The dataset, "Kangaroo Data," contains 1 million policy records from 2013 to 2017.
Features include various policyholder demographics, policy details, and sales information.
The target variable (cancel) has three classes:
- 0: Not canceled
- 1: May cancel but can be convinced
- 2: Canceled
### Variable Descriptions
- id: Policy ID (cannot be used in the model)
- tenure: Number of years with the insurance provider
- claim.ind: Occurrence of claim (0 = no, 1 = yes)
- n.adults: Number of adults in the property
- n.children: Number of children in the property
- ni.gender: Gender of policyholder
- ni.marital.status: Marital status of policyholder (0 = no, 1 = yes)
- premium: Price of the policy
- sales.channel: Medium through which the policy was purchased
- coverage.type: Type of coverage
- dwelling.type: Type of dwelling
- len.at.res: Length at residence
- credit: Financial credit level of policyholder
- house.color: Color of the house
- ni.age: Age of the policyholder
- year: Year of the policy
- zip.code: Zip code of the property
- cancel: Cancellation indicator (0 = not cancel, 1 = may cancel, 2 = cancel)

## Preprocessing Steps
1. **Data Cleaning**: Handled missing values using the mean for continuous variables and mode for categorical variables.
2. **Outlier Detection**: Removed unrealistic values, such as ni.age > 130.
3. **Feature Encoding**: Applied `LabelEncoder` to convert categorical features to numerical values.
4. **Normalization**: Used `MinMaxScaler` to normalize feature values to a range of [0, 1].
5. **Handling Imbalanced Classes**: Utilized `RandomOverSampler` to balance the dataset.

## Modeling
Explored multiple classifiers, including:
- Decision Tree
- Random Forest
- Gradient Boosting
- Logistic Regression
- K-Nearest Neighbors
- Naive Bayes
- AdaBoost
- Bagging Classifier
- Multi-layer Perceptron

**Final Model**: The **Random Forest Classifier** provided the best performance based on the weighted F1-score.

## Evaluation Metrics
- The Random Forest Classifier achieved a notable F1 score of 0.84 on the test dataset, indicating strong predictive performance. 

## Model Interpretability
1. **Permutation Importance**: Identified the top 5 influential features:
   - credit
   - sales.channel
   - zip.code
   - year
   - ni.age
2. **Partial Dependence Plots (PDP)**: Visualized the impact of the top features on policy cancellation.

## Business Insights & Recommendations
1. **Credit Score**: Customers with lower credit scores are more likely to cancel. Focus marketing efforts on customers with higher credit scores.
2. **Customer Tenure**: Longer tenure correlates with lower cancellation rates. Implement loyalty programs to retain customers.
3. **Age Factor**: Younger customers are more likely to cancel. Adjust marketing and product offerings to better appeal to this demographic.
4. **Sales Channel**: Policies sold through brokers have lower cancellation rates. Increase broker partnerships and provide incentives to brokers.


