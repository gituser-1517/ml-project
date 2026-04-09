**Problem Statement**

You are a junior data analyst at a retail company. Your manager hands you a dataset of past customer orders and asks you to build a model that predicts whether a 
customer will make a repeat purchase within 30 days.

The dataset contains the following columns:

**Column**	                          **Description**

customer_id	                      Unique customer identifier
order_count_last_90d	            Number of orders placed in the last 90 days
avg_order_value	                  Average order value in INR
days_since_last_order	            Days elapsed since the customer's most recent order
repeat_purchase_flag	            1 if the customer made a repeat purchase within 30 days, 0 otherwise
discount_used_on_repeat_order	    Discount applied on the repeat purchase order


**Task 1 Question**

Identify which column in the dataset is the label, and which column, if included as a feature, would introduce data leakage. For each, write one sentence 
justifying your choice.

**Task1 Answer**

repeat_purchase_flag - This column is the label. As the model need to predict whether customer will make a repeat purchase within 30 days, this column will be the
label for the model.

discount_used_on_repeat_order - If this column is included in feature it would introduct data leakage. This discount is applied based on the repeat purchase/order 
which is the label the model tries to predict. Hence if the discount_used_on_repeat_order exists in the feature, it can force the lable to derive prediction from this 
feature.



**Task 2 Question**

Your manager skips straight to training a gradient boosting model. Suggest two steps from the complete ML workflow that should have been completed first, 
and briefly explain why each step matters before jumping to a complex model.


**Task2 Answer**

Before start training a ML model, following basic ML workflow need to taken care first:

1. Problem Framing - Identifying the business case.
2. Features & Labels - Identifying the input features and the output label to be predicted
3. Data Split - Split the data for training, testing and validation
4. Baseline - Set the manual baseline to compare with model prediction

Detailed ML workflow is mentioned below for reference.

1. Problem Framing        → Define what is being predicted and how success is measured
2. Data Auditing          → Assess data quality, check for ethical and privacy concerns
3. Feature Engineering    → Transform raw inputs into meaningful signals
4. Data Splitting         → Separate data into train, validation, and test sets
5. Baseline Model         → Establish minimum acceptable performance
6. Model Training         → Train the ML model on the training set
7. Validation & Tuning    → Evaluate on validation set, adjust to reduce overfitting
8. Final Testing          → Report honest performance on the held-out test set
9. Deployment             → Move the model into production
10. Monitoring            → Track performance over time as real-world data evolves
