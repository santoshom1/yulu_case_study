## TABLE OF CONTENT:
- [ABOUT YULU & DATASET](#yulu-case-study)
- [UNIVARIATE ANALYSIS](#univariate-analysis)
- [BI-VARIATE ANALYSIS](#bi-variate-analysis)
- [BUSINESS OBJECTIVE 1](#business-objective-1)
- [BUSINESS OBJECTIVE 2](#business-objective-2)
- [BUSINESS OBJECTIVE 3](#business-objective-3)
- [BUSINESS OBJECTIVE 4](#business-objective-4)
- [CORRELATION BETWEEN FEATURES](#correlation-between-features)
- [BUSINESS INSIGHTS](#business-insights)
- [CONCLUSION](#conclusion)


## yulu case study
Yulu is India’s leading micro-mobility service provider, which offers unique vehicles for the daily commute. Starting off as a mission to eliminate traffic congestion in India, Yulu provides the safest commute solution through a user-friendly mobile app to enable shared, solo and sustainable commuting.
Yulu zones are located at all the appropriate locations (including metro stations, bus stands, office spaces, residential areas, corporate offices, etc) to make those first and last miles smooth, affordable, and convenient. 
Yulu has recently suffered considerable dips in its revenues. They have contracted a consulting company to understand the factors on which the demand for these shared electric cycles depends. Specifically, they want to understand the factors affecting the demand for these shared electric cycles in the Indian market.
## the company wants to know
- Which variables are significant in predicting the demand for shared electric cycles in the Indian market?
- How well those variables describe the electric cycle demands
## dataset - [link](https://d2beiqkhq929f0.cloudfront.net/public_assets/assets/000/001/428/original/bike_sharing.csv?1642089089)

- Click here to view the full case study notebook:
📘 [View Notebook](Yulu.ipynb)
- Open it directly in Colab:  [▶️ Open in Colab (right-click to open in new tab)](https://colab.research.google.com/drive/1W0CqPQukjjhwfaMl6nTZaYWC-KL49mPC)

## Basic Exploration
- There are 10886 rows of data for each column
- Here columns seems to be having one object type variable and rest other are numeric variables
- The data has No missing values or null values or any duplicated values
- Datetime columns holds unique values for every row, season and weather has on 4 unique categories followed by holiday and workingday columns having 2 unique categories.

- For these columns it is better for our understanding to assign unique names for unique categories in each column as given in the problem statement .Now we have 5 object type columns, and 7 numerical and 1 date time column in the data.

## UNIVARIATE ANALYSIS
**Temperature(temp)** :  The temperature data is roughly normally distributed , indicating moderate temperature  are the most common

**Humidity**  : Humidity data is also similar to normal distribution with a peak around 60-80%, Indicating moderate to high humidity is common.

**Windspeed** :  Windspeed data is heavily skewed towards lower values indicating most days have lower wind speeds

**Casual** : The distribution is heavily right skewed with most days having  a low number of casual users  but a very few days showing high usage

**Registered** : Similar to casual users the distribution is right skewed  though the count of registered users generally higher than casual users 

**Total Rentals** :  The distribution is right-skewed, with most days having a low total count of rentals, but a significant number of days having high rental counts

<img width="1069" height="746" alt="image" src="https://github.com/user-attachments/assets/467f6266-e9f4-4236-8955-7bb446047c2a" />


## BI-VARIATE ANALYSIS:
**working day & holiday analysis:**
- There were Only 2.8 percent of Holiday records out of 10 thousand records where non-working days holds 32% of records, this difference is because of which weekends were not included in holidays.
- Working day holds 68 % of the data whereas non-holiday holds 97% of the records

<img width="652" height="487" alt="image" src="https://github.com/user-attachments/assets/87b6ac4f-2aa1-458e-bbf1-e1e6ba5af811" />


**season and workingday:**
- Three seasons summer, winter and fall are mostly having same value holding 2730 records each However fall is having Most number of bike rentals followed by summer and winter. where as spring shows a high dip on the bike rentals.

<img width="282" height="262" alt="image" src="https://github.com/user-attachments/assets/d48717f9-ce14-45e5-8839-c98653384339" />

- from the below barplot it is observed that working has no effect on the bike rentals season wise. For any season whether it might be a working day or not the impact on the bike rentals looks significantly similar.

<img width="586" height="460" alt="image" src="https://github.com/user-attachments/assets/c07e4004-0ec3-4fb4-bfb8-13b938e098a5" />

**season and weather:**
- Most of the data contains the record of the weather condition as clear or cloudy and most of the rentals were made in this weather condition only as it is suitable for anyone to ride in this condition.
- The second most is misty and cloudy weather where it holds 5 lakh number of bike rentals closely to 30 % of the total rentals
- Heavy rain and snowy weather shows the least number of bike rentals, as weather is not suitable for anyone to be outside the roof.
- the below bar plot tells us spring being the least contributor to the total bike rentals across all weather conditions.
  where as the rest of three seasons shows significantly contributing equally to the total rentals across all the seasons.
<img width="606" height="466" alt="image" src="https://github.com/user-attachments/assets/dee1f9e1-3651-4e59-b9ee-fa7056689b7b" />


**temperature vs totalrentals:**
- Bike rentals were mostly rented in between the temperature of 15 to 35 celcius , indicating moderate temperature are the most common

<img width="1040" height="488" alt="image" src="https://github.com/user-attachments/assets/8764524c-dd2f-4586-9d1f-b48e976fe19b" />


- The temperature people likely to rent a bike and travel is around the temperature between 25 to 30 celcius as shown in the picture below
<img width="219" height="276" alt="image" src="https://github.com/user-attachments/assets/8526ac20-c236-4ef0-8ed1-660507165eb9" />


**Humidity vs Total_rentals:**
- The Humidity in which people likely to rent a bike and travel is between 40 to 60 as shown in the picture below
<img width="238" height="428" alt="image" src="https://github.com/user-attachments/assets/a9c04556-f75a-4e98-a519-7e80bc0ced92" />


**windspeed vs Total_rentals:**
- The Windspeed where people likely to rent a bike and travel is around the windspeed between 0 to 20  as shown in the picture below, more the windspeed less people are likely to rent a bike,
- 
<img width="247" height="288" alt="image" src="https://github.com/user-attachments/assets/db197387-38b6-4728-9953-aae64f86755a" />

<img width="279" height="293" alt="image" src="https://github.com/user-attachments/assets/61e00bc9-8185-4c0e-8b36-342b1a00a564" />


## Business Objective 1:

***- Which variables are significant in predicting the demand for shared electric cycles in the indian market?***

***Strategic Objective:***

- for this to be answered there are some variables that needs to be tested with count of bike_rentals to check for dependency.
- 
**Weather vs Total_rentals:**
  
- H0 : There is no significant difference in bicycle demand across different weather conditions.
- H1 : There is a significant difference in bicycle demand across different weather conditions.
*weather where heavy rain or snow occurs has no significance to the demand as it has fewer records.*
- the qqplot we got shows us that data is not normally distributed and for levene's test also shows us variances are not equal which brings us to non-parametric tests.
- kruskal test is one of the non-parametric test which is replacement of ANOVA when anova assumptions are not met. After doing kruskal-vallis test p-value obtained is signifcantly lower than any aplha value then null hypothesis is rejected.
- Here; pval = 3.12206618e-45, Consider an alpha as 0.05. since pval is very much lesser than alpha Null Hypothesis is Rejected and We can conclude that ***There is a significant difference in bicycle demand across different weather conditions.***
- 
**Season vs Total-rentals:**
  
**H0 : Season has no effect on bike rentals**

**H1 : Season has effect on bike rentals**
- Three seasons summer, winter and fall are mostly having same value holding 2730 records each However fall is having Most number of bike rentals followed by summer and winter. where as spring shows a high dip on the bike rentals.
- the qqplot we got shows us that data is not normally distributed and for levene's test also shows us variances are not equal which brings us to non-parametric tests.
- kruskal test is one of the non-parametric test which is replacement of ANOVA when anova assumptions are not met. After doing kruskal-vallis test p-value obtained is signifcantly lower than any aplha value hen null hypothesis is rejected.
- Here Pval : 2.2263613e-151, Consider an alpha as 0.05. since pval is very much lesser than alpha Null Hypothesis is Rejected and We can conclude that ***Season has effect on bike rentals.***
***As per the numbers working day and holiday columns any way have power over demand for bike rentals.***

## Business Objective 2:

***- Working day has effect on number of electric cycles rented?***

***Strategic Objective:***

**H0 : Working day has no effect on bike rentals**

**H1 : Working day has effect on bike rentals**
- A non working day has over 6.5lakh bike rental records where as a working day holds records 14.5 lakh bike rentals which suggests that bikes are mostly rented by employees on their way to office from home or home from office
- the qqplot we got shows us that data is not normally distributed and for levene's test also shows us variances are not equal which brings us to non-parametric tests.
- kruskal test is one of the non-parametric test which is replacement of ANOVA when anova assumptions are not met. After doing kruskal-vallis test p-value obtained is signifcantly lower than any aplha value hen null hypothesis is rejected.
- Here Pval :0.9667, Consider an alpha as 0.05. since pval is very much higher than alpha we fail to reject Null Hypothesis and We can conclude that ***working day has no effect on bike rentals.***

## Business Objective 3:

***- No.of  Cycles rented similar or diffrent in diffrent seasons?***

***Strategic Objective:***

- Number of cycles rented are different in different seasons

<img width="836" height="620" alt="image" src="https://github.com/user-attachments/assets/21bc7315-9b0a-4719-aa02-f4f261898db5" />


## Business Objective 4:

***- No.of Cycles rented similar or different in different weather?***

***Strategic Objective:***
- yes, number of cycles rented rented are diffrent in different weather

<img width="809" height="607" alt="image" src="https://github.com/user-attachments/assets/c366b766-0151-447d-b49b-ab81efa7edcb" />


- ***From the above Data it is clearly observed that people are mostly like to prefer clear or cloudy weather to rent a bicycle.***

## CORRELATION BETWEEN FEATURES:
<img width="1920" height="1080" alt="Screenshot (3680)" src="https://github.com/user-attachments/assets/584fbc89-a2db-4e52-b6ce-c8ce2940d83d" />

**High positive Correlation:** 

- Registered And Total_rentals: 
The number of registered users is highly positively correlated with the total count of rentals at 0.97, implying that registered users significantly contribute to the overall count.
- Casual Ans Total_rentals: 
The number of Casual users is highly positively correlated with the total count of rentals at 0.69, implying that Casual users are considerable part of the total users base.

**Moderate positive Correlation:**
- temp and total rentals: Temp and total rentals are correlated at a value of 0.39, this suggests that higher temperatures are associted with an increased demand for bicycles.

**Negative Correlation:**

- Humidity and  total rentals: 
Humidity and count are correlated at a value of -0.32, Higher humidity values are moderately negatively correlated with the total rentals  indicating that people are less likely to rent bicycles in more humid conditions.

- windspeed and casual : 
windspeed negatively correlates with the count of casual users at -0.32, suggesting that higher windspeeds may prevent the occurances of casual users.

**Observation:**

- weather and humidity(0.41) : weather conditions show a moderate positive correlation with humidity, indicating that certain weather conditions are associated with higher humidity levels.

## BUSINESS INSIGHTS:

-**Temperature influence:**
Higher temperatures are associate with the increased bicycle rentals. 

**Strategic Implication:**
Enhance service availability and marketing efforts During warmer periods to capture higher demands.

**Humidity and Windspeed:**
Higher humidity and windspeed negatively affect bicycle rentals. Humidity shows a negative correlation(-0.32) with total rentals while wind speed negatively correlates (-0.32) with casual users.

**Strategic Implication:**
Provide incentives or promotions during high humidity or wind speed periods to maintain rental numbers.

**Weather Conditions:**
weather condition significantly affect bicycle demand. Clear weather pulls the highest demand, while adverse weather condition reduce rentals.

**Strategic Implication:**
Monitor weather forecasts and adjust operations accordingly, possibly offering discounts or special services during less favorable weather.

**Seasonal variations:**
Bicycle demand varies significantly across seasons, with specific seasons showing higher total rentals.

**Strategic Implication:**
Plan inventory and staffing based on seasonal demand trends to optimize operations and costs.

**Registered vs Casual Users:**
Registered users have a high positive correlation (0.97) with the total count, indicating they are the primary drivers of demand while casual users also significantly contribute to the total count(0.69)

**Strategic Implication:**
Focusing on expanding the registered user base through loyalty programs and target marketing.

**Weekday vs Weekend Demand:**
There is no significant difference in the number of bike rides between weekdays and weekends.

**Strategic Implication:**
Maintain consistent service levels throughout the week, without needing drastic operational changes between weekdays and weekends.

**Impact of Holidays:**
Holidays account for a small propotion of the data but can show spikes in the demand.

**Strategic Implication:**
prepare for potential demand spikes on holidays with promotional events or increased inventory.

## CONCLUSION:

*By leveraging these insights, Yulu can enhance their operational efficiency , optimize inventory management, and develop targeted marketing strategies. Understanding the impact of various factors on bicycle demand enables data-driven decision making, leading to improved customer satisfaction and increased profitability.*
