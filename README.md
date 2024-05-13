# DataScience_Insights

# Project: Will the Customer Accept the Coupon?
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
