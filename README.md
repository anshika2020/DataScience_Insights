# DataScience_Insights

# Project 1 : Will the Customer Accept the Coupon?
# Goal: This project aims to use what you know about visualizations and probability distributions to distinguish between customers who accepted a driving coupon versus those who did not.


Step#1: Review the coupon dataset and investigate the dataset for missing or problematic data
     a. missing_data_count1 = data.isnull().sum()

Step#2: Data Cleanup Steps: After reviewing the dataset, I gathered that:

    a. missing_data_removed = data.replace(to_replace=[None, 'None', ''], value='NaN', inplace=False) 
    missing_data_count2 = missing_data_removed.isnull().sum()
    1. The values "less1" and "never" essentially mean 0 and can be replaced by 0
    2. The value gt8, 50plus, below21 can be replaced by 8+, 50+, <21 respectively
    3. The car value is null for 12577 records and I decided to replace it by "Unknown" instead of dropping car column as it is needed for the data analysis later.
    4. There are NaN values of Bar, CoffeeHouse, CarryAway, RestaurantLessThan20, and Restaurant20To50 columns too. I decided to to replace them by "Unknown" as well.
    5. A few column names can be renamed for better readability.
    
Step#3: Investigate the Bar Coupons

    Below are the hypotheses based on the observations:
    Hypothesis 1: The drivers who received bar coupons and accepted them, visiting the bar more than once a month, neither have kids nor are widowed. 
    Hypothesis 2:  Drivers below the age of 30 are also visiting bars, but their frequency is not as high as drivers who have either partners or friends. 
    Hypothesis 3: I also noticed that the frequency increases to the cheapest restaurants for those with incomes less than $50k. They tend to visit frequently as they also accept the coupons at a high rate.
    
Step#4: Using the bar coupon example as motivation, you are to explore one of the other coupon groups and try to determine the      characteristics of passengers who accept the coupons.  

    Hypothesis 1: The drivers who received coffee house coupons and accepted them, visiting the bar more than once a month, have no kids 
    Hypothesis 2:  Drivers below the age of 30 are also visiting bars, but their frequency is not as high as drivers who have either partners or friends. 
    Hypothesis 3: I also noticed that the frequency increases to the cheapest restaurants for those with incomes less than $50k. The trend shows that people whoo earn less than 50k tend to visit less frequent than other two groups which have no kids and are below the age 30.

 Findings :
 
    These findings provide insights into the characteristics of passengers who accept different types of coupons, helping in understanding consumer behavior and optimizing marketing strategies for targeted promotions.





#Project 2: Understand what factors make a car more or less expensive. As a result of your analysis, provide clear recommendations to your client -- a used car dealership -- as to what consumers value in a used car.

Step #1: Business Understanding This research assignment uses a vehicle dataset and analyses the data using different model. I followed the CRISP-DM methodology for the data analysis.

Step #2 - 3: Data Understanding and preparation I used the following steps to understand the vehicles dataset:

Executed Dataframe.info() to get the list of columns, number of rows etc
Removed null values from the dataframe.
Used different barplots and countplots to review the data.
The plot result showed that the data was not evenly distributed across different values of the columns. So, I decided to filter the data for further analysis: list_of_manufacturers = ["ford","chevrolet"] list_of_condition = ["excellent","good","like new"] list_of_fuel = ["gas"] list_of_title = ["clean"] list_of_type = ["SUV","sedan","truck"] list_of_size = ["full-size","mid-size","compact"] list_of_paint = ["red","blue","black","grey","silver","white"] list_of_cylinders = ["4 cylinders","6 cylinders","8 cylinders"]
Removed price outliers using quantile method.
Executed Dataframe.corr() to determine the correlation of price and various
attributes and found posivite and negative correlation of various attributes to price.
Split the dataset into training and test datasets.
Step #4: Modeling In this step, I created several models using:

Linear Regression
Ridge Regression
Ridge Regression with optimal alpha (using GridSeachCV)
Sequential Feature Selection
Lasso Regression
Step #5: Evaluation Evaluated all the models using the mean squared error for training and test datasets. Best features found using Sequential Feature Selectors are - condition_excellent
condition_like new
drive_4wd
size_compact size_full-size
type_SUV
type_truck
paint_color_red

The Lasso model was found to have the least training MSE. But the training MSE was higher.

After evaluating the training and test MSEs of all the models, I concluded that the model generated using sequential feature selection is the best as the difference between the training and test MSEs is on the lower side compared to that of the other models.

Step #5: Deploy the Readme and jupyter notebook to GIT Hub.
