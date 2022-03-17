# Purchase-probability-retail-
Find the customer purchase probability using navigation pattern of customer on website




# A.	Problem statement:
With the help of user behavior data (product browsing and product conversion) on website we have to get the probability of users for buying  a product.

# B.	Approach taken:
Since we have 2 data set behavior and conversion, I have used behavior data set to create the feature and conversion data for creating the target variable. Probability of purchase of a user  is calculated later with the help of final model 

Below steps have been followed for feature creation.

###	Feature engineering
1. Removed some user id which don’t make sense.  
1. “time Spent” feature on a page is calculated for a user for each page.
     
2. time spend on a page (in minute) is the difference of next page click timing and current page click timing.
     
3. few places this minute value is too high, with the help of histogram and box plot I have replaced high value with a statistical value (3rd quantile + 1.5*IQR).

4. we have missing value for “time spend” on those  page where user has visited at the end. These values are filled with median time spent by respective user. 
     
4. “Number of click” features are created for each page by a user.
   
5. Next, aggregated data at user level where time spent and number of clicks are there for each page type and taken as the features.

###	Target creation.

1.	Now conversion data is merged with behavior data on user_id and created a feature called purchased label. In this, value is 1 if user is purchased something otherwise 0.
2.	 classes are not balanced, so upsampled positive class by repeating this class by 11 times.
  
# C.	Interpretation of Results:

1.	I have considered R2 and F-score to evaluate the model performance. In non-linear model metrics values are high on train and test both.
2.	With the help of final model, probability of purchase is calculated for individual user.
  
# D.	Scope for improvement:

1.	Currently we have only one day data, with the help of more data we can create cluster of different patterns followed by users.
2.	Some more user information like gender, age, profession, is user clicked external link to reach at product page will help in improving the model performance.
3.	 In Browsing data if we get product id with product visited page ,this will help in identify which all products user has visited and among those what  he/she has bought. 


 

