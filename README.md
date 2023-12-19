# -Airbnb_Price_Prediction-
Project Introduction:
Airbnb hosted over 60M people in 34000 cities across the world and continuing to grow quickly. So the problem statement is to predict the price of Airbnb house based on multiple factors like locality, reviews per month, availability, room type etc. Also I had created some dashboards in Tableau for depth knowledge of Data set and trying to understand the pricing dynamics of Airbnb. 

Objective:  With the help of this project, Airbnb Home providers can find equilibrium price that optimizes the profit and affordability. Also Guests can find the affordable and desired Airbnb with less prices. They can also plan their journey according to their budget and season. It also increases the employment for the people who have extra space and provide a better and affordable place for guest who are looking for housing options. 

Methodology:
So let’s start with flow of Project:
every data science project follow life cycle whose first step is Data extraction, I had taken the dataset from Kaggle, it is Airbnb New York data set. 

2nd step is Data preprocessing, in this part, first we need to understand the attributes and behavior of data like, how many columns are there, what are the data types and how much data is missing? I have to treat missing values; I had filled mean values in place of null in some columns and simply remove the whole row in some column.  Also remove insignificant columns from the dataset.

3rd step is Exploratory data analysis, it is an approach to analyze the dataset and summarize the data and find patterns in it. I had also analyzed categorical and numeric features by univariate and bivariate analysis.

4th step is feature engineering, it is a process of using domain knowledge to extract feature from raw data. These features are used to improve the performance of machine learning model. In this step, I had converted categorical features like neighbourhood group, root_type and neighbourhood into numerical features beacuse these are not processed in machine learning. Also, I had to perform log transformation on Price attribute because it is left skewed.

5th step is model building, in this step, I had applied Linear Regression, Ridge and Lasso Regression and Decision Tree on preprocessed data.  I found Decision Tree for predictive model with the help of R-squared score because its accuracy is the higher than all other models.

6th step is model deployment, first I dumped the most accurate model into pickel file. I had created a Flask app which takes input as Neighbourhood group, room type availability and show predicted result on screen. 


Challenges: 
1st one is treatment of Categorical attribute, in the starting of project, I removed categorical attributes because in regression, I only need numeric features. So I just remove all the categorical features. Then model’s accuracy is very bad. Then I realized that I had done some big mistake.
Solution:  After that I had treated categorical features with the help of label encoding and one hot encoding which converted categorical features into numeric features.

2nd challenge: The data is positive skewed that means there are more no of tuples having less price. This generate a bias in dataset so the our prediction model gives less prices all the time. 
Solution: I had applied log transformation on Price attribute which resolve this problem. Hence the accuracy of model increases.

3rd challenge: 

Results: 1. avg. Price of Airbnb house in manhatten is 31% which is maximum among all the neighbourhood group. Bronex is the cheapest as its contribution in pi chart is 14%.
2.most of the persons prefers Entire Room/ Apartment and very less people prefers Shared Room to stay.
3. average price of Entire Room/Apartment is 160 which is twice of the price of Private Room.
