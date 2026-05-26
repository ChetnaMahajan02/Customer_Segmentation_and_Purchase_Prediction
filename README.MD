### CUSTOMER SEGMENTATION & PURCHASE BEHAVIOUR

* Undestanding customer behaviour better to personalise marketing campaigns and predict future purchases for an e-commerce comapny

* A customer transation dataset containing customer demographics and purchase history has been provided

### Methodology

* Data cleaning: 
- Handling the missing values by filling the numerical values with median and categorical values with mode.  
- Duplicate rows removed

* Basic Exploratory analysis:
- studied the distribution of gender, membership type high value customer which shows that vmembership type is a strong predictor of total spend
- the presence of extreme outliers makes it important to scale the data before clusterring

#### Customer segmentation using Clusterring
* prepared the data by selecting the numerical features
* applied standard scaling to normalise all selected features
* determined optimal number of clusters using k-means clusterring
* applied k-means clusterring with otimal k=4 on numerical features and then on original dataframe
_____________________________________________________________________________________________________
  - Cluster 0 represents low spending customers with lower average income.
  - Cluster 1 represents low spending customers with lower number of transactions, average transaction value and less number of visits.
  - Cluster 2 represents moderate spending customers with high engagement in num_visits and number of transactions.
  - Cluster 3 represents premium customers with high total spend.

#### Predictive Modelling
*  Feature engineering: Added two new feaures 'spend_per_visit' and 'discount_percentage' to understand customer behaviour.
* Prepared the data for modelling by selecting and the X & Y (High value customer) variable and split the data into training (80%) and split (20%) sets using random state = 42
* Applied One Hot Encoding to categorical features- gender, city_tier, membership_type
* Applied standard scaling to numerical features in training data to avoid data leakage
* Did Principal Component Analysis (PCA) for selecting most important features
_______________________________________________________________________________________________________

#### Build Classification model
* Build, fit and trained Logistic Regression model successfully
* Generated predictions on test data
* Model evaluation: 
- done using Confusion Metrix, Precision, accuracy, Recall & F1 Score
* Model Optimization:
- done using gridsearchcv with 3 fold cross validation
- best parameters were found and model was trained on best model
- evaluated the tuned model on trest data
- performancce was compared before and after tuning

#### Feature importance Analysis
* Found the top 8 most impactful features by extracting the coefficients from best model and using PCA components
* Plot a box plot to study the distribution of top 8 important features on customer segments

##### Business Recommendations
According to cluster_summary insights during clustering, Cluster 1 customers  show low total_spend, low num_transactions, low num_visits and high days_since_last_purchase.

* Recommendation:Increase customer
engagement, offer exclusive incentives, target value based recommendations and do surveys to understand their needs and reactivate their customer relationship with the brand.


As evident from Box plot between customer_segment and discount_used, Cluster 3 uses the maximum discount coupons followed by cluster 2. This is evident from their high spending and high transaction value purchases.

* Recommendation: Nurture cluster 3 customers with more loyalty pragrammes, early access to new launches and higher rewards to retain them for long term.
Also we can incentivise cluster 2 customers for more spending or upgrade them to premium services to increase their engagement and purchases.

* Recommendation: Boost engagement for Cluster 0 by increasin num_transactions and num_visits as they have less total_spend. Give reawards for repeat purchases, give personalised product suggestions, offer discounts on the products they choose if they shop more.