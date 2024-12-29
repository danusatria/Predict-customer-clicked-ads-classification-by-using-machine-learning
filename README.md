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

## Data Processing
### Checking null in dataset
![image](https://github.com/user-attachments/assets/ffa09530-d2c4-4cc0-a0c4-500e47ff8b6e)

There are 13 null data, the data is very small compared to the total data (1.3%). So it is deleted.

### Checking duplicated data
There no duplicated data.

### Feature Encoding
Do one hot encoding for columns: 'Gender', 'Clicked on Ad', 'city', 'province', 'category'

### Change 'Timestamp' column to datetime format
Extract year, month, week and day in separate columns

### Data Splitting
The data was split into training and testing sets. This is common practice as to make sure that the machine learning models weren’t simply memorizing the answers from the data it was given. The data was split in a 70:30 ratio, 70% training data and 30% testing data.

## Modeling
During the modeling phase, an experiment was carried out where machine learning models were trained and tested using both non-normalized/non-standardized data and normalized/standardized data. The results from both approaches were compared. Hyperparameter tuning was performed in each scenario to optimize model performance. The combination of the model and standardization method that produced the best results will be selected. A total of six models were tested, including the following:
- Support Vector Machine
- Gradient Boosting
- Decision Tree
- Random Forest
- Logistic Regression
- KNeighbors Classifier

### Without Normalization/Standardization
![image](https://github.com/user-attachments/assets/3b1cdcf7-4e9f-4a88-b175-8d72b0ebe691)
![image](https://github.com/user-attachments/assets/6a588fbf-eabf-46ed-994f-3acc1c72e333)


Model Observation:
- Low accuracy (71%) and poor performance.
- Top Features: Daily Time Spent on Site, Daily Internet Usage.

### With Normalization/Standardization
![image](https://github.com/user-attachments/assets/6e10160a-30be-4e68-931c-19935461b222)
![image](https://github.com/user-attachments/assets/d46ec074-8f8a-4c29-b315-1dbc26dceb51)

Model Observation:
- High accuracy (97%) and poor performance.
- Top Features: Daily Time Spent on Site, Daily Internet Usage.

### Model Summary:
- Experiment 1: Without data normalization, the model performed poorly in predicting ad clicks. Key features such as Daily Time Spent on Site and Daily Internet Usage alone were insufficient for accurate predictions.
- Experiment 2: Incorporating data normalization significantly improved the model's accuracy and precision, enabling more effective identification of potential ad clickers.
- Key Findings: The most influential features for prediction were Daily Time Spent on Site and Daily Internet Usage, underscoring their importance in understanding user behavior.
- Conclusion: Data normalization is essential for enhancing model performance and is strongly recommended as part of the modeling process.

### Feature Importance

![image](https://github.com/user-attachments/assets/4726878d-daa1-4b74-9cd5-1e17adad894e)

Feature Importance Analysis
The analysis has highlighted two key features that significantly influence user behavior and ad click-through rates:
- Daily Internet Usage: This is a vital indicator of user engagement. Users who spend more time online are generally more active and attentive, making them more likely to respond to ads.
- Daily Time on Site: This directly impacts users' exposure to advertisements. Longer visits provide increased opportunities for users to interact with and respond to ads.

These features, Daily Internet Usage and Daily Time on Site, are invaluable for understanding user behavior and optimizing ad campaigns, offering actionable insights for targeting and strategy development

### Business Recomendation Based on 2 Top Feature Importance (Daily Internet Usage, Daily Time Spent On site)
- Optimize User Experience: Improve the quality of website content and design to increase the time users spend on the site. Use user data to provide relevant product or service recommendations.
- Market Segmentation Based on Age: The older age group tends to be more responsive to ads. Thus, we can develop segmented ad campaigns to appeal to senior consumers. This can involve offering products or services that suit their needs and preferences.
- Segmentation Based on Income Level: Given the high interest of low-income users in ads, we can optimize our ad budget by targeting this market segment. By offering cost-effective solutions, we can build long-term customer loyalty.

### Business Simulation
- Scenario 1: Without using machine learning
  - Assumption:
    - Cost per ad: Rp 1,000
    - Average purchase value: Rp 500,000
    - Conversion rate (CR): 5%
    - Target number of ads: 1,000 users
    - Number of users who actually click on ads: 500 people
    - Click rate: 500/1,000 * 100 = 50%
- Calculation:
  - Advertising cost: Rp 1,000 x 1,000 users = Rp 1,000,000
  - Number of purchases: Number of users who actually click on ads x CR = 500 users x 5% = 25 purchases
  - Revenue: Number of purchases x Average purchase value = 25 purchases x Rp 500,000 = Rp 12,500,000
  - Profit: Revenue - Advertising cost = Rp 12,500,000 - Rp 1,000,000 = Rp 11,500,000
 
- Scenario 2: With using machine learning
    - Assumption:
      - Cost per ad: Rp 1,000
      - Average purchase value: Rp 500,000
      - Conversion rate (CR): 5%
      - Target number of ads: 1,000 users
      - Number of users who actually clicked on the ad: Precision x Target number of users = 98% * 1,000 users = 980 users
      - Click rate: 980/1,000 * 100 = 98%
    - Calculation:
      - Advertising cost: Rp 1,000 x 1,000 users = Rp 1,000,000
      - Number of purchases: Number of users who actually clicked on the ad x CR = 980 users x 5% = 49 purchases
      - Revenue: Number of purchases x Average purchase value = 49 purchases x Rp 500,000 = Rp 24,500,000
      - Profit: Revenue - Advertising cost = Rp 24,500,000 - Rp 1,000,000 = Rp 23,500,000
     
### Conclusion
By comparing the profit and click rate before and after implementing the model, we can see that with the implementation of the model, the click rate increased from 50% to 98%, and the profit also increased from Rp 11,500,000 to Rp 23,500,000 (an increase of 104.35%).
