
### Table of Contents

1. [Installation](#installation)
2. [Project Motivation](#motivation)
3. [Project Descriptions](#description)
4. [Results](#results)
5. [References](#references)
6. [Licensing, Authors, and Acknowledgements](#licensing)

## Installation <a name="installation"></a>

Code should run with no issues using Python versions 3.*. The following are the libraries and packages needed to successfully run the project:

- pandas
- numpy
- math
- json
- matplotlib
- sklearn preprocessing libraries
- sklearn
- seaborn
- xgboost

## Project Motivation<a name="motivation"></a>

I have always found promotional offers by businesses to be interesting. Therefore I could not pass up the opportunity to work on  a dataset from one of the worlds leading retail companies.  I am interested in how these special offers raise a customer's interest and influence a purchase, and how the different offers influence customer buying behavior. With this project I intend to use exploratory analysis and models to unearth features that influence offer completion in the dataset.

## Project Description<a name="description"></a>

The project uses simulated data of Starbucks customers behavior on the Starbucks rewards app. Starbucks customers sometimes receive an offer or two for its products. The dataset is a simplified version of the actual data. It only contains offers related to a single product instead of many. The users might receive more than one offer or no offer at all.

The Capstone Challenge Project builds a successful machine learning model which predicts whether customers of a certain demographic will most likely complete an offer. The project seeks to help Starbucks on which demographic of customers are most likely to complete its offers. We will explore the following demographics and then choose the one that is mostly suitable for the Machine learning model. They are:

- Income level
- Gender
- Age
- Offer Duration
- How the offer is communicated
- Offer type
- Offer Completion
These are the areas which are thought to have major impact on the behavior of Starbucks customers. The actual degree to which they matter will become apparent as the dataset is explored. The features seen as the most significant to the completion of offers will be further explored and used where necessary for the model.



## Dataset Descriptions <a name="dataset"></a>

The data set contains simulated data that mimics customer behavior on the Starbucks rewards mobile app. Once every few days, Starbucks sends out an offer to users of the mobile app. An offer can be merely an advertisement for a drink or an actual offer such as a discount or BOGO (buy one get one free). Some users might not receive any offer during certain weeks.

Not all users receive the same offer, and that is the challenge to solve with this data set.
Every offer has a validity period before the offer expires. As an example, a BOGO offer might be valid for only 5 days. You'll see in the data set that informational offers have a validity period even though these ads are merely providing information about a product; for example, if an informational offer has 7 days of validity, you can assume the customer is feeling the influence of the offer for 7 days after receiving the advertisement.
There are 3 datasets namely:
- portfolio
- profile
- transcript

Data Dictionary
profile.json
Rewards program users (17000 users x 5 fields)

gender: (categorical) M, F, O, or null
age: (numeric) missing value encoded as 118
id: (string/hash)
became_member_on: (date) format YYYYMMDD
income: (numeric)
portfolio.json
Offers sent during 30-day test period (10 offers x 6 fields)

reward: (numeric) money awarded for the amount spent
channels: (list) web, email, mobile, social
difficulty: (numeric) money required to be spent to receive reward
duration: (numeric) time for offer to be open, in days
offer_type: (string) bogo, discount, informational
id: (string/hash)
transcript.json
Event log (306648 events x 4 fields)

person: (string/hash)
event: (string) offer received, offer viewed, transaction, offer completed
value: (dictionary) different values depending on event type
offer id: (string/hash) not associated with any "transaction"
amount: (numeric) money spent in "transaction"
reward: (numeric) money gained from "offer completed"
time: (numeric) hours after start of test

The full set of files related to this course are owned by Udacity, so they are not publicly available here.  However, you can see pieces of the analysis here.  This README also serves as a template for students to follow in creating their own project README files..  

There is an additional `.py` file that runs the necessary code to obtain the final model used to predict salary.
There is a jupyter notebook that documents and runs all the code for the project.

## Results<a name="results"></a>

The 3 models in the project were all analyzed using the Root Mean Square Error(RMSE). It is the standard deviation of the residuals (prediction errors). Residuals are a measure of how far from the regression line data points are; RMSE is a measure of how spread out these residuals are. In other words, it tells you how concentrated the data is around the line of best fit.
The RMSE from our 3 models above are:
- Baseline Model: Train RMSE error: 0.06461127565148764, Test RMSE error: 0.13643719402592924
- Correlation Tuned Model: 0.06368740514313077, Test RMSE error: 0.15087425084601191
- GridSearchSv Model: Train RMSE error: 0.05766602233052254, Test RMSE error: 0.10836191475391388

As can be seen from above the GridSearchSv model performed the best as it had the least errors both in the Train and Test sets. In the Correlation Model the training data performed better better than the Baseline model but the test is worse off. This might be explained by overfitting in the Baseline model.

The 3 most important features for event offer completion in the model are:
- reward_x
- channel_email
- discount

The technical description  of the code can be found at the post available [here](https://medium.com/@josh_2774/how-do-you-become-a-developer-5ef1c1c68711).

## References<a name="references"></a>
https://www.kaggle.com/questions-and-answers/115480
https://towardsdatascience.com/fine-tuning-xgboost-in-python-like-a-boss-b4543ed8b1e
https://machinelearningmastery.com/avoid-overfitting-by-early-stopping-with-xgboost-in-python/
https://www.statisticshowto.com/probability-and-statistics/regression-analysis/rmse-root-mean-square-error/#:~:text=Root%20Mean%20Square%20Error%20(RMSE)%20is%20the%20standard%20deviation%20of,the%20line%20of%20best%20fit.
https://stackoverflow.com/questions/34029865/how-to-plot-bar-chart-for-a-list-in-python
https://www.marketing-schools.org/types-of-marketing/promotional-marketing.html
https://yoast.com/psychology-discounts/


## Licensing, Authors, Acknowledgements<a name="licensing"></a>

Must give credit to Starbucks and Udacity for the data.  You can find the Licensing for the data and other descriptive information at the Kaggle link available [here](https://www.kaggle.com/stackoverflow/so-survey-2017/data).  Otherwise, feel free to use the code here as you would like!

Author: Yasir Waziri
