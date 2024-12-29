# Predict customer clicked ads classification by using machine learning

## Background
An Indonesian company is interested in evaluating the performance of advertisement on their website. This evaluation is essential for the company as it helps gauge the advertisement’s reach and its ability to engage customers.

By analyzing historical advertisement data and uncovering insights and trends, this approach can aid the company in defining their marketing objectives. In this specific case, the primary emphasis lies in developing a machine learning classification model that can accurately identify the target customer demographic.

## Goal
- Develop a precise machine learning model to forecast ad clicks effectively.
- Leverage data-driven insights to refine and strengthen the company’s marketing initiatives.
- Improve audience targeting to maximize the effectiveness of advertising campaigns.

## Objective
- Develop machine learning models tailored to accurately predict user behavior, identifying those most likely to click on advertisements.
- Select the optimal model for this scenario by evaluating performance metrics such as Recall and Accuracy, prioritizing simplicity and efficient prediction times.
- Analyze and identify key factors influencing users' likelihood to engage with advertisements.
- Offer actionable recommendations to the marketing and management teams for enhancing targeted ad strategies, based on insights from data analysis and model outcomes.

## Column Explanation
- Daily Time Spent on Site: Average time spent by users on the website.
- Age: Age of users.
- Area Income: Income level of users' areas.
- Daily Internet Usage: Daily internet usage by users.
- Male: Gender of users (binary: "Male" or "Female").
- Timestamp: Timestamps or dates of user data.
- Clicked on Ad: Indicator of whether a user clicked on an ad (binary: "Yes" or "No").
- City: City where users are located.
- Province: Province or region of users.
- Category: Categorical variable or category.

## Data Analysis
Univariate Analysis

![image](https://github.com/user-attachments/assets/ac9b56be-82c8-47dd-af8b-16758e427f5b)
![image](https://github.com/user-attachments/assets/e4c4df21-f570-4a01-998e-96b7e40f86ec)
![image](https://github.com/user-attachments/assets/1c1e502c-5136-45fe-b010-96d9609ba724)
![image](https://github.com/user-attachments/assets/4297a899-a787-486f-b06a-57b7a4bcddc9)
Analysis :
- The distribution of data on the target (Clicked on Ad) is even, so no processing is required to reduce / add data.
- Daily Time Spent on Site, Age, Daily Internet Usage columns have nearly normal distributions.
- Area Income column has negative skewed indicating outliers.

Bivariate Analysis
![image](https://github.com/user-attachments/assets/da8b4e88-639f-4aff-8687-56a7a1d98edc)
![image](https://github.com/user-attachments/assets/7155b12c-2bf1-4ada-8e34-97d3869c9bc1)

Heatmap Analysis
![image](https://github.com/user-attachments/assets/f53e560a-da4b-4008-be6b-80ed47bee5ed)
- Daily Time Spent on Site and Daily Internet Usage have a fairly strong positive correlation. This means that the more time a person spends on a website, the more likely they are to have high daily internet usage.
- Daily Time Spent on Site and Age have a fairly strong negative correlation. This means that the older a person is, the less time they spend on a website.

Summary for the all the correlation columns above:
- Customers who click on ads have an average screen time of between 40-50 minutes.
- The age of customers who click on ads is between 35-45 years.
- Customers with an area income between 2.5-4 tend to click on ads.
- Customers with usage of 120-160 tend to click on ads.
- Women click on ads more than men.
- Bandung City has the highest ad click rate, while the lowest is in Serang City.
- West Java Province has the highest ad click rate, while the lowest is in West Kalimantan Province.
- The most popular category is automotive, while the least popular is finance.



